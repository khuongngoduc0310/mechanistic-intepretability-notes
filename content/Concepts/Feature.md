---
type: concept
aliases:
  - features
tags:
  - concept
---

# Feature

## Definition

- A **feature** is an interpretable property or concept represented in the model's activations that the model can use in its computation.
- A feature is generally represented as a **direction/pattern across the activation space**, rather than belonging to a single neuron.
- Because of **[[Superposition]]**:
    - One feature can involve many neurons.
    - One neuron can participate in many features
## Type of features (From [[Circuit Tracing (Anthropic)]]:
	- Input features: 
		- Represent low-level properties of text (e.g. specific token or phrases)
		- Appear mostly in the early layers
	- Abstract features: 
		- Represent more abstract properties (e.g. a feature for the danger of mixing common cleaning chemicals)
		- Appear the middle and later layers
	- Function features:
		- Represent function properties (e.g. "add 9" feature)
		- Appear the middle and later layers
	- Output features:
		- Its activation promote a specific output (specific token or categories of tokens)
		- Example: "say a capital" feature.
	- Polysemantic features:
		- Represent many unrelated concepts
		- Appear mostly in the earlier layers

## Related Concepts

- [[Circuit]]
- [[Feature]]

## Sources

- [[Circuit Tracing (Anthropic)]]