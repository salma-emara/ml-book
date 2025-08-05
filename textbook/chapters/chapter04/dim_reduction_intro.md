# Introduction to Dimensionality Reduction

**<span style="font-size:1.5em;">Why Reduce Dimensions?</span>**

High-dimensional data is common in modern applications:

- Images: each pixel is a feature
- Text: word counts across large vocabularies
- Sensors: readings over time or across devices

However, high dimensions come with challenges:

- **Visualization**: Hard to plot data beyond 3D
- **Computational Cost**: Increases with the number of features
- **Overfitting**: More parameters lead to higher variance
- **Noise Sensitivity**: Irrelevant features add noise

The goal of dimensionality reduction is to simplify data by projecting it onto a lower-dimensional space, while preserving as much **relevant structure** as possible.

---

**<span style="font-size:1.5em;">What Is Dimensionality Reduction?</span>**

Dimensionality reduction refers to methods that map high-dimensional data $\mathbf{x} \in \mathbb{R}^d$ to lower-dimensional representations $\mathbf{z} \in \mathbb{R}^k$ where $k \ll d$:

$$
\mathbf{z} = f(\mathbf{x}) \quad \text{(encoding)}
$$

In some settings, we may also want to reconstruct the input:

$$
\hat{\mathbf{x}} = g(\mathbf{z}) \quad \text{(decoding)}
$$

Good dimensionality reduction techniques:

- Preserve the **variation** or **structure** in the data
- Reduce redundancy
- Enable **compression**, **denoising**, and **visualization**

---

**<span style="font-size:1.5em;">Linear vs Nonlinear Methods</span>**

In this chapter, we focus on **linear methods**, specifically **Principal Component Analysis (PCA)**.

PCA finds a linear subspace that captures the maximum variance in the data and is widely used due to its simplicity, interpretability, and closed-form solution.

Nonlinear methods (e.g., t-SNE, UMAP) are not discussed in this chapter.

---

**<span style="font-size:1.5em;">Key Idea of PCA</span>**

We assume that the data lies close to a lower-dimensional **linear subspace**. PCA finds:

- A set of **orthogonal directions** (principal components)
- Directions that **maximize the variance** of the data
- A projection of the data onto these components

This results in a low-dimensional summary that retains the most significant information in the data.
