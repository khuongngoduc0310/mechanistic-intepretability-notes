---
type: concept
aliases:
tags:
  - concept
---

# Attribution Graph

## Definition

- Attribution graph is a graph that describe the influence of one feature to another feature, helping us to trace the steps/path model uses to produce input.
- Nodes in the attribution graph represent [[Feature|features]], token embeddings, [[Reconstruction Error]]s and output logit.
- The edges represent linear effect between the nodes → Activity of each [[Feature]] is the sum of its input edges.

![[Pasted image 20260831100126.png]]

![[Pasted image 20260831100910.png]]
## Related Concepts

## Sources
