# Calibration and Decision Boundaries

**<span style="font-size:1.5em;">Decision Boundaries</span>**

A classifier partitions the input space into regions associated with each class.  
The separating surfaces are called **decision boundaries**.

For linear classifiers:

$$
\hat y(\mathbf{x}) = \text{sign}(\mathbf{w}^\top \mathbf{x} + b).
$$

The boundary corresponds to:

$$
\mathbf{w}^\top \mathbf{x} + b = 0.
$$

---

**<span style="font-size:1.5em;">Geometric View</span>**

- The vector $\mathbf{w}$ is orthogonal to the boundary.  
- The bias $b$ shifts the boundary.  
- Scaling $(\mathbf{w}, b)$ leaves the boundary unchanged.

---

**<span style="font-size:1.5em;">Probabilistic View</span>**

In probabilistic models (e.g., logistic regression):

$$
p(y=1 \mid \mathbf{x}) = \sigma(\mathbf{w}^\top \mathbf{x} + b),
$$

with decision boundary at $p(y=1 \mid \mathbf{x}) = 0.5$.

---

**<span style="font-size:1.5em;">Calibration</span>**

Calibration ensures that predicted probabilities match true frequencies:  
if the model outputs 0.8, then roughly 80% of such predictions should be correct.

Poor calibration → overconfident or underconfident predictions.  
Methods such as **temperature scaling** adjust logits before applying softmax.

---

**<span style="font-size:1.5em;">Summary</span>**

Decision boundaries describe *where* predictions change; calibration describes *how confident* predictions should be.  
Both are essential for building trustworthy classifiers.
