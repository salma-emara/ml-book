# 5.1 Linear Regression

**<span style="font-size:1.5em;">Problem Formulation</span>**

Consider the labeled dataset

$$
\mathcal{D} = \left\{ \left( \mathbf{x}_n \in \mathbb{R}^d , \ v_n \in \mathbb{R} \right) : n = 1, \ldots, N \right\}.
$$

We restrict our attention to the class of linear models

$$
\mathcal{H} = \left\{ f(\mathbf{x}) = \mathbf{w}^\top \mathbf{x} \ \ \text{for all} \ \mathbf{w} \in \mathbb{R}^d \right\}.
$$

The optimal parameter vector is obtained by solving

$$
\mathbf{w}^\star = \arg \min_{\mathbf{w} \in \mathbb{R}^d} \frac{1}{N} \sum_{n=1}^N \mathcal{L} \left( \mathbf{w}^\top \mathbf{x}_n , v_n \right),
$$

where $\mathcal{L}$ is an appropriate loss function.

---

**<span style="font-size:1.5em;">Empirical Risk with Squared Loss</span>**

A common choice for regression is the squared loss

$$
\mathcal{L} \left( y_n , v_n \right) = \left( y_n - v_n \right)^2.
$$

The empirical risk is then expressed as

$$
\hat{R}(\mathbf{w}) = \frac{1}{N} \sum_{n=1}^N \left( \mathbf{w}^\top \mathbf{x}_n - v_n \right)^2.
$$

---

**<span style="font-size:1.5em;">Vectorized Formulation</span>**

Define the data matrix

$$
\mathbf{X} = \begin{bmatrix} \mathbf{x}_1 & \mathbf{x}_2 & \dots & \mathbf{x}_N \end{bmatrix},
$$

and note that

$$
\mathbf{w}^\top \mathbf{X} = \begin{bmatrix} \mathbf{w}^\top \mathbf{x}_1 & \dots & \mathbf{w}^\top \mathbf{x}_N \end{bmatrix} = \mathbf{y}^\top.
$$

The empirical risk becomes

$$
\hat{R}(\mathbf{w}) = \frac{1}{N} \left\| \mathbf{y} - \mathbf{v} \right\|^2 = \frac{1}{N} \left\| \mathbf{X}^\top \mathbf{w} - \mathbf{v} \right\|^2.
$$

---

**<span style="font-size:1.5em;">Empirical Risk Minimization</span>**

The optimization problem is therefore

$$
\mathbf{w}^\star = \arg \min_{\mathbf{w} \in \mathbb{R}^d} \frac{1}{N} \left\| \mathbf{X}^\top \mathbf{w} - \mathbf{v} \right\|^2.
$$

Since this objective is convex, the unique minimizer can be obtained by setting the gradient to zero:

$$
\nabla \hat{R} = \frac{2}{N} \left( \mathbf{X} \mathbf{X}^\top \mathbf{w} - \mathbf{X} \mathbf{v} \right) = \mathbf{0}.
$$

This yields the normal equations

$$
\mathbf{X} \mathbf{X}^\top \mathbf{w}^\star = \mathbf{X} \mathbf{v}.
$$

If $\det(\mathbf{X} \mathbf{X}^\top) \neq 0$, the solution is

$$
\mathbf{w}^\star = \left( \mathbf{X} \mathbf{X}^\top \right)^{-1} \mathbf{X} \mathbf{v} = \mathbf{X}^\dagger \mathbf{v},
$$

where $\mathbf{X}^\dagger$ is the Moore–Penrose pseudo-inverse of $\mathbf{X}$.

---

**<span style="font-size:1.5em;">Polynomial Regression Example</span>**

For a polynomial hypothesis of degree $P$,

$$
\mathcal{H} = \left\{ f(x) = w_0 + w_1 x + \dots + w_P x^P : w_0, \dots, w_P \in \mathbb{R} \right\},
$$

the target relation is approximated as

$$
v \approx f(x) = \sum_{i=1}^P w_i x^i.
$$

The learning problem becomes

$$
w_0^\star, \dots, w_P^\star = \arg \min_{w_0, \dots, w_P} \frac{1}{N} \sum_{n=1}^N \left( w_0 + w_1 x_n + \dots + w_P x_n^P - v_n \right)^2.
$$

---

**<span style="font-size:1.5em;">Line Fitting Example</span>**

Restricting to a linear hypothesis $f(x) = w x$ and dataset

$$
\mathcal{D} = \{ (\text{weight}, \text{price}) = (4,2), (5,1.5), (4.8,3), (6,4) \},
$$

the empirical risk is

$$
\hat{R}(w) = \frac{1}{4} \left[ (4w - 2)^2 + (5w - 1.5)^2 + (4.8w - 3)^2 + (6w - 4)^2 \right].
$$

Minimization yields

$$
f^\star(x) = w^\star x = 0.53 x.
$$

---

**<span style="font-size:1.5em;">Affine Models</span>**

An affine model includes a bias term:

$$
f(\mathbf{x}) = \mathbf{w}^\top \mathbf{x} + b.
$$

The hypothesis set is

$$
\mathcal{H} = \left\{ f(\mathbf{x}) = \mathbf{w}^\top \mathbf{x} + b : \mathbf{w} \in \mathbb{R}^d , b \in \mathbb{R} \right\}.
$$

The optimization problem becomes

$$
(\mathbf{w}^\star, b^\star) = \arg \min_{\mathbf{w} \in \mathbb{R}^d, b \in \mathbb{R}} \frac{1}{N} \sum_{n=1}^N \left( \mathbf{w}^\top \mathbf{x}_n + b - v_n \right)^2.
$$

By augmenting each input vector with a 1,

$$
\mathbf{X} = \begin{bmatrix} 1 & \dots & 1 \\ \mathbf{x}_1 & \dots & \mathbf{x}_N \end{bmatrix},
$$

the solution is

$$
\begin{bmatrix} b^\star \\ \mathbf{w}^\star \end{bmatrix} = \left( \mathbf{X} \mathbf{X}^\top \right)^{-1} \mathbf{X} \mathbf{v} = \mathbf{X}^\dagger \mathbf{v}.
$$

---


**<span style="font-size:1.5em;">Vector-Valued Outputs</span>**

For vector-valued outputs $\mathbf{v}_n \in \mathbb{R}^\ell$, the model becomes

$$
f(\mathbf{x}) = \mathbf{W}^\top \mathbf{x} + \mathbf{b},
$$

where $\mathbf{W} \in \mathbb{R}^{d \times \ell}$ and $\mathbf{b} \in \mathbb{R}^\ell$. The same derivation applies with the appropriate adjustments for matrix dimensions.

---

**<span style="font-size:1.5em;">Computational Complexity</span>**

Computing $\mathbf{X} \mathbf{X}^\top$ requires $\mathcal{O}(d^2 N)$ operations. Inversion of $\mathbf{X} \mathbf{X}^\top$ requires between $\mathcal{O}(d^{2.4})$ and $\mathcal{O}(d^3)$ operations. Multiplying the inverse by $\mathbf{X}$ costs $\mathcal{O}(d^2 N)$. Overall complexity is approximately $\mathcal{O}(d^3)$, which can be prohibitive when $d$ is large.
