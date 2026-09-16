---
type: concept
aliases:
  - MLA
tags:
  - concept
---

# Multi-head Latent Attention

## Definition

**Multi-Head Latent Attention (MLA)** is an attention mechanism that compresses the **Key (K)** and **Value (V)** information into a smaller **latent representation**.

Instead of storing the full K and V vectors for every attention head, MLA can store this compressed latent representation and use it to perform attention.

$x \rightarrow c_{KV} \rightarrow K,V$

where $c_{KV}$ is the compressed latent representation.

## Simple Explanation

In normal [[Multi-Head Attention]], every previous token stores its K and V information:

$\text{Token} \rightarrow K,V$

This creates a large [[KV Cache]].

MLA instead compresses that information:

$\text{Token} \rightarrow \text{small latent representation}$

So:

> **MHA stores the full K and V information. MLA stores a compressed version of that information.**

The attention heads can still use this compressed information to determine **where to attend and what information to retrieve**.

## Example

Suppose a model has many attention heads.

With normal Multi-Head Attention:

```text
Token 1 → K1, K2, K3, ... + V1, V2, V3, ...
Token 2 → K1, K2, K3, ... + V1, V2, V3, ...
Token 3 → K1, K2, K3, ... + V1, V2, V3, ...
```

A large amount of information must be stored in the KV cache.

With MLA:

```text
Token 1 → compressed latent cKV
Token 2 → compressed latent cKV
Token 3 → compressed latent cKV
```

The model uses this smaller latent representation for attention instead of storing all of the full K and V vectors.

## Why It Matters

The main advantage of MLA is **reducing the size of the KV cache**.

This is important because during LLM inference, the model must remember information about all previous tokens.

A smaller KV cache means:

- **Less GPU memory usage**
    
- **Lower memory bandwidth requirements**
    
- **More efficient inference**
    
- **Longer context lengths are easier to handle**
    
- **More requests can be processed at once**
    

DeepSeek introduced MLA in **DeepSeek-V2**, reporting a major reduction in KV-cache size compared with its earlier architecture.

In short:

MLA = compress attention memory to make inference more efficient\boxed{\text{MLA = compress attention memory to make inference more efficient}}

## Related Concepts

- [[Multi-Head Attention]]
    
- [[KV Cache]]
    
- [[Low-Rank Compression]]
    
- [[Rotary Positional Embedding]]
    

## Sources

- DeepSeek-AI, _DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model_, arXiv:2405.04434