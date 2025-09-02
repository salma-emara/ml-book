# Optimizers

**<span style="font-size:1.5em;">Motivation</span>**

Once gradients are computed via backpropagation, we need a strategy to update the network parameters.  
Optimizers define **how weights and biases are adjusted** to minimize the loss function.  

Formally, for parameters $\theta$, the generic update rule is:  

$$
\theta \leftarrow \theta - \eta \, \nabla_\theta \mathcal{L},
$$

where $\eta > 0$ is the **learning rate**.  

---

**<span style="font-size:1.5em;">Stochastic Gradient Descent (SGD)</span>**

The simplest and most widely used optimizer.  
Instead of the full dataset, SGD computes the gradient on **mini-batches**:  

$$
\theta \leftarrow \theta - \eta \, \nabla_\theta \mathcal{L}(\theta; \mathcal{B}),
$$

where $\mathcal{B}$ is a random mini-batch.  

- Efficient and scalable.  
- Sensitive to the choice of $\eta$.  
- May oscillate in ravines of the loss landscape.  

---

**<span style="font-size:1.5em;">Momentum</span>**

Momentum accelerates convergence by accumulating a moving average of past gradients:  

$$
v_t = \beta v_{t-1} + (1-\beta)\nabla_\theta \mathcal{L}(\theta_t),
$$

$$
\theta_{t+1} = \theta_t - \eta v_t,
$$

where $0 < \beta < 1$ controls the memory.  

---

**<span style="font-size:1.5em;">RMSProp</span>**

RMSProp scales learning rates by dividing gradients with a running average of squared gradients:  

$$
s_t = \rho s_{t-1} + (1-\rho)\big(\nabla_\theta \mathcal{L}(\theta_t)\big)^2,
$$

$$
\theta_{t+1} = \theta_t - \frac{\eta}{\sqrt{s_t + \epsilon}} \, \nabla_\theta \mathcal{L}(\theta_t),
$$

where $\rho$ is the decay factor and $\epsilon$ is a small constant for stability.  

---

**<span style="font-size:1.5em;">Adam (Adaptive Moment Estimation)</span>**

Adam combines **momentum** and **RMSProp**:  

- First moment estimate (mean of gradients):  

$$
m_t = \beta_1 m_{t-1} + (1-\beta_1)\nabla_\theta \mathcal{L}(\theta_t),
$$

- Second moment estimate (uncentered variance):  

$$
v_t = \beta_2 v_{t-1} + (1-\beta_2)\big(\nabla_\theta \mathcal{L}(\theta_t)\big)^2,
$$

- Bias-corrected estimates:  

$$
\hat{m}_t = \frac{m_t}{1-\beta_1^t}, 
\qquad 
\hat{v}_t = \frac{v_t}{1-\beta_2^t},
$$

- Update rule:  

$$
\theta_{t+1} = \theta_t - \frac{\eta}{\sqrt{\hat{v}_t} + \epsilon} \, \hat{m}_t.
$$


