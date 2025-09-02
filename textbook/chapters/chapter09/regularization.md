# Regularization Techniques

Regularization aims to improve **generalization** by preventing a model from overfitting the training data.  
This is achieved by adding constraints or modifying the training procedure.

---

### General Form
In regularization, the empirical risk is modified by adding a penalty term:

$$
\tilde{R}(\mathbf{w}) = \frac{1}{N} \sum_{n=1}^N \mathcal{L}(y_n, v_n) + \lambda \, \Pi(\mathbf{w})
$$

- $\Pi(\mathbf{w})$: regularization function (penalty on weights)  
- $\lambda$: regularization parameter, tuned via validation  

---

### ℓ<sub>p</sub>-Norm Regularization
A common penalty is the **ℓ<sub>p</sub>-norm**:

$$
\Pi(\mathbf{w}) = \|\mathbf{w}\|_p^p = \sum_i |w_i|^p
$$

- **ℓ₂-norm (Ridge / Tikhonov):** discourages large weights, widely used in regression.  
- **ℓ₁-norm (Lasso):** encourages sparsity, many weights become exactly zero.  

---

### Weight Decay
Using $\ell_2$-regularization with gradient descent yields **weight decay**:

$$
w_i \leftarrow (1 - \eta \lambda) w_i - \eta \, \frac{\partial}{\partial w_i} \hat{R}(\mathbf{w})
$$

- Weights shrink over time (“decay”), preventing them from growing too large.  
- Weight decay is widely applied in training neural networks.

---

### Stochastic Regularization: Dropout
Another approach is to introduce **stochasticity** during training.  

- In each forward pass, randomly drop some neurons:  

$$
y_i \leftarrow m_i y_i, \quad m_i \in \{0,1\}
$$

- Dropout prevents co-adaptation of neurons and improves generalization.  
- At test time, all neurons are used but scaled appropriately.

