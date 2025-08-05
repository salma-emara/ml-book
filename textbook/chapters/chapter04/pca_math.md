# PCA: Mathematical Derivation

**<span style="font-size:1.5em;">Goal</span>**

We want to find the **best $k$-dimensional subspace** that preserves the **maximum variance** of a dataset:

$$
\mathcal{D} = \{ \mathbf{x}_1, \dots, \mathbf{x}_N \}, \quad \mathbf{x}_n \in \mathbb{R}^d
$$

Assume the data is **centered**:  

$$
\bar{\mathbf{x}} = \frac{1}{N} \sum_{n=1}^N \mathbf{x}_n = \mathbf{0}
$$

Let $\mathbf{S}$ be the sample covariance matrix:

$$
\mathbf{S} = \frac{1}{N} \sum_{n=1}^N \mathbf{x}_n \mathbf{x}_n^\top
$$

We want to find a **projection direction** $\mathbf{w} \in \mathbb{R}^d$ such that the projected data:

$$
\hat{x}_n = \mathbf{w}^\top \mathbf{x}_n
$$

has **maximum variance** over all data points.

---

**<span style="font-size:1.5em;">Variance of Projected Data</span>**

The variance of the projection is:

$$
\mathrm{Var}(\hat{x}) = \frac{1}{N} \sum_{n=1}^N (\mathbf{w}^\top \mathbf{x}_n)^2 = \mathbf{w}^\top \mathbf{S} \mathbf{w}
$$

We maximize this under the constraint that $\|\mathbf{w}\| = 1$:

$$
\max_{\|\mathbf{w}\| = 1} \mathbf{w}^\top \mathbf{S} \mathbf{w}
$$

This is a **constrained optimization problem**.

---

**<span style="font-size:1.5em;">Lagrangian Formulation</span>**

Let $\lambda$ be a Lagrange multiplier. Define:

$$
\mathcal{L}(\mathbf{w}, \lambda) = \mathbf{w}^\top \mathbf{S} \mathbf{w} - \lambda (\mathbf{w}^\top \mathbf{w} - 1)
$$

Take gradient with respect to $\mathbf{w}$ and set to zero:

$$
\nabla_{\mathbf{w}} \mathcal{L} = 2 \mathbf{S} \mathbf{w} - 2 \lambda \mathbf{w} = 0 \\
\Rightarrow \mathbf{S} \mathbf{w} = \lambda \mathbf{w}
$$

So $\mathbf{w}$ must be an **eigenvector** of $\mathbf{S}$ and $\lambda$ the corresponding **eigenvalue**.

To maximize variance, choose the eigenvector with the **largest eigenvalue**.

---

**<span style="font-size:1.5em;">Top $k$ Principal Components</span>**

Let $\mathbf{w}_1, \dots, \mathbf{w}_k$ be the eigenvectors corresponding to the $k$ largest eigenvalues $\lambda_1 \geq \lambda_2 \geq \dots \geq \lambda_k$.

The projection matrix is:

$$
\mathbf{W} = [\mathbf{w}_1, \dots, \mathbf{w}_k] \in \mathbb{R}^{d \times k}
$$

Projected data:

$$
\mathbf{z}_n = \mathbf{W}^\top \mathbf{x}_n \in \mathbb{R}^k
$$

Optional reconstruction:

$$
\hat{\mathbf{x}}_n = \mathbf{W} \mathbf{z}_n = \mathbf{W} \mathbf{W}^\top \mathbf{x}_n
$$

---

**<span style="font-size:1.5em;">PCA via SVD</span>**

Let $\mathbf{X} \in \mathbb{R}^{N \times d}$ be the centered data matrix (rows are data points).

Compute the **Singular Value Decomposition (SVD)**:

$$
\mathbf{X} = \mathbf{U} \mathbf{\Sigma} \mathbf{V}^\top
$$

- $\mathbf{U}$: left singular vectors (not used in PCA)
- $\mathbf{\Sigma}$: diagonal matrix of singular values
- $\mathbf{V}$: right singular vectors = **principal components**

The first $k$ columns of $\mathbf{V}$ give the top $k$ PCA directions.

Note:

$$
\mathbf{S} = \frac{1}{N} \mathbf{X}^\top \mathbf{X}
$$

So $\mathbf{S}$ and $\mathbf{X}$ share the same right singular vectors as eigenvectors.

---

**<span style="font-size:1.5em;">Summary</span>**

- PCA finds orthogonal directions of **maximum variance**
- Solve by **eigen-decomposition** of covariance or **SVD**
- Retain top $k$ directions for dimensionality reduction
- Projection is **linear**, but captures nonlinear patterns if data is shaped that way


