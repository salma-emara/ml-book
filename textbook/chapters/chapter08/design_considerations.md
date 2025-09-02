# Training Neural Networks - Design Considerations

**<span style="font-size:1.5em;">Design Considerations</span>**

Designing neural networks involves several practical aspects that directly affect training stability, convergence speed, and generalization.

---

**<span style="font-size:1.5em;">Initialization</span>**

Poor initialization may lead to **slow convergence** or getting trapped in poor local minima.

- **Xavier/Glorot initialization** is suitable for tanh activations.  
- **He initialization** is recommended for ReLU activations.  
- Goal: maintain balanced variance of activations across layers.

---

**<span style="font-size:1.5em;">Learning Rate</span>**

The learning rate $\eta$ critically affects optimization:

- Too large $\eta \;\;\Rightarrow$ divergence.  
- Too small $\eta \;\;\Rightarrow$ very slow progress.  

**Practical strategy:** use learning rate schedules or adaptive methods (e.g., exponential decay, step decay, Adam).

---

**<span style="font-size:1.5em;">Batch Size</span>**

- **Small batches:** produce noisy gradient estimates, often aiding generalization.  
- **Large batches:** give smoother updates but may converge to sharp minima.  
- Common practice: mini-batch training (batch sizes 32–256).

---

**<span style="font-size:1.5em;">Overfitting and Regularization</span>**

To prevent overfitting, several techniques are applied:

- **$L_2$ regularization (weight decay):**

$$
\hat R_\lambda(\mathbf{w}) = \hat R(\mathbf{w}) + \lambda \|\mathbf{w}\|^2
$$

- **Dropout:** randomly zeros out activations during training.  
- **Early stopping:** halt training when validation performance stops improving.

---

**<span style="font-size:1.5em;">Data Preprocessing</span>**

Normalization of features improves optimization stability:

$$
x_j \;\leftarrow\; \frac{x_j - \mu_j}{\sigma_j}
$$

- Ensures features have comparable scales.  
- Outliers should be handled (e.g., clipping, normalization).  

---

**<span style="font-size:1.5em;">Practical Tips</span>**

1. Start with a moderately high learning rate, then reduce it.  
2. Always monitor training vs. validation error curves.  
3. Use cross-validation when dataset size is limited.  
4. Visualize loss surfaces and calibration plots for better diagnostics.

