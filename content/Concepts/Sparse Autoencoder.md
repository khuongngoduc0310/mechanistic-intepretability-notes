---
type: concept
aliases:
  - SAE
tags:
  - concept
---
# Sparse Autoencoder

## Definition

A **Sparse Autoencoder (SAE)** is a model that takes a neural network's activation and converts it into a set of sparse, more interpretable [[Feature.md|features]], then uses those features to reconstruct the original activation.

$\text{Activation} \rightarrow \text{Sparse Features} \rightarrow \text{Reconstructed Activation}$
or

$r \rightarrow  \text{sparse features} \rightarrow \hat{r}$

The word **sparse** means that only a small number of features are active at the same time.

---

## Why It Matters

Because of [[Superposition]], information is not necessarily stored cleanly in individual neurons.

- One [[Feature]] can be distributed across many neurons.
    
- One neuron can participate in many features.
    

This makes individual neurons difficult to interpret.

SAEs try to recover cleaner, interpretable features from those mixed activations.

They are useful for understanding:

- What information the model represents
    
- Which features activate for a prompt
    
- How concepts are encoded
    
- Which features may participate in a [[Circuit]]
    

### SAE vs Transcoder

An SAE reconstructs the **activation it reads**:

```text
Residual Stream
      ↓
Sparse Features
      ↓
Reconstructed Residual Stream
```

A [[Transcoder]] instead tries to reconstruct the **output of another model component**, usually an [[Multi Layer Perceptron]]:

```text
Residual Stream
      ↓
Sparse Features
      ↓
Reconstructed MLP Output
```

Therefore:

> **SAE → explains representation**

> **Transcoder → explains computation**

---

## Related Concepts

- [[Feature.md]]
- [[Superposition.md]]
- [[Residual Stream.md]]
- [[Transcoder.md]]
- [[Cross Layer Transcoder|Cross-Layer Transcoder]]
- [[Multi Layer Perceptron]]
- [[Circuit]]

---

## Sources

- [[Toy Models of Superposition]]
- [[Circuit Tracing (Anthropic)]]