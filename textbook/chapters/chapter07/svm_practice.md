# Support Vector Machines in Practice

**<span style="font-size:1.5em;">Choosing a Kernel</span>**

- The kernel function $K(\mathbf{x}_m,\mathbf{x}_n)$ defines the feature space implicitly.  
- Choosing a good kernel is **critical** for performance, but often problem-dependent.  
- Common kernels:  
  - **Linear** (default for linearly separable data).  
  - **Polynomial** of degree $p$:  
    $$
    K(\mathbf{x}_n,\mathbf{x}_m) = (\mathbf{x}_n^\top \mathbf{x}_m + c)^p.
    $$  
  - **Gaussian (RBF)** kernel:  
    $$
    K(\mathbf{x}_n,\mathbf{x}_m) 
    = \exp\!\left(-\tfrac{\|\mathbf{x}_n - \mathbf{x}_m\|^2}{\sigma}\right).
    $$

---

**<span style="font-size:1.5em;">Kernel Interpretations</span>**

- Polynomial kernel $\to$ polynomial feature embeddings.  
- Gaussian kernel $\to$ infinite-dimensional embeddings (via Taylor expansion).  
- Each kernel corresponds to a choice of **feature representation**.

---

**<span style="font-size:1.5em;">Representation Learning</span>**

- Predefined kernels are a form of **feature engineering**.  
- By fixing $K$, we implicitly fix the embedding $\varphi(\mathbf{x})$.  
- Alternative: **learn the kernel** from data.  

Parameterize the kernel:

$$
K_\theta(\mathbf{x}_m,\mathbf{x}_n)
$$

and train jointly with the classifier:

$$
\min_{\mathbf{w},\,\theta}\ \hat{R}(\mathbf{w}, \theta).
$$

---

**<span style="font-size:1.5em;">Example: Gaussian Kernel with Learned Width</span>**

Instead of fixing $\sigma$, optimize it along with the SVM parameters:

$$
K_\sigma(\mathbf{x}_m,\mathbf{x}_n) 
= \exp\!\left(-\frac{\|\mathbf{x}_m - \mathbf{x}_n\|^2}{\sigma}\right).
$$

---

**<span style="font-size:1.5em;">Neural Networks as Kernels</span>**

Neural networks can act as **learned feature maps**:

$$
\varphi_\theta(\mathbf{x}) \quad \Rightarrow \quad
K_\theta(\mathbf{x}_m,\mathbf{x}_n) 
= \varphi_\theta(\mathbf{x}_m)^\top \varphi_\theta(\mathbf{x}_n).
$$

This connects SVMs to modern **deep representation learning**, where data-driven features replace hand-crafted kernels.

---

**<span style="font-size:1.5em;">Practical Notes</span>**

- SVMs remain highly competitive on **small to medium datasets**.  
- They scale poorly with extremely large $N$ (due to quadratic programming).  
- Kernel choice and regularization parameters ($C$, $\sigma$, polynomial degree $p$) are typically tuned by **cross-validation**.  
- In high dimensions, SVMs with RBF kernels often perform well with minimal feature engineering.  

