# 5.3 Geometric Interpretation

**<span style="font-size:1.5em;">Linear Regression</span>**

A linear regression model in $\mathbb{R}^d$

$$
f(\mathbf{x}) = \mathbf{w}^\top \mathbf{x}
$$

defines a hyperplane in the feature space. The learning algorithm seeks the hyperplane that minimizes the average squared difference between the predicted values and the true labels.

In the one-dimensional case with hypothesis $f(x) = w x$, the model reduces to fitting a straight line through the origin. For the dataset

$$
\mathcal{D} = \{ (\text{weight}, \text{price}) = (4,2),\ (5,1.5),\ (4.8,3),\ (6,4) \},
$$

the empirical risk is

$$
\hat{R}(w) = \frac{1}{4} \left[ (4w - 2)^2 + (5w - 1.5)^2 + (4.8w - 3)^2 + (6w - 4)^2 \right],
$$

and minimization yields

$$
f^\star(x) = 0.53\,x.
$$

---

**<span style="font-size:1.5em;">Linear Classification</span>**

In one dimension, a threshold-based classifier

$$
f(x) = \mathrm{sign}(x - b)
$$

splits the real line into two regions with a decision boundary at $x = b$:

- For $x < b$, $f(x) = -1$ (e.g., "cat")
- For $x > b$, $f(x) = 1$ (e.g., "dog")

In $\mathbb{R}^d$, a linear classifier of the form

$$
f(\mathbf{x}) = \mathrm{sign}(\mathbf{w}^\top \mathbf{x} + b)
$$

defines a decision hyperplane

$$
\{ \mathbf{x} : \mathbf{w}^\top \mathbf{x} + b = 0 \},
$$

which separates the space into two half-spaces corresponding to the two classes.
