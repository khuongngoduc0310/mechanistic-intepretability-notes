---
type: concept
aliases:
  - MLP
  - MLPs
  - Multi-Layer Perceptron
tags:
  - concept
---
# Multi Layer Perceptron

## Definition

An **MLP (Multi-Layer Perceptron)** is the feed-forward part of a transformer layer that independently transforms each token’s residual-stream representation through linear layers and a nonlinearity.

In simple form:

$\text{MLP}(x)=W_2\,\sigma(W_1x+b_1)+b_2$

- $W_1$: expands/transforms the representation
- $\sigma$: nonlinear activation
- $W_2$: projects it back to the residual-stream dimension

Its output is then **added back into the [[Residual Stream]]**.

## Related Concepts

- [[Residual Stream]]
- [[Transformer]]
- [[Transcoder]]
- [[Cross Layer Transcoder]]
- [[Feature]]

## Sources

- [[Attention Is All You Need]]
- [[Circuit Tracing (Anthropic)]]