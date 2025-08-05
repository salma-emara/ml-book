# PCA: Basic Concepts

**<span style="font-size:1.5em;">What Is PCA?</span>**

Principal Component Analysis (PCA) is a **linear transformation** technique that projects data onto a new set of orthogonal axes (principal components) that capture the most variance in the data.

PCA identifies the directions along which the data varies the most and discards those with minimal variation (assumed to be noise).

---

**<span style="font-size:1.5em;">Why Maximize Variance?</span>**

Variance is a natural proxy for information:

- Low variance dimensions likely contain **noise**
- High variance dimensions contain **signal**

Hence, PCA seeks directions that preserve **maximum variance** when projecting data to lower dimensions.

---

**<span style="font-size:1.5em;">Data Projection</span>**

Let $\mathbf{x} \in \mathbb{R}^d$ be a data point, and let $\mathbf{w} \in \mathbb{R}^d$ be a unit vector.

The projection of $\mathbf{x}$ onto $\mathbf{w}$ is:

$$
\hat{x} = \mathbf{w}^\top \mathbf{x}
$$

The variance of the projected data (over all points $\mathbf{x}_1, \dots, \mathbf{x}_N$) is:

$$
\mathrm{Var}(\hat{x}) = \mathbf{w}^\top \mathbf{S} \mathbf{w}
$$

where $\mathbf{S}$ is the empirical covariance matrix:

$$
\mathbf{S} = \frac{1}{N} \sum_{n=1}^N (\mathbf{x}_n - \bar{\mathbf{x}})(\mathbf{x}_n - \bar{\mathbf{x}})^\top
$$

---

**<span style="font-size:1.5em;">Optimization Objective</span>**

PCA solves the following problem:

$$
\max_{\mathbf{w} \in \mathbb{R}^d, \, \|\mathbf{w}\| = 1} \quad \mathbf{w}^\top \mathbf{S} \mathbf{w}
$$

This is a **Rayleigh quotient**, and its solution is given by the **eigenvector** of $\mathbf{S}$ corresponding to the **largest eigenvalue**.

The first principal component is the direction of **maximum variance**.

Subsequent components are chosen to be:

- Orthogonal to previous ones
- Maximize residual variance

---

**<span style="font-size:1.5em;">Geometric Intuition</span>**

PCA finds a rotated coordinate system in which:

- The **first axis** captures the largest spread of data
- The **second axis** captures the next largest spread, orthogonal to the first
- And so on...

Projecting data onto the first few principal components gives a **compressed**, **denoised**, and often more **interpretable** representation.

---

**<span style="font-size:1.5em;">Centered Data Assumption</span>**

PCA assumes that data has been **centered**:

$$
\bar{\mathbf{x}} = \frac{1}{N} \sum_{n=1}^N \mathbf{x}_n, \quad \text{then subtract } \bar{\mathbf{x}} \text{ from all samples}
$$

This ensures that the first principal component corresponds to the direction of maximum variance **around the mean**, rather than being biased by the location of the data.

