# Probabilistic Modeling

Probabilistic modeling provides a **principled and interpretable** framework for learning from data. Rather than assuming a deterministic relationship between data and labels, we treat observations as outcomes of an underlying **random process**. This allows us to reason about **uncertainty**, **make predictions**, and **generate new data**.

This section introduces the foundations of **density estimation**, **maximum likelihood estimation (MLE)**, and **Gaussian modeling**—cornerstones of many unsupervised and generative learning methods.

<br>

**<span style="font-size:1.5em;">Density Estimation</span>**

Suppose we are given a dataset of $N$ observations:

$$
\mathcal{D} = \{ \mathbf{x}_{n} : n = 1, \dots, N \}
$$

We assume these data points are sampled from some unknown **probability distribution** $P_{\theta}(\mathbf{x})$ parameterized by $\theta$:

$$
\mathbf{x}_{n} \sim P_{\theta}(\mathbf{x}_{n})
$$

The task of **density estimation** is to infer the structure of $P_{\theta}(\mathbf{x})$ that best explains the observed data. Once estimated, this distribution can be used to:

- Identify typical vs. rare (outlier) samples  
- Generate synthetic data  
- Enable probabilistic reasoning (e.g., confidence, uncertainty)

<br>

**<span style="font-size:1.5em;">Why Gaussian?</span>**

The Gaussian distribution is a central tool in machine learning due to:

- The **Central Limit Theorem**: the sum of many independent random variables tends toward a Gaussian distribution, regardless of the original distributions.
- Its **mathematical tractability** and closed-form solutions.
- Its flexibility: mixtures of Gaussians (GMMs) can approximate any continuous distribution.

For example:

$$
P(\mathbf{x}) = \sum_{m=1}^M \pi_m \, \mathcal{N}(\mathbf{x} \mid \mu_m, \Sigma_m), \quad \sum_{m=1}^M \pi_m = 1
$$

This forms the basis for **probabilistic clustering** and **generative models** like GMMs and VAEs.
