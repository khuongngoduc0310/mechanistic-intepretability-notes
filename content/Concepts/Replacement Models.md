---
type: concept
aliases:
  - interpretable models
---
# Replacement Models

## Definition 

A model that replace transformer neurons (MLPs) with more interpretable features (SLTs, CLTs,...) to help with circuit tracing.

# Why it matters

Because regular model is harder to track and examine how it behaves, replacing it with spare transcoders (where features are more likely to separate - because of [[Superposition.md#Definition|superposition]]) will help in reverse engineering the model.

# Sources

- [[Circuit Tracing (Anthropic)]]

