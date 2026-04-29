# Papers 2026

## LLM Techniques
- [Engram](https://arxiv.org/abs/2601.07372) -> "When a model sees a phrase like “Diana, Princess of Wales”, it does not retrieve this as a stored entity. Instead, it reconstructs the meaning gradually across multiple layers of attention and feed-forward networks." This explains what they are trying to address better than I could. They encode knowledge in static n-grams and show that it can be cmobined with traditional attention. Very interesting idea from deepseek (once again...)
- [DeepSeek V4](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro/blob/main/DeepSeek_V4.pdf) -> heavily compresses KV cache improving long context performance -> great [video](https://www.youtube.com/watch?v=q8holiIirgo)
