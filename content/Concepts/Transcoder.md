---
type: concept
aliases:
  - transcoders
tags:
  - concept
---

# Transcoder

## Definition

A **Transcoder** is a sparse model that reads from the [[Residual Stream]], converts the activation into interpretable [[Feature.md|features]], and uses those features to reconstruct the output of a model component, usually an [[Multi Layer Perceptron]].

$\text{Residual} \rightarrow \text{Sparse Features} \rightarrow \text{MLP Output}$

Unlike an [[Sparse Autoencoder.md|SAE]], it reconstructs the **MLP output**, not its original input.
## Example

$$
\begin{gather*}
\text{Residual Stream} \\
\downarrow \\
\text{Transcoder Encoder} \\
\downarrow \\
\text{Sparse Features} \\
\downarrow \\
\text{Transcoder Decoder} \\
\downarrow \\
\text{Reconstructed MLP Output} \\
\downarrow \\
\text{Residual Stream}
\end{gather*}
$$


## Why It Matters

Transcoders help explain **what an MLP computes**, rather than only what information is represented.

This makes them useful for:

- Finding interpretable computations
- Tracing feature-to-feature interactions
- Building [[Attribution Graph|Attribution Graphs]]

## Related Concepts

- [[Sparse Autoencoder]]
- [[Cross Layer Transcoder]]
- [[Feature]]
- [[Multi Layer Perceptron]]
- [[Residual Stream]]
- [[Attribution Graph]]

## Sources

- [[Circuit Tracing (Anthropic)|Circuit Tracing (Anthropic)]]