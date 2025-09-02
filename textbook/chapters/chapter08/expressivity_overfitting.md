# Training Neural Networks - Expressivity and Overfitting

**<span style="font-size:1.5em;">Expressivity and Overfitting</span>**

Neural networks are powerful function approximators, but their expressivity comes with challenges in controlling complexity and avoiding overfitting.

---

**<span style="font-size:1.5em;">Expressivity of Neural Networks</span>**

- Universal Approximation Theorem:  
  A feedforward neural network with at least one hidden layer and nonlinear activations can approximate **any continuous function** on compact domains, given sufficient hidden units.  

- Deeper architectures can represent complex functions more efficiently than shallow ones.  
- However, increased depth and width expand the hypothesis space, raising the risk of overfitting.

---

**<span style="font-size:1.5em;">Overfitting Phenomenon</span>**

- **Definition:** The model fits the training data very well but fails to generalize to unseen data.  
- **Symptoms:**  
  - Training error $\downarrow$ while validation error $\uparrow$.  
  - Model memorizes noise and outliers.  

<div style="text-align: center; background-color: white; padding: 10px;">
  <img src="../../_static/nn6.svg" alt="Support Vectors"/>
</div>

---

**<span style="font-size:1.5em;">Bias–Variance Trade-Off</span>**

- **High bias (underfitting):** Model too simple, poor training accuracy.  
- **High variance (overfitting):** Model too complex, poor generalization.  
- Goal: find balance between bias and variance via architecture and regularization.

<div style="text-align: center; background-color: white; padding: 10px;">
  <img src="../../_static/nn5.svg" alt="Support Vectors"/>
</div>

---

**<span style="font-size:1.5em;">Strategies to Mitigate Overfitting</span>**

- **Regularization:** $L_1$, $L_2$, weight decay.  
- **Dropout:** Randomly deactivate neurons during training.  
- **Early stopping:** Stop when validation error starts increasing.  
- **Data augmentation:** Enrich dataset with transformations.  
- **Cross-validation:** Ensure robustness of hyperparameter choices.  

