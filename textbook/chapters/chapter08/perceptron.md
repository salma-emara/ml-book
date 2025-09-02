# Perceptron Model

**<span style="font-size:1.5em;">Introduction</span>**

The **perceptron** is one of the earliest models of artificial neurons, introduced by Rosenblatt (1958).  
It was designed as a simplified computational abstraction of a biological neuron and remains a **fundamental building block** in machine learning.  

---

**<span style="font-size:1.5em;">Mathematical Formulation</span>**

Given an input vector  

$$
\mathbf{x} = [x_1, x_2, \ldots, x_d]^\top,
$$  

the perceptron computes a **linear combination** with weights $\mathbf{w} = [w_1, w_2, \ldots, w_d]^\top$ and bias $b$:

$$
a = \sum_{i=1}^d w_i x_i + b = \mathbf{w}^\top \mathbf{x} + b.
$$  

The output is then passed through a **step activation function**:

$$
y =
\begin{cases}
1 & \text{if } a > 0, \\
0 & \text{otherwise}.
\end{cases}
$$

---

**<span style="font-size:1.5em;">Decision Boundary</span>**

The perceptron essentially defines a **linear classifier**:  

$$
\mathbf{w}^\top \mathbf{x} + b = 0
$$  

represents the **decision boundary** (a hyperplane in $\mathbb{R}^d$).  
- If a point lies on one side, the perceptron predicts class 1.  
- If on the other side, it predicts class 0.  
