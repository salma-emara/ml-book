# 5.4 Evaluation Metrics

**<span style="font-size:1.5em;">Loss Functions</span>**

For regression tasks, a common choice is the squared loss:

$$
\mathcal{L}(y, v) = (y - v)^2.
$$

For classification tasks, the $0$–$1$ loss is standard:

$$
\mathcal{L}(y, v) =
\begin{cases}
1, & y \neq v, \\
0, & y = v.
\end{cases}
$$

---


**<span style="font-size:1.5em;">Risk</span>**

Given a sample $(\mathbf{x}, \mathbf{v})$ and model output $\mathbf{y} = f(\mathbf{x})$, the **risk** (expected loss) is defined as:

$$
R(f) = \mathbb{E}_{\mathbf{x}, \mathbf{v}} \left[ \mathcal{L} \big( f(\mathbf{x}), \mathbf{v} \big) \right].
$$

For example, in regression:

$$
R(f) = \mathbb{E}_{\mathbf{x}, v} \left[ \big( f(\mathbf{x}) - v \big)^2 \right],
$$

and in the one-dimensional threshold classification case:

$$
R(f) = \Pr \left\{ \mathrm{sign}(x - b) \neq v \right\}.
$$

---

**<span style="font-size:1.5em;">Empirical Risk</span>**

Since the joint distribution of $(\mathbf{x}, \mathbf{v})$ is generally unknown, the **empirical risk** is used as an estimate:

$$
\hat{R}(f) = \frac{1}{N} \sum_{n=1}^N \mathcal{L} \big( f(\mathbf{x}_n), \mathbf{v}_n \big).
$$

By the law of large numbers, if the data samples are i.i.d. and $N$ is sufficiently large, then

$$
\hat{R}(f) \approx R(f).
$$

---

**<span style="font-size:1.5em;">Learning Objective</span>**

The empirical risk minimization principle selects:

$$
f^\star = \arg \min_{f \in \mathcal{H}} \hat{R}(f).
$$

For linear regression with squared loss, this yields:

$$
\mathbf{w}^\star = \left( \mathbf{X} \mathbf{X}^\top \right)^{-1} \mathbf{X} \mathbf{v},
$$

assuming $\mathbf{X} \mathbf{X}^\top$ is invertible.

For the one-dimensional threshold classifier:

$$
b^\star = \arg \min_{b \in \mathbb{R}} \frac{1}{N} \sum_{n=1}^N \mathcal{L} \left( \mathrm{sign}(x_n - b), v_n \right),
$$

which approximates the minimizer of the exact risk:

$$
R(f) = \Pr \left\{ \mathrm{sign}(x - b) \neq v \right\}.
$$
