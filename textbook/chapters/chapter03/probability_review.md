# Probability Review

Probability theory forms the foundation of many machine learning techniques. A solid understanding of probability is essential to model uncertainty, reason about randomness, and design algorithms that learn from data in a principled way. This section reviews key probability concepts that will serve as the basis for probabilistic modeling and learning.

<br>

**<span style="font-size:1.5em;">Discrete Random Variables</span>**

A discrete random variable $x$ takes values from a finite or countable set $\mathcal{X} = \{a_1, \dots, a_I\}$ and is governed by a probability mass function (PMF):

$$
P(x = a_i) = p_i \quad \text{such that} \quad 0 \leq p_i \leq 1, \quad \sum_{i=1}^I p_i = 1
$$

**Example**: A Bernoulli random variable with parameter $\theta$:

$$
x \sim \text{Ber}(\theta) \quad \Rightarrow \quad
P(x) = \begin{cases}
\theta & x = 1 \\
1 - \theta & x = 0
\end{cases}
$$

<br>

**<span style="font-size:1.5em;">Continuous Random Variables</span>**

A continuous random variable $x$ takes values in $\mathbb{R}$ and is described by a probability density function (PDF) $P(x)$ such that:

$$
P(x) \geq 0, \quad \int_{-\infty}^{+\infty} P(x)\, dx = 1
$$

**Example**: A Gaussian (Normal) distribution with mean $\mu$ and variance $\sigma^2$:

$$
x \sim \mathcal{N}(\mu, \sigma^2) \quad \Rightarrow \quad
P(x) = \frac{1}{\sqrt{2\pi \sigma^2}} \exp\left( -\frac{(x - \mu)^2}{2\sigma^2} \right)
$$

<br>

**<span style="font-size:1.5em;">Independent and i.i.d. Samples</span>**

Two random variables $x$ and $y$ are independent if:

$$
P(x, y) = P(x) \cdot P(y)
$$

A set of samples $\{x_1, \dots, x_N\}$ are said to be **i.i.d.** (independent and identically distributed) if:

- Each sample comes from the same distribution
- All samples are statistically independent

<br>

**<span style="font-size:1.5em;">Expectation</span>**

The **expected value** (or mean) of a function $f(x)$ under distribution $P(x)$ is:

$$
\mathbb{E}[f(x)] = 
\begin{cases}
\sum_{x \in \mathcal{X}} f(x) P(x) & \text{if } x \text{ is discrete} \\
\int_{-\infty}^{+\infty} f(x) P(x)\, dx & \text{if } x \text{ is continuous}
\end{cases}
$$

For large number of i.i.d. samples:

$$
\frac{1}{N} \sum_{n=1}^N f(x_n) \approx \mathbb{E}[f(x)]
$$

<br>

**<span style="font-size:1.5em;">Variance</span>**

For a real-valued random variable $x \sim \mathcal{N}(\mu, \sigma^2)$:

$$
\mathbb{E}[x] = \mu, \quad \text{Var}(x) = \mathbb{E}[(x - \mu)^2] = \sigma^2
$$
