# 5.2 Linear Classification

**<span style="font-size:1.5em;">Problem Formulation</span>**

We observe a labeled dataset

$$
\mathcal{D} = \left\{ \left( \mathbf{x}_n , \ \text{class}_n \right) : n = 1, \ldots, N \right\},
$$

and seek a mapping

$$
f : \mathcal{X} \to \mathcal{V},
$$

where

$$
\mathcal{V} = \{ \text{class}_1, \ldots, \text{class}_K \}.
$$

---

**<span style="font-size:1.5em;">Threshold-Based Classifier</span>**

For the one-dimensional case, consider the hypothesis set

$$
\mathcal{H} = \left\{ f(x) = \mathrm{sign}(x - b) \in \{-1,1\} \right\}.
$$

This can be interpreted as

$$
y =
\begin{cases}
\text{cat}, & f(x) = -1, \\
\text{dog}, & f(x) = 1.
\end{cases}
$$

This assumes that the two classes are separable by thresholding on the scalar feature $x$.

---

**<span style="font-size:1.5em;">Example Dataset</span>**

Consider the dataset

$$
\mathcal{D} =
\{
(5.5,\text{cat}), \ (4.5,\text{cat}), \ (12.5,\text{dog}), \ (9.5,\text{dog}), \ (7.5,\text{cat})
\}.
$$

The objective is to determine the threshold $b$ that minimizes the empirical misclassification risk.

---

**<span style="font-size:1.5em;">Loss Function and Empirical Risk</span>**

We use the $0$–$1$ loss:

$$
\mathcal{L}(y, v) =
\begin{cases}
1, & y \neq v, \\
0, & y = v.
\end{cases}
$$

The empirical risk is then

$$
\hat{R}(f) = \frac{1}{N} \sum_{n=1}^N \mathcal{L} \left( f(x_n), v_n \right).
$$

---

**<span style="font-size:1.5em;">Exact Risk</span>**

If $(x, v) \sim P(x, v)$, the exact risk of the threshold classifier is

$$
R(f) = \mathbb{E}_{x, v} \left[ \mathcal{L} \left( \mathrm{sign}(x - b), v \right) \right]
= \Pr \left\{ \mathrm{sign}(x - b) \neq v \right\}.
$$

---


**<span style="font-size:1.5em;">Learning Objective</span>**

The empirical risk minimization principle selects

$$
f^\star = \arg \min_{f \in \mathcal{H}} \hat{R}(f),
$$

where, for the threshold classifier, this reduces to

$$
b^\star = \arg \min_{b \in \mathbb{R}} \frac{1}{N} \sum_{n=1}^N \mathcal{L} \left( \mathrm{sign}(x_n - b), v_n \right).
$$
