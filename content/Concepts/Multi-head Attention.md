---
type: concept
aliases:
  - MHA
  - Attention
tags:
  - concept
---

# Multi-head Attention

## Definition

Multi-head Attention is a block that help attending information from the earlier tokens to the later tokens.
It consist of multiple attention heads, each attention head have the input projected into:

$$ Q = XW_Q,\  K = XW_K,\  V = XW_V$$
Then each head compute:
$$ Attention(Q,K,V) = softmax(\frac{QK^T}{\sqrt{d_k}})V $$
Then all heads are **concatenated**:
$$MHA(X) = Concat(head_1,head_2,...,head_h)W_O$$

Where:
- $Q$ (query): what this token is looking for.
- $K$ (key): what each token offer when match.
- $QK^T$ determine how strongly one token match another token.
- $V$ (value): contain information that it offer if it get attended to.
- $W_O$ : project the concatenated heads into the [[Residual Stream]] dimension.
## Simple Explanation

$$
\boxed{Q \text{ asks},\ K \text{ matches},\ V \text{ provides},\ W_O \text{ combines}}$$

## Why It Matters

- This is the basic concept that offer in [[Attention Is All You Need]].
- Show how one word can offer different meaning based on the context offer before it.

## Related Concepts

## Sources

- [[Attention Is All You Need]]