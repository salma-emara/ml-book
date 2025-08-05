# Maximum Likelihood Estimation (MLE)

**<span style="font-size:1.5em;">MLE Principle</span>**

To learn the parameters $\theta$ of a model, we use the **maximum likelihood principle**: choose the parameters that make the observed data most probable.

The **likelihood function** measures the probability of the data under the model:

$$
\mathcal{L}_{\mathcal{D}}(\theta) = \prod_{n=1}^N P_{\theta}(\mathbf{x}_{n})
$$

Since multiplying many probabilities can be numerically unstable, we often use the **log-likelihood**:

$$
\log \mathcal{L}_{\mathcal{D}}(\theta) = \sum_{n=1}^N \log P_{\theta}(\mathbf{x}_{n})
$$

MLE seeks the parameters that **maximize** this function:

$$
\theta^* = \arg\max_{\theta} \log \mathcal{L}_{\mathcal{D}}(\theta)
$$

<br>

**<span style="font-size:1.5em;">Bernoulli Example</span>**

Consider a binary random variable $x_{n} \in \{0, 1\}$ following a Bernoulli distribution:

$$
x_{n} \sim \text{Ber}(\theta)
$$

Suppose we observe:

$$
\mathcal{D} = \{1, 1, 0, 1, 0\}
$$

Then the likelihood is:

$$
\mathcal{L}_{\mathcal{D}}(\theta) = \theta^3 (1 - \theta)^2
$$

Taking the logarithm:

$$
\log \mathcal{L}(\theta) = 3 \log \theta + 2 \log(1 - \theta)
$$

Maximizing this function with respect to $\theta$ gives:

$$
\theta^* = \frac{\text{\# of ones}}{\text{total}} = \frac{3}{5} = 0.6
$$

<br>

**<span style="font-size:1.5em;">Gaussian Example</span>**

Now consider continuous variables, e.g., heights or sensor readings. Suppose:

$$
x_{n} \sim \mathcal{N}(\mu, \sigma^2)
$$

and we observe:

$$
\mathcal{D} = \{ 0.3, -1.5, -0.1 \}
$$

The log-likelihood (ignoring constant terms) becomes:

$$
\log \mathcal{L}(\mu) = -\frac{1}{2} \sum_{n=1}^N (x_{n} - \mu)^2
$$

The MLE for $\mu$ is simply the **sample mean**:

$$
\mu^* = \frac{1}{3}(0.3 - 1.5 - 0.1) = -0.43
$$

This shows that MLE reduces
