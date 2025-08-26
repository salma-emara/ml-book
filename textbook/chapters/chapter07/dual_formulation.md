# Dual Formulation of the Support Vector Classifier

**<span style="font-size:1.5em;">Optimization with Inequality Constraints</span>**

We want to solve constrained optimization problems of the form:

$$
\min_{\mathbf{w}} f(\mathbf{w})
\quad \text{subject to} \quad g_n(\mathbf{w}) \le 0, \quad n=1,\ldots,N .
$$

---

**<span style="font-size:1.5em;">SVC as a Constrained Problem</span>**

For the Support Vector Classifier:

$$
f(\mathbf{w}) = \|\mathbf{w}\|^2, 
\qquad g_n(\mathbf{w}) = 1 - v_n \mathbf{w}^\top \mathbf{x}_n .
$$

Thus,

$$
\min_{\mathbf{w}} \|\mathbf{w}\|^2 
\quad \text{subject to} \quad v_n \mathbf{w}^\top \mathbf{x}_n \ge 1 .
$$

---

**<span style="font-size:1.5em;">Lagrangian Formulation</span>**

Introduce dual variables $\lambda_n \ge 0$ and form:

$$
\ell(\mathbf{w}, \boldsymbol{\lambda})
= \|\mathbf{w}\|^2 + \sum_{n=1}^N \lambda_n \big(1 - v_n \mathbf{w}^\top \mathbf{x}_n \big).
$$

---

**<span style="font-size:1.5em;">Key Property</span>**

- If $\mathbf{w}$ is feasible ($g_n(\mathbf{w}) \le 0$), then

$$
\max_{\boldsymbol{\lambda}\ge 0}\ \ell(\mathbf{w}, \boldsymbol{\lambda}) = f(\mathbf{w}).
$$

- If $\mathbf{w}$ is infeasible ($g_n(\mathbf{w}) > 0$ for some $n$), then

$$
\max_{\boldsymbol{\lambda}\ge 0}\ \ell(\mathbf{w}, \boldsymbol{\lambda}) = +\infty.
$$

Thus,

$$
\min_{\mathbf{w}} \max_{\boldsymbol{\lambda}\ge 0} \ell(\mathbf{w}, \boldsymbol{\lambda})
= \min_{\mathbf{w}} f(\mathbf{w}) \ \text{subject to } g_n(\mathbf{w}) \le 0.
$$

---

**<span style="font-size:1.5em;">Primal vs. Dual</span>**

- **Primal problem**

$$
P = \min_{\mathbf{w}} \max_{\boldsymbol{\lambda}\ge 0} \ell(\mathbf{w}, \boldsymbol{\lambda}).
$$

- **Dual problem**

$$
D = \max_{\boldsymbol{\lambda}\ge 0} \min_{\mathbf{w}} \ell(\mathbf{w}, \boldsymbol{\lambda}).
$$

Always $D \le P$.  
By **Slater’s conditions** (convexity + strict feasibility), we have **strong duality**: $D = P$.

---

**<span style="font-size:1.5em;">KKT Conditions</span>**

Optimal $(\mathbf{w}^\star, \boldsymbol{\lambda}^\star)$ must satisfy:

- Stationarity:  
  $$
  \nabla_{\mathbf{w}} \ell(\mathbf{w}^\star, \boldsymbol{\lambda}^\star) = \mathbf{0}.
  $$
- Primal feasibility: $g_n(\mathbf{w}^\star) \le 0$.  
- Dual feasibility: $\lambda_n^\star \ge 0$.  
- Complementary slackness:  
  $$
  \lambda_n^\star g_n(\mathbf{w}^\star) = 0.
  $$

---

**<span style="font-size:1.5em;">Examples</span>**

- *Paraboloid I:*  

$$
\min \ w_1^2 + w_2^2 \quad \text{subject to } w_1 \le 1.
$$

Solution: $\mathbf{w}^\star=(0,0)$, $\lambda^\star=0$ (constraint inactive).

- *Paraboloid II:*  

$$
\min \ w_1^2 + w_2^2 \quad \text{subject to } w_1 \le -1.
$$

Solution: $\mathbf{w}^\star=(-1,0)$, $\lambda^\star=2$ (constraint active).

---

**<span style="font-size:1.5em;">Back to SVC: Dual Problem</span>**

Primal:

$$
\min_{\mathbf{w}} \|\mathbf{w}\|^2
\quad \text{subject to } v_n \mathbf{w}^\top \mathbf{x}_n \ge 1.
$$

Dual Lagrangian:

$$
\ell(\mathbf{w}, \boldsymbol{\lambda})
= \|\mathbf{w}\|^2 + \sum_{n=1}^N \lambda_n \big(1 - v_n \mathbf{w}^\top \mathbf{x}_n \big).
$$

Stationarity:

$$
2\mathbf{w}^\star - \sum_{n=1}^N \lambda_n^\star v_n \mathbf{x}_n = \mathbf{0}
\quad \Rightarrow \quad
\mathbf{w}^\star = \tfrac{1}{2} \sum_{n=1}^N \lambda_n^\star v_n \mathbf{x}_n .
$$

---

**<span style="font-size:1.5em;">Dual Objective</span>**

Substitute $\mathbf{w}^\star$ into $\ell$:

$$
\ell(\mathbf{w}^\star, \boldsymbol{\lambda}) 
= \sum_{n=1}^N \lambda_n - \tfrac{1}{4}\sum_{n=1}^N\sum_{m=1}^N 
\lambda_n \lambda_m v_n v_m \, \mathbf{x}_n^\top \mathbf{x}_m .
$$

Thus the dual problem is:

$$
\max_{\boldsymbol{\lambda}\ge 0} \ 
\sum_{n=1}^N \lambda_n 
- \tfrac{1}{4}\sum_{n=1}^N\sum_{m=1}^N 
\lambda_n \lambda_m v_n v_m \,\mathbf{x}_n^\top \mathbf{x}_m .
$$

**Observation:** the solution depends only on **cross-correlations** $\mathbf{x}_n^\top \mathbf{x}_m$.

---

**<span style="font-size:1.5em;">Complementary Slackness</span>**

At optimum:

$$
\lambda_n^\star \big(1 - v_n \mathbf{w}^{\star\top} \mathbf{x}_n\big) = 0.
$$

- If $v_n \mathbf{w}^{\star\top}\mathbf{x}_n = 1$ (point on margin), then $\lambda_n^\star > 0$.  
- If $v_n \mathbf{w}^{\star\top}\mathbf{x}_n > 1$ (strictly inside), then $\lambda_n^\star = 0$.  

Thus **only support vectors** have nonzero $\lambda_n^\star$.

---

**<span style="font-size:1.5em;">Support Vector Solution</span>**

The classifier is:

$$
\mathbf{w}^\star = \sum_{n\in \mathcal{S}} \lambda_n^\star v_n \mathbf{x}_n,
$$

where $\mathcal{S}$ is the set of support vectors.  

For a new sample $\mathbf{x}$, prediction is:

$$
y = \mathrm{sign}\!\left(\mathbf{w}^{\star\top}\mathbf{x}\right)
= \mathrm{sign}\!\left(\sum_{n\in \mathcal{S}} \lambda_n^\star v_n \mathbf{x}_n^\top \mathbf{x}\right).
$$

