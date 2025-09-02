# Training Neural Networks - Batch Normalization

**<span style="font-size:1.5em;">Batch Normalization</span>**

Training deep networks can be unstable because intermediate activations may vary in scale across layers.  
**Batch Normalization (BN)** addresses this by normalizing layer activations during training.

---

**<span style="font-size:1.5em;">Motivation</span>**

- Without normalization, deeper layers may see highly variable distributions ("internal covariate shift").  
- BN stabilizes learning and often accelerates convergence.  
- It also helps regularize the model, reducing overfitting.

---

**<span style="font-size:1.5em;">Normalization Step</span>**

Given activations $\{x_1, x_2, \ldots, x_m\}$ in a mini-batch:

1. Compute the batch mean:
   $$
   \mu_B = \frac{1}{m}\sum_{i=1}^m x_i
   $$

2. Compute the batch variance:
   $$
   \sigma_B^2 = \frac{1}{m}\sum_{i=1}^m (x_i - \mu_B)^2
   $$

3. Normalize:
   $$
   \hat{x}_i = \frac{x_i - \mu_B}{\sqrt{\sigma_B^2 + \epsilon}}
   $$

---

**<span style="font-size:1.5em;">Scaling and Shifting</span>**

BN introduces two learnable parameters, $\gamma$ (scale) and $\beta$ (shift), so the final output is

$$
y_i = \gamma \hat{x}_i + \beta
$$

This allows the network to **recover the original distribution** if needed, while benefiting from normalization during training.

---

**<span style="font-size:1.5em;">Practical Notes</span>**

- BN is typically applied **before activation functions** in fully-connected and convolutional networks.  
- At test time, running estimates of $\mu_B$ and $\sigma_B^2$ are used instead of batch statistics.  
- BN can act as a **form of regularization**, sometimes reducing the need for dropout.  

