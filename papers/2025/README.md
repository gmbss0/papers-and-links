# Papers 2025

## Information Retrieval
- [Last but Not Late Interaction for Listwise Document Reranking](https://arxiv.org/abs/2509.25085) -> Documents to be reranked go all into the SAME transformer pass (not in a batch). They introduce document embeddings as document delimeter, that go into a lightweight projector. Finally, these are used as embeddings to compute cosine-similarity with the query embedding. Results seem to be close to qwen3-reranker-4B and significantly better than the 0.6B reranker (while being a "small" 0.6B model itself).
- [Qwen3 Embedding: Advancing Text Embedding and Reranking Through Foundation Models](https://arxiv.org/abs/2506.05176) -> Family of embedding and reranking models of size 0.6B / 4B and 8B. Reranking is framed as a text generation problem where the LM gets the an instruction, a query and a document and is encouraged to output "yes" or "no". The probability for the next token being "yes" is used as reranking score. According to authors it is important to modify the instruction tailored to each task. This can have impact the recall by "1-5%".

## LLM techniques
- [CoT reasoning a mirage?](https://arxiv.org/abs/2508.01191) -> additional evidence that CoT is not "reasoning"; instead the authors refer to it as "structured pattern matching", as CoT performance quickly degrades even when going slightly beyond the training data distribution

## Large Language Diffusion Models
- [LLaDA](https://arxiv.org/abs/2502.09992) -> Diffusion models can perform as good or outperform Auto-Regressive LLMs with similar compute!
- [d1](https://arxiv.org/abs/2504.12216) -> diffuGRPO: method to add reasoning capabilities to diffusion LLMs. 

## Reasoning Models / RL
- [DeepSeekMath](https://arxiv.org/abs/2402.03300) -> GRPO was introduced here, interesting data collection pipeline
- [DeepSeek-R1](https://arxiv.org/abs/2501.12948) -> R1 training pipeline

## Transformer: Architecture and/or Training
- [Attention sinks in Transformers](https://arxiv.org/abs/2504.02732) -> analysis of phenomenon, where transformers attend a lot to the first token in sequence
- [DeepSeekV3 innovations](https://arxiv.org/pdf/2503.11486) -> List of new tricks: key-value joint embedding, expert segmentation and shared expert
- [ByteLatentTransformer](https://arxiv.org/abs/2412.09871) -> Transformer that matches performance of token-based models, but encoding bytes

## Computer Vision
- [SAM 2](https://arxiv.org/abs/2408.00714) -> The image embeddings of frames are conditioned on what they call a "memory-bank", which are the predictions and masks of past frames. This is also leveraged for the data engine. If between 2 frames SAM 2 loses the mask of an object, because it has the past masks in the memory bank, adding one-click on the object will often be enough for the model to recover the mask. If you would start from scratch you would probably need more clicks and here more clicks means less data you can label in the same time (they have created the largest video mask dataset available). 

## not from 2025 but read first time this year...
- [Matryoshka Representation Learning](https://arxiv.org/pdf/2205.13147) -> allow single embedding to adapt to compute contraints of downstream task without the need to train seperate model per embedding size
- [PagedAttention from vLLM](https://arxiv.org/abs/2309.06180) -> KV-Cache implementation that was used to build vLLM on top
- [Speculative Decoding](https://arxiv.org/abs/2211.17192) -> use small fast model to compute N tokens, then pass them in a batch to the big slow model and let it accept tokens or not
