# Classification with Confidence

**<span style="font-size:1.5em;">Motivation</span>**

So far, we looked at minimizing empirical risk to find a classifier $f(\mathbf{x})$.  
But often, we want more than just a **label prediction**—we want a **measure of confidence** in the prediction.

---

**<span style="font-size:1.5em;">Probabilistic Interpretation</span>**

Suppose the classifier outputs probabilities

$$
p(y \mid \mathbf{x}; \mathbf{w}),
$$

where $y \in \{1, \dots, C\}$ is the class label.  
The predicted class is

$$
\hat{y}(\mathbf{x}) = \arg\max_{c} \; p(y=c \mid \mathbf{x}; \mathbf{w}).
$$

The **confidence** of this prediction is the probability assigned to that class:

$$
\text{Conf}(\mathbf{x}) = \max_{c} \; p(y=c \mid \mathbf{x}; \mathbf{w}).
$$

---

**<span style="font-size:1.5em;">Linear Classifiers with Softmax</span>**

For linear models, we can assign scores:

$$
s_c(\mathbf{x}) = \mathbf{w}_c^\top \mathbf{x},
$$

for each class $c=1,\dots,C$.  
To interpret these as probabilities, apply the **softmax** transformation:

$$
p(y=c \mid \mathbf{x}; \mathbf{W}) =
\frac{\exp(s_c(\mathbf{x}))}{\sum_{j=1}^C \exp(s_j(\mathbf{x}))}.
$$

This ensures:

1. $p(y=c \mid \mathbf{x}; \mathbf{W}) \geq 0$,  
2. $\sum_{c=1}^C p(y=c \mid \mathbf{x}; \mathbf{W}) = 1$.

---

**<span style="font-size:1.5em;">Training with Cross-Entropy</span>**

To train a probabilistic classifier, we minimize the **cross-entropy loss** (equivalently, maximize likelihood):

$$
\hat{R}(\mathbf{W}) = -\frac{1}{N}\sum_{i=1}^N \log p(y_i \mid \mathbf{x}_i; \mathbf{W}).
$$

Gradient-based updates are then applied as in gradient descent:

$$
\mathbf{W}^{t+1} = \mathbf{W}^t - \eta \,\nabla \hat R(\mathbf{W}^t).
$$

---

**<span style="font-size:1.5em;">Confidence and Decision Boundaries</span>**

- In **two-class logistic regression**, the probability is modeled as:

$$
p(y=1 \mid \mathbf{x}; \mathbf{w}) = \sigma(\mathbf{w}^\top \mathbf{x}),
$$

where $\sigma(z) = \tfrac{1}{1+\exp(-z)}$ is the logistic sigmoid.  

- Decision boundary: $\mathbf{w}^\top \mathbf{x} = 0$.  
- Confidence:  
  - near the boundary → $\approx 0.5$ (low confidence),  
  - far from the boundary → $\approx 0$ or $\approx 1$ (high confidence).

---

**<span style="font-size:1.5em;">Example: Logistic Regression Update</span>**

The negative log-likelihood loss is

$$
\hat{R}(\mathbf{w}) = -\frac{1}{N}\sum_{i=1}^N
\left[y_i \log \sigma(\mathbf{w}^\top \mathbf{x}_i) + (1-y_i)\log (1-\sigma(\mathbf{w}^\top \mathbf{x}_i))\right].
$$

Gradient:

$$
\nabla \hat{R}(\mathbf{w}) = -\frac{1}{N}\sum_{i=1}^N \big(y_i - \sigma(\mathbf{w}^\top \mathbf{x}_i)\big)\mathbf{x}_i.
$$

Update rule:

$$
\mathbf{w}^{t+1} = \mathbf{w}^t + \eta \,\frac{1}{N}\sum_{i=1}^N
\big(y_i - \sigma(\mathbf{w}^{t\top} \mathbf{x}_i)\big)\mathbf{x}_i.
$$

---

**<span style="font-size:1.5em;">Key Insights</span>**

- **Confidence** comes naturally from probabilistic classifiers (softmax / logistic regression).  
- High confidence = prediction far from decision boundary.  
- Low confidence = prediction near boundary.  
- **Cross-entropy loss** encourages correct predictions with high probability, not just correct labels.  

---

**<span style="font-size:1.5em;">Further Read</span>**

- Bishop, *PRML*, Chapter 4 — Logistic Regression  
- Goodfellow, *Deep Learning*, Chapter 6.2 — Softmax and Cross-Entropy  
- ESL, Chapter 4 — Classification with Probability Estimates
