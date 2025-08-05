# PCA: Algorithm and Implementation

**<span style="font-size:1.5em;">Step-by-Step PCA</span>**

Given a dataset of $N$ observations $\{ \mathbf{x}_1, \dots, \mathbf{x}_N \}$ in $\mathbb{R}^d$, we want to project it onto a $k$-dimensional subspace.

---

**<span style="font-size:1.5em;">Algorithm</span>**

1. **Center the Data**

   Compute the empirical mean:

   $$
   \bar{\mathbf{x}} = \frac{1}{N} \sum_{n=1}^N \mathbf{x}_n
   $$

   Center all data points:

   $$
   \tilde{\mathbf{x}}_n = \mathbf{x}_n - \bar{\mathbf{x}}
   $$

   Let $\mathbf{X} \in \mathbb{R}^{N \times d}$ be the centered data matrix.

---

2. **Compute Covariance Matrix**

   $$
   \mathbf{S} = \frac{1}{N} \mathbf{X}^\top \mathbf{X}
   $$

---

3. **Eigen-Decomposition**

   Solve for eigenvalues and eigenvectors:

   $$
   \mathbf{S} \mathbf{w}_i = \lambda_i \mathbf{w}_i
   $$

   Sort eigenvalues: $\lambda_1 \geq \lambda_2 \geq \dots \geq \lambda_d$

---

4. **Select Top $k$ Components**

   Form the projection matrix:

   $$
   \mathbf{W}_k = [\mathbf{w}_1, \dots, \mathbf{w}_k] \in \mathbb{R}^{d \times k}
   $$

---

5. **Project the Data**

   Project each centered sample:

   $$
   \mathbf{z}_n = \mathbf{W}_k^\top \tilde{\mathbf{x}}_n \in \mathbb{R}^k
   $$

   The collection $\{ \mathbf{z}_n \}$ is the reduced-dimensional representation.

---

**<span style="font-size:1.5em;">Optional Reconstruction</span>**

To approximately reconstruct from the projection:

$$
\hat{\mathbf{x}}_n = \mathbf{W}_k \mathbf{z}_n + \bar{\mathbf{x}} = \mathbf{W}_k \mathbf{W}_k^\top (\mathbf{x}_n - \bar{\mathbf{x}}) + \bar{\mathbf{x}}
$$

This gives a low-rank approximation of the original data.

---

**<span style="font-size:1.5em;">Interpretation</span>**

- The **first principal component** explains the most variance in the data.
- The **second** is orthogonal to the first and explains the next highest variance.
- Each new direction adds diminishing information.

---

**<span style="font-size:1.5em;">Notes</span>**

- PCA is **unsupervised**: it does not use labels
- It assumes **linear structure**
- SVD can be used instead of covariance matrix if $d$ is large or data is sparse

