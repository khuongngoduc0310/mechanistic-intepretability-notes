---
type: concept
aliases:
  - Layer Normalization
  - LN
tags:
  - concept
---

# Layer Normalization

## Definition

Layer Normalization normalize a vector so they have nearly **zero mean** and **unit variance.**(variance = 1)

$$ \mu = \frac{1}{d} \sum_i{x_i}  $$
$$ \sigma^2 = \frac{1}{d} \sum_i(x_i - \mu)^2 $$
then
$$ LN(x) = \gamma \frac{x - \mu}{\sqrt{\sigma^2 + \epsilon}} + \beta $$
where:
- $\mu$ is mean of the features
- $\sigma^2$ is variance
- $\gamma$ is learned scale
- $\beta$ learned shift
- $\epsilon$ is a small constant to prevent division by zero

## Example

Suppose:

$$  
x=[1,3]  
$$

Mean:

$$
\mu=\frac{1+3}{2}=2
$$

Variance:

$$
\sigma^2=\frac{(1-2)^2+(3-2)^2}{2}=1  
$$

Ignoring $$(\epsilon):

[-1,1]  
$$

The normalized vector now has:

$$
\text{mean}=0  
$$

$$
\text{variance}=1  
$$

Then LayerNorm applies the learned $\gamma$ and $\beta$.

## Why It Matters

Layer Normalization keeps activation values at a more controlled scale as information moves through the network.

This helps:

- **Training stability** — prevents activations from becoming extremely large or small.
- **Gradient flow** — makes optimization more predictable.
- **Consistent input scale** — attention and FFN layers receive inputs with a controlled distribution.
- **Deep Transformers** — helps many Transformer layers work together without activation scales becoming unstable.

## Related Concepts

## Sources