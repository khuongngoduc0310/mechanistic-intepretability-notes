---
type: concept
aliases:
  - pre-norm
  - pre-layer normalization
tags:
  - concept
---

# Pre-Normalization
## Definition

Pre-Normalization is a transformer architecture that use [[Layer Normalization]] before feeding into [[Multi-head Attention]] blocks or [[Multi Layer Perceptron|MLP]] blocks.

## Example

$x’ = x + Attention(LN(x))$

$x_{next} = x’ + FFN(LN(x’))$

![[Pasted image 20260915165615.png]]

## Why It Matters

- The residual stream does not get normalized before being caried forward
- More stable training
- Better gradient flow because residual path stay close to identity path ?
- Can suffer from [[representation collapse]] / [[diminishing layer contribution]]

## Related Concepts

- [[Post-Norm]]

## Sources