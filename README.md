# Entropy-Aware Dynamic KV Cache Sparsification   
# for Autoregressive Image Generation and Editing
# Abstract
>Autoregressive (AR) image generation has recently gained momentum as a scalable alternative to diffusion models, benefiting from unified next-token prediction paradigm and strong instruction following ability. 
However, AR visual generation must decode excessively long sequences of visual tokens, making inference heavily bottlenecked by the memory footprint and latency of the self-attention KV cache. 
While KV cache compression is well studied in Large Language Model, its counterparts in AR image generation remain underexplored.
The reason is fundamental: visual tokens are highly redundant, and their spatial information density is highly non-uniform. 
In this work, we introduce \ModelName, a training-free, entropy-aware sparse attention method that is specifically designed for AR image generation and editing. 
Our key insight is that information-rich regions exhibit higher entropy and require broader attention, while redundant regions show lower entropy and allow aggressive sparsification.
Based on this insight, we dynamically identify information-rich regions during decoding and adaptively adjust attention sparsity to reduce KV-cache overhead. 
\ModelName is plug-and-play and can be readily applied to mainstream AR models.
Extensive experiments on four representative AR  models across multiple benchmarks demonstrate that \ModelName significantly \textbf{improves inference efficiency while maintaining, and often even improving, generation and editing quality. 
