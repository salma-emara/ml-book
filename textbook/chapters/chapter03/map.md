# Maximum A Posteriori (MAP) Estimation

**<span style="font-size:1.5em;">MAP Principle</span>**

While MLE chooses parameters that maximize the likelihood of the observed data, **Maximum A Posteriori (MAP)** estimation incorporates prior beliefs about the parameters.

MAP combines the likelihood with a **prior distribution** over the parameters:

$$
P(\theta \mid \mathcal{D}) \propto P(\mathcal{D} \mid \theta) \, P(\theta)
$$

Taking logarithm:

$$
\log P(\theta \mid \mathcal{D}) = \log P(\mathcal{D} \mid \theta) + \log P(\theta) + \text{const}
$$

MAP estimation finds:

$$
\theta^* = \arg\max_{\theta} \left[ \log P(\mathcal{D} \mid \theta) + \log P(\theta) \right]
$$

This is especially useful when:

- We have **limited data**
- We want to **regularize** the estimation
- We want to encode **prior domain knowledge**

<br>

**<span style="font-size:1.5em;">Example: Gaussian Prior</span>**

Suppose the likelihood is Gaussian and the prior over $\mu$ is also Gaussian:

$$
x_{n} \sim \mathcal{N}(\mu, \sigma^2), \quad \mu \sim \mathcal{N}(0, \tau^2)
$$

Then the MAP estimate is:

$$
\mu^* = \frac{\frac{N}{\sigma^2} \, \bar{x}}{\frac{N}{\sigma^2} + \frac{1}{\tau^2}}
$$

This is a **weighted average** of the prior mean (0) and the sample mean $\bar{x}$.

As $N \to \infty$, MAP converges to MLE. But for small $N$, the prior plays a crucial role.
