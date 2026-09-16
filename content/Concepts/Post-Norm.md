---
type: concept
aliases:
  - post-norm
  - post-normalization
  - post layer normalization
tags:
  - concept
---

# Post-Norm

## Definition

Post-Norm is a transformer architecture and uses [[Layer Normalization]] after adding the residual stream and the updates from [[Attention]] or [[Multi Layer Perceptron|MLPs]].

## Example

$x’ = LN(x + Attention(x))$
$x_{next} = LN(x’ + FFN(x’))$


![[Pasted image 20260915165615.png]]

## Why It Matters

- Harder to interpret
- Less common in modern LLMs
- Harder to train
- Perform  better
- Keep the residual stream normalized after layers
- Require learning rate warm-up

## Related Concepts

- [[Pre-Norm]]
- [[.md|Concept Template]]

## Sources

- [[.md|Concept Template]]