tags:: [[$AMZN]], [[$GOOGL]], [[$NVDA]], [[Trainium]], [[TPU]], [[CUDA]], [[PyTorch]], [[open-source]], [[developer-tools]], [[moat]], [[Huawei]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-18
file-updated-at:: 2026-11-18

- ## Amazon and Google ship native PyTorch backends for Trainium and TPU
	- **Source**: the owner's observation, plus the two repos' READMEs and GitHub repository metadata (pulled 2026-11-18): [aws-neuron/torch-neuronx](https://github.com/aws-neuron/torch-neuronx) and [google-pytorch/torch_tpu](https://github.com/google-pytorch/torch_tpu).
	- **Thesis**: In October 2026 Amazon and Google released open-source plugins that let standard, upstream PyTorch run on Trainium and TPU as ordinary devices, the way it runs on Nvidia GPUs. The plugins aim to lower a long-standing software barrier to their ASICs, but GitHub stars so far show little developer pull.

- ## How they work: plugins on upstream PyTorch, not forks
	- **Out-of-tree extensions**: both are installed alongside stock PyTorch, not as modified copies of the PyTorch codebase. They hook in through PyTorch's **[PrivateUse1](https://docs.pytorch.org/tutorials/advanced/privateuseone.html)** dispatch mechanism, a dispatch key PyTorch reserves for third-party backends. A plugin registers its own kernels for PyTorch's core operators (ATen), names its device, and adds a `torch.compile` backend.
	- **What it means for users**: models move to the accelerator with a normal `.to(device)` call and run eagerly, like on any GPU, with graph compilation optional. Before this, PyTorch on Trainium and TPU mostly ran through the **PyTorch/XLA** path, which traces graphs lazily.
	- | | AWS torch-neuronx (Trainium) | Google TorchTPU |
	  |---|---|---|
	  | Status | Beta. Version 2.14.3.0 pinned to PyTorch 2.14, Neuron SDK 2.33. Trn2 and Trn3 only | Public release on PyPI (`torch_tpu`). Python 3.11–3.15, following PyTorch's support matrix |
	  | Device and execution | `neuron` device, **eager by default**. `torch.compile(backend="neuron")` is optional | Custom ATen kernels for TPU, with `torch.compile` for graph mode. Keeps a compilation cache for the **XLA computations** it still runs underneath |
	  | Distributed training | `torch.distributed`, DTensor and functional collectives, for data, tensor and fully sharded (FSDP) parallelism. Multi-node via EFA networking | Data and tensor parallelism |
	  | Custom kernels | NKI kernels callable from PyTorch, in eager mode and inside compiled graphs | Not described in the README |
	  | Example models | Llama, Qwen2, Whisper, GPT-2, MoE, Conformer ASR | Llama, Qwen, ResNet, DLRM, minGPT, UNet |
	  | Stated gaps | `torch.compile` needs **static shapes** and recompiles for each new input shape. float64 runs as float32. Limited FlexAttention. No TorchAO MXFP8 support | Not listed in the README |
	  | Lineage | Earlier `torch-neuronx` versions were the XLA-based product. This release replaces them with a PyTorch-native backend | A separate project from PyTorch/XLA. The README does not describe how the two relate |
	- **Upstream tracking**: because neither is a fork, each plugin can follow upstream PyTorch releases instead of maintaining a diverged codebase. torch-neuronx encodes the PyTorch version it targets in its own version number.

- ## Developer traction so far: GitHub stars
	- Snapshot on 2026-11-18. Stars are a rough proxy for developer interest, not usage, since most users install from PyPI or prebuilt images.
	- | Repo | What it is | Stars | Forks | Repo created |
	  |---|---|---|---|---|
	  | pytorch/pytorch | The framework itself (CUDA support is built in) | 105,681 | 30,756 | 2016-08 |
	  | jax-ml/jax | Google's own framework, TPU-first | 36,649 | 4,010 | 2018-10 |
	  | pytorch/xla | The previous PyTorch-on-TPU path | 2,809 | 574 | 2018-11 |
	  | **google-pytorch/torch_tpu** | **Native PyTorch backend for TPU** | **859** | **97** | 2026-03 |
	  | aws-neuron/aws-neuron-sdk | Trainium and Inferentia SDK docs and issues | 654 | 202 | 2019-11 |
	  | Ascend/pytorch (torch_npu) | Huawei's Ascend plugin, also built on PrivateUse1 | 609 | 114 | 2021-08 |
	  | **aws-neuron/torch-neuronx** | **Native PyTorch backend for Trainium** | **138** | **11** | 2025-09 |
	- Both repos existed months before their October 2026 public release. TorchTPU has about 6× torch-neuronx's stars and 9× its forks, but is still under a third of PyTorch/XLA's count. torch-neuronx is below Huawei's five-year-old Ascend plugin.

- ## Context in the repo
	- **CUDA moat**: one argument is that LLMs weaken CUDA's software moat, because most developers now build on model APIs and Anthropic proved a leading lab can run on Trainium and TPUs. Native PyTorch backends lower the switching cost for the labs and enterprises that do write PyTorch ([[2026-11-18-nvidia-vanishing-moats-after-huang]]).
	- **Google's software push**: SemiAnalysis reported in Nov 2025 that Google was building native PyTorch support for TPUs, plus TPU backends for vLLM and SGLang. Meta's earlier PyTorch/XLA contracts (2020–2023) were cancelled in 2023 ([[2025-11-28-semianalysis-tpuv7-google-takes-a-swing-at-the-king]]).
