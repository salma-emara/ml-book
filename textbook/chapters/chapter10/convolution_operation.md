# The Convolution Operation

Convolution is the core operation in CNNs that enables feature extraction from structured inputs like images, signals, and sequences.  
It computes a weighted sum between a small filter (kernel) and local regions of the input.

---

**<span style="font-size:1.5em;">1D Convolution (Simplified)</span>**

Given a 1D input $x = [x_1, x_2, \dots, x_N]$ and a 1D filter $w = [w_1, w_2, \dots, w_k]$, the convolution output $y$ is:

$$
y_i = \sum_{j=1}^k x_{i + j - 1} \cdot w_j
$$

This "slides" the filter along the input, producing an output signal.

---

**<span style="font-size:1.5em;">2D Convolution (Common in Images)</span>**

For a 2D input (e.g., grayscale image) $X \in \mathbb{R}^{H \times W}$ and a 2D filter $W \in \mathbb{R}^{k \times k}$,  
the convolution output $Y$ at position $(i,j)$ is:

$$
Y_{i,j} = \sum_{u=1}^{k} \sum_{v=1}^{k} X_{i+u-1, j+v-1} \cdot W_{u,v}
$$

This produces a **feature map** that captures how well the input matches the filter at each location.

---

**<span style="font-size:1.5em;">Convolution vs. Cross-Correlation</span>**

In mathematics, **convolution** flips the filter before applying it.  
However, most deep learning frameworks (PyTorch, TensorFlow) use **cross-correlation**, which does not flip the kernel:

$$
Y_{i,j} = \sum_{u=1}^{k} \sum_{v=1}^{k} X_{i+u-1, j+v-1} \cdot W_{u,v}
$$

Despite the difference, the term "convolution" is used in practice.

---

**<span style="font-size:1.5em;">Multiple Channels</span>**

For color images or multi-channel signals, each filter spans all channels:  
If input has $C$ channels and filter size is $k \times k$, then filter weights form a 3D tensor $W \in \mathbb{R}^{C \times k \times k}$.

The convolution is computed as:

$$
Y_{i,j} = \sum_{c=1}^C \sum_{u=1}^{k} \sum_{v=1}^{k} X_{c, i+u-1, j+v-1} \cdot W_{c,u,v}
$$

---

**<span style="font-size:1.5em;">Why Convolution Works</span>**

- **Locality:** Detects features based on local context  
- **Translation Equivariance:** Output changes predictably when input shifts  
- **Efficiency:** Reuses the same small number of weights across all locations

These properties make convolution ideal for modeling structured patterns in space or time.

