# Capacity, Complexity, and Model Selection

### Generalization vs. Data
- Adding **more training data** reduces the chance of memorization and improves generalization.
- With limited data, models risk **overfitting**.
- With sufficient data, even complex models can generalize well.


---

### Generalization vs. Model Capacity
- **Capacity**: The ability of a model to fit diverse functions.
- Increasing parameters increases both:
  - **Learning ability** (can represent complex functions)
  - **Memorization ability** (risk of overfitting)
- There is a **tradeoff** between expressiveness and generalization.

---

### Model Selection
- The choice of model capacity must match:
  - Data size
  - Task complexity
- If capacity is too small → **underfitting**.  
- If capacity is too large → **overfitting**.
- **Validation methods** (e.g., cross-validation) guide capacity choice.

