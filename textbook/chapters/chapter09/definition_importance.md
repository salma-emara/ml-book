# Definition and Importance

Once training is complete, a model is deployed for inference.  
The central question becomes:

> **Will the model perform well on unseen samples?**

This ability is referred to as **generalization**.

---

### Generalization
- **Definition:** The ability of a trained model to perform well on **unseen data** drawn from the same distribution as the training data.  
- Unseen data typically comes from the same underlying process, but its labels are unknown during training.

---

### Measuring Generalization
To assess generalization in practice:
- We evaluate the model on **samples not used during training**.  
- Common approach: split the available dataset into **training**, **validation**, and **test** sets.

---

Generalization is the cornerstone of machine learning:  
without it, models would only memorize data rather than learning patterns useful for future predictions.
