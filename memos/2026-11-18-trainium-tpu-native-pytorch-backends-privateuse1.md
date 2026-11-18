tags:: [[$AMZN]], [[$GOOGL]], [[$NVDA]], [[$META]], [[Trainium]], [[TPU]], [[CUDA]], [[PyTorch]], [[XLA]], [[open-source]], [[developer-tools]], [[moat]], [[Huawei]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-18
file-updated-at:: 2026-11-18

- ## Amazon and Google ship native PyTorch backends for Trainium and TPU
	- **Sources**:
		- The owner's observations.
		- [Introducing TorchTPU](https://pytorch.org/blog/introducing-torchtpu/), PyTorch blog, October 20, 2026.
		- The two repos' READMEs and GitHub metadata, pulled 2026-11-18: [aws-neuron/torch-neuronx](https://github.com/aws-neuron/torch-neuronx) and [google-pytorch/torch_tpu](https://github.com/google-pytorch/torch_tpu).
	- **Thesis**: In October 2026 Amazon and Google released open-source plugins that let standard, upstream PyTorch run on Trainium and TPU as ordinary devices, the way it runs on Nvidia GPUs. TorchTPU officially replaces the deprecated PyTorch/XLA, and Google reports near-JAX performance on unmodified PyTorch code. The plugins aim to lower a long-standing software barrier to these ASICs, but GitHub stars so far show little developer pull.

- ## How they work: plugins on upstream PyTorch, not forks
	- **Out-of-tree extensions**: both are installed alongside stock PyTorch, not as modified copies of its codebase. They hook in through PyTorch's **[PrivateUse1](https://docs.pytorch.org/tutorials/advanced/privateuseone.html)** dispatch mechanism, a dispatch key PyTorch reserves for third-party backends. A plugin registers its own kernels for PyTorch's core operators (ATen), names its device, and adds a `torch.compile` backend.
	- **What it means for users**: porting is meant to be a device change, e.g. `.to("cuda")` → `.to("tpu")`. Models then run eagerly, as on a GPU, with graph compilation optional. Google notes that peak TPU performance still needs shapes, sharding and ops tuned for TPU, but the model should run out of the box.
	- **Upstream tracking**: because neither is a fork, each plugin can follow upstream PyTorch releases instead of maintaining a diverged codebase. torch-neuronx encodes its target PyTorch version in its own version number.
	- | | AWS torch-neuronx (Trainium) | Google TorchTPU |
	  |---|---|---|
	  | Status | Beta. Version 2.14.3.0 pinned to PyTorch 2.14, Neuron SDK 2.33. Trn2 and Trn3 only | On PyPI (`torch_tpu`). Google says it already runs production inference and training for some of the largest Google Cloud customers |
	  | Origin | AWS Neuron team. Earlier `torch-neuronx` versions were XLA-based, and this release replaces them | **Google–Meta collaboration** (the PyTorch team at Meta) started in mid-2025. **Officially replaces PyTorch/XLA**, which is now deprecated (owner's note) |
	  | Eager execution | `neuron` device, eager by default. An experimental mode fuses eligible eager ops | Default: one ATen op at a time, asynchronous with the CPU. A new **DeferAndFuse** mode batches eager ops to narrow the gap with compiled execution |
	  | Graph mode | `torch.compile(backend="neuron")` | `torch.compile` built on TorchDynamo (not lazy tensors), aiming for performance similar to JAX compile |
	  | Operator coverage | Per-API support table in the repo | About **450 ATen ops**, including forward and backward passes for all core ATen ops needed by major architectures |
	  | Distributed training | `torch.distributed`, DTensor and functional collectives, for data, tensor and fully sharded (FSDP) parallelism. Multi-node via EFA networking | DDP, FSDP and DTensor, via TPU collectives at PyTorch's Process Group layer. Collectives compile to XLA ops, with no separate NCCL-style library |
	  | Custom kernels | NKI kernels callable from PyTorch, eager or compiled | JAX/Pallas and the Helion DSL, plus Google's **Tokamax** kernel library (attention, MoE grouped matmul) |
	  | Ecosystem integrations | Examples for Llama, Qwen2, Whisper, GPT-2, MoE | Hugging Face Transformers v5 and Diffusers, vLLM, SGLang, TorchTitan, Ray, TorchRec |
	  | Stated gaps | `torch.compile` needs **static shapes** and recompiles per input shape. float64 runs as float32. Limited FlexAttention. No TorchAO MXFP8 | XLA assumes static shapes, so Google is adding "bounded dynamism". Only one process can use a TPU, so RL colocation is not supported out of the box. By default each collective compiles separately, which can cost 30–40% end to end |

- ## TorchTPU and XLA: different layers of the same stack
	- They are not alternatives:
		- | Layer | Role |
		  |---|---|
		  | PyTorch (upstream) | The framework that user code is written in |
		  | **TorchTPU** (`torch_tpu`) | The PyTorch-native backend plugin, built on PrivateUse1. It translates PyTorch ops into StableHLO in both eager and `torch.compile` paths |
		  | **XLA (OpenXLA)** | The low-level compiler. It optimizes StableHLO graphs (and Mosaic for custom kernels) into TPU machine code. It powers **JAX, TensorFlow and PyTorch** on TPU |
		  | PjRT runtime and TPU hardware | Compiles, launches and moves data. The TPU instruction set is proprietary and not public |
	- **Google's PTX analogy**: StableHLO and, even more so, Mosaic play the role of Nvidia's PTX as the stable target layer above the hardware.
	- **Why PyTorch/XLA fell short**, per Google: it was built in 2020 on lazy tensors. It needed intrusive source changes to mark compilable regions, suffered severe compile latency, had **no true eager mode**, and lagged on new distributed primitives. Google says PyTorch/XLA and TorchAX "shoehorn PyTorch into JAX's modus operandi." TorchTPU has no JAX runtime dependency.

- ## TorchTPU results reported by Google
	- | Test | Result |
	  |---|---|
	  | Out-of-box model coverage | 4,917 popular Hugging Face models across 500+ architecture families. **98% run without crashing**, and 97% (638 of 657) match GPU numerically |
	  | Shape-varying (bounded dynamism) correctness | Correct numerics on 834 of 839 causal LLMs (99%) |
	  | Pure-PyTorch Muse Glimmer 30B, no model-specific kernels | Prefill on one TPUv7: about 25.7K tokens/s at **59% MFU** (model FLOPs utilization) for 5,120-token sequences. Training on 4 TPUv7: about 5.6K tokens/s per chip at 38% MFU |
	  | GPU-written TorchTitan Muse Glimmer 30B, minimally adapted | Training on 4 TPUv7: about 5.3K tokens/s per chip at 36% MFU |
	  | Qwen3 MoE 235B on 64 TPUv7, TorchTitan vs. JAX/MaxText | **1,828 vs. 1,937 tokens/s**, so PyTorch is within about 6% of JAX. Scaled to a full TPUv7 pod with roughly flat MFU |
	  | vLLM–TorchTPU inference (SemiAnalysis InferenceX) | Lowest cost per million tokens on InferenceX 8K/1K at 2.01 cents (down from 3.6 cents in September). 0.83 cents on AgentX with 4 chips |
	- See [[2026-09-07-semianalysis-tpuv7-inference-externalization]] for the SemiAnalysis view.

- ## Developer traction so far: GitHub stars
	- Snapshot on 2026-11-18. Stars are a rough proxy for developer interest, not usage, since most users install from PyPI or prebuilt images.
	- | Repo | What it is | Stars | Forks | Repo created |
	  |---|---|---|---|---|
	  | pytorch/pytorch | The framework itself (CUDA support is built in) | 105,681 | 30,756 | 2016-08 |
	  | jax-ml/jax | Google's own framework, TPU-first | 36,649 | 4,010 | 2018-10 |
	  | pytorch/xla | The previous PyTorch-on-TPU path, now deprecated | 2,809 | 574 | 2018-11 |
	  | **google-pytorch/torch_tpu** | **Native PyTorch backend for TPU** | **859** | **97** | 2026-03 |
	  | aws-neuron/aws-neuron-sdk | Trainium and Inferentia SDK docs and issues | 654 | 202 | 2019-11 |
	  | Ascend/pytorch (torch_npu) | Huawei's Ascend plugin, also built on PrivateUse1 | 609 | 114 | 2021-08 |
	  | **aws-neuron/torch-neuronx** | **Native PyTorch backend for Trainium** | **138** | **11** | 2025-09 |
	- Both repos existed months before their October 2026 public release. TorchTPU has about 6× torch-neuronx's stars and 9× its forks, but is still under a third of PyTorch/XLA's count. torch-neuronx is below Huawei's five-year-old Ascend plugin.

- ## Context in the repo
	- **CUDA moat**: one argument is that LLMs weaken CUDA's software moat, because most developers now build on model APIs and Anthropic proved a leading lab can run on Trainium and TPUs. Native PyTorch backends lower the switching cost for the labs and enterprises that do write PyTorch ([[2026-11-18-nvidia-vanishing-moats-after-huang]]).
	- **Google's software push**: SemiAnalysis reported in Nov 2025 that Google was building native PyTorch support for TPUs, plus TPU backends for vLLM and SGLang. Meta's earlier PyTorch/XLA contracts (2020–2023) were cancelled in 2023. TorchTPU is now a joint Google–Meta project ([[2025-11-28-semianalysis-tpuv7-google-takes-a-swing-at-the-king]]).
