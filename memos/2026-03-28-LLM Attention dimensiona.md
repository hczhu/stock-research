file-created-at:: 2026-03-28

- Meta's latest Code Llama models introduced a powerful fine-tuning technique: "an additional fine-tuning stage that extends the maximum context length from 4,096 tokens to 100,000 tokens." This came as a surprise to me, as I always thought the popular attention-based LLM network had input sequence length, N, as a hyper-parameter. Upon closer inspection of the attention block, no trainable parameter tensor has N as a dimension, although many intermediary output tensors do.
- ![Image](https://pbs.twimg.com/media/F5HkcPHaAAANPgS?format=jpg&name=large)