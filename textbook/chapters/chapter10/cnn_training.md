# Training Convolutional Neural Networks

Training a CNN follows the same principles as any neural network:  
forward pass → loss computation → backward pass (backpropagation) → parameter updates.

---

**<span style="font-size:1.5em;">Forward Pass</span>**

- Input is passed through **convolutional layers**, **ReLU**, **pooling**, etc.  
- Produces **feature maps** and final predictions (via softmax or sigmoid layers).  
- Output is compared to ground truth using a **loss function** (e.g., cross-entropy).

---

**<span style="font-size:1.5em;">Backward Pass: Gradients</span>**

- Compute gradient of loss with respect to output  
- Apply **backpropagation** to compute gradients for filters, weights, and biases  
- Gradients flow through convolutions, pooling, and activations

Frameworks like PyTorch and TensorFlow handle gradient calculations automatically.

---

**<span style="font-size:1.5em;">Mathematics of Backpropagation in CNNs</span>**

Backpropagation in CNNs involves computing gradients for:

- **Convolutional filters** $W$  
- **Bias terms** $b$  
- **Input feature maps** $X$

Let:

- $X \in \mathbb{R}^{H \times W}$: input feature map  
- $W \in \mathbb{R}^{k \times k}$: filter  
- $Y = X * W + b$: output feature map

Then:

1. **Gradient w.r.t. filter $W$:**

$$
\frac{\partial \mathcal{L}}{\partial W} = X * \frac{\partial \mathcal{L}}{\partial Y}
$$

2. **Gradient w.r.t. bias $b$:**

$$
\frac{\partial \mathcal{L}}{\partial b} = \sum_{i,j} \frac{\partial \mathcal{L}}{\partial Y_{i,j}}
$$

3. **Gradient w.r.t. input $X$ (for previous layers):**

$$
\frac{\partial \mathcal{L}}{\partial X} = \frac{\partial \mathcal{L}}{\partial Y} * \text{rot180}(W)
$$

Here, $\text{rot180}(W)$ is the 180° rotated filter, used in true convolution.

---

**Example: 1D Case**

For $y_i = \sum_j x_{i+j} \cdot w_j$, we have:

$$
\frac{\partial \mathcal{L}}{\partial w_j} = \sum_i \frac{\partial \mathcal{L}}{\partial y_i} \cdot x_{i+j}
$$

This logic extends naturally to 2D with padding and stride.

---

**<span style="font-size:1.5em;">Backprop Through ReLU and Pooling</span>**

- **ReLU:**

$$
\frac{\partial \mathcal{L}}{\partial x} = \begin{cases}
\frac{\partial \mathcal{L}}{\partial y} & \text{if } x > 0 \\
0 & \text{otherwise}
\end{cases}
$$

- **Max Pooling:** gradients flow only through the maximum-valued input in each window.

---

**<span style="font-size:1.5em;">Parameter Update</span>**

After computing gradients, use an optimizer like SGD or Adam:

$$
\theta \leftarrow \theta - \eta \cdot \frac{\partial \mathcal{L}}{\partial \theta}
$$

- $\theta$: weights or biases  
- $\eta$: learning rate  
- $\mathcal{L}$: loss function

---

**<span style="font-size:1.5em;">Training Tips</span>**

- Normalize inputs (e.g., zero mean, unit variance)  
- Use mini-batches for stability and speed  
- Apply **data augmentation** to improve generalization  
- Monitor validation loss to prevent overfitting

---

**<span style="font-size:1.5em;">Regularization Techniques</span>**

- **Dropout**  
- **Weight decay** (L2 norm)  
- **Early stopping**  
- **Batch normalization**

