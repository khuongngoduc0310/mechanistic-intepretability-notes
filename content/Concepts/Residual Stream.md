---
type: concept
aliases:
tags:
  - concept
---

# Residual Stream

## Definition

The **Residual Stream** is the main vector representation that carries information about each token through the transformer layers.

Each attention and [[Multi Layer Perceptron|MLP]] block reads from it, computes an update, and adds that update back into the stream.

## Simple Explanation

Think of it as the model's shared **information workspace**.
$$
\begin{gather*}
\text{Residual Stream} \\
\downarrow \\
\text{Attention / MLP reads from it} \\
\downarrow \\
\text{Computes new information} \\
\downarrow \\
\text{Add the result back} \\
\downarrow \\
\text{Updated residual stream} \\
\end{gather*}
$$

## Why It Matters

The residual stream is important because it is where information is:

- Stored and updated across layers
- Read by [[Attention]] and [[Multi Layer Perceptron|MLP]] blocks
- Used to represent [[Feature.md|features]]
- Traced in mechanistic interpretability

Many tools such as [[Sparse Autoencoder.md|SAEs]] and [[Transcoder.md|Transcoders]] analyze the residual stream to understand what the model is representing and computing.

## Related Concepts

- [[Transformer]]
- [[Attention]]
- [[Multi Layer Perceptron|MLP]]
- [[Feature]]
- [[Sparse Autoencoder]]
- [[Transcoder]]
- [[Cross Layer Transcoder]]

## Sources

- [[Attention Is All You Need]]
- [[Circuit Tracing (Anthropic)]]