# Mathematical Preliminaries

Before diving into machine learning models, it's important to define the mathematical setting and notation used throughout.

<br>

**<span style="font-size:1.5em;">Dataset Notation</span>**

We denote the dataset by:

$$
\mathbb{D} = \{ (x_n, y_n) : n = 1, \dots, N \}
$$

- $x_n$: feature vector or input sample  
- $y_n$: label or target corresponding to $x_n$  
- $N$: number of training examples  

Each input $x_n \in \mathbb{R}^d$ is a $d$-dimensional real-valued vector.

<br>

**<span style="font-size:1.5em;">Model Function</span>**

A machine learning model is a function:

$$
f: \mathbb{R}^d \rightarrow \hat{y}
$$

where:

- $\hat{y}$ is the output space (e.g., $\mathbb{R}$ for regression, a finite set of classes for classification)  
- The model is parameterized by $\theta$, so we often write $f(x; \theta)$

<br>

**<span style="font-size:1.5em;">Loss Function</span>**

To measure the model's prediction quality, we use a loss function:

$$
\mathcal{L}(y,\hat{y})
$$

Examples:

- Mean Squared Error (MSE): $\mathcal{L}(y, \hat{y}) = (y - \hat{y})^2$  
- Cross-Entropy Loss: used in classification

<br>

**<span style="font-size:1.5em;">Empirical Risk Minimization</span>**

Training the model means minimizing the total loss over the dataset:

$$
\hat{\theta} = \arg\min_{\theta} \frac{1}{N} \sum_{n=1}^N \mathcal{L}(y_n, f(x_n; \theta))
$$

This principle is known as **Empirical Risk Minimization (ERM)**.

<br>

**<span style="font-size:1.5em;">Gradient-Based Optimization</span>**

To minimize the loss, we often use gradient-based methods such as Stochastic Gradient Descent (SGD):

$$
\theta \leftarrow \theta - \eta \cdot \nabla_\theta \mathcal{L}(y_n, f(x_n; \theta))
$$

where $\eta$ is the learning rate.

<br>


