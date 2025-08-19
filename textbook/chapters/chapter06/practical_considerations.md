# Practical Considerations in Training

**<span style="font-size:1.5em;">Initialization</span>**

- Poor initialization can slow convergence or trap training in poor local minima.
- Aim: maintain balanced variance across layers.

---

**<span style="font-size:1.5em;">Learning Rate</span>**

The step size $\eta$ is critical:

- Too large $\rightarrow$ divergence.  
- Too small $\rightarrow$ slow convergence or poor minima.  
- Practical solution: schedules (exponential decay, step decay) or adaptive optimizers (Adam, RMSprop).

---

**<span style="font-size:1.5em;">Batch Size</span>**

- **Small batches**: noisy gradients, often better generalization.  
- **Large batches**: smoother updates, risk of sharp minima.  
- Typical practice: moderate mini-batches (e.g., 32–256).

---

**<span style="font-size:1.5em;">Regularization</span>**

To prevent overfitting:

- **$L_2$ penalty (weight decay):**

$$
\hat R_\lambda(\mathbf{w}) = \hat R(\mathbf{w}) + \lambda \|\mathbf{w}\|^2.
$$

- **Dropout:** randomly zero activations.  
- **Early stopping:** stop training when validation error no longer decreases.

---

**<span style="font-size:1.5em;">Data Preprocessing</span>**

Normalize features for stable optimization:

$$
x_j \leftarrow \frac{x_j - \mu_j}{\sigma_j}.
$$

Also address outliers (clipping, normalization).

---

**<span style="font-size:1.5em;">Practical Guidelines</span>**

1. Begin with a relatively high learning rate, reduce as training progresses.  
2. Always compare training and validation performance.  
3. Use cross-validation for small datasets.  
4. Visualize losses and calibration when possible.

---

**<span style="font-size:1.5em;">Summary</span>**

Successful training depends not only on optimization algorithms but also on **initialization, learning rate schedules, batch size, and regularization**.  
Careful preprocessing and monitoring ensure models generalize reliably.
