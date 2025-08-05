# PCA: Applications

**<span style="font-size:1.5em;">Why Use PCA?</span>**

PCA is a widely used technique due to its **simplicity**, **interpretability**, and **effectiveness** in various settings.

---

**<span style="font-size:1.5em;">1. Dimensionality Reduction</span>**

Reduce data from $d$ dimensions to $k \ll d$:

- Lower memory and computation cost
- Less noise and redundancy
- Useful as a preprocessing step before classification or clustering

---

**<span style="font-size:1.5em;">2. Visualization</span>**

Project high-dimensional data to 2D or 3D for visual analysis:

- Cluster structure
- Class separation
- Outlier detection

Use cases:

- Plotting document embeddings
- Visualizing gene expression profiles
- Monitoring sensor arrays

---

**<span style="font-size:1.5em;">3. Denoising</span>**

Noise often lies in low-variance components.

Procedure:

1. Project data onto top $k$ components (signal)
2. Discard small-variance components (assumed noise)
3. Reconstruct data from top components

This is known as **low-rank approximation**.

---

**<span style="font-size:1.5em;">4. Compression</span>**

Store only projections $\mathbf{z}_n \in \mathbb{R}^k$ and the PCA basis $\mathbf{W}_k$.

Original data can be approximately reconstructed:

$$
\hat{\mathbf{x}}_n = \mathbf{W}_k \mathbf{z}_n + \bar{\mathbf{x}}
$$

This can dramatically reduce storage cost for image, audio, or sensor data.

---

**<span style="font-size:1.5em;">5. Feature Engineering</span>**

- PCA can create **uncorrelated features** (principal components)
- Sometimes used to **whiten** data (rescale so all variances = 1)
- Can help in **regression**, **classification**, and **anomaly detection**

---

**<span style="font-size:1.5em;">Limitations of PCA</span>**

- **Linear**: cannot model curved manifolds
- **Variance-based**: assumes high variance = important
- **Global**: does not focus on local structure

For complex patterns, nonlinear methods like **t-SNE**, **UMAP**, or **autoencoders** may be preferred.

