# Typical Workflow of Machine Learning

A typical machine learning pipeline includes several key steps from raw data to deployment.

<br>

**<span style="font-size:1.5em;">Data Collection and Preprocessing</span>**

The process starts with gathering and preparing data.

- Raw data is often unstructured and noisy  
- Preprocessing includes:
  - Cleaning (e.g., handling missing values)
  - Feature extraction or engineering
  - Normalization or scaling  

The result is a dataset of labeled examples:

$$
\mathbb{D} = \{ (x_n, y_n) : n = 1, \dots, N \}
$$

<br>

**<span style="font-size:1.5em;">Model Selection</span>**

We select a model structure capable of mapping inputs to outputs:

$$
f(x; \theta)
$$

- $f$: model function  
- $\theta$: learnable parameters

Common choices include linear models, decision trees, and neural networks.

<br>

**<span style="font-size:1.5em;">Training</span>**

Training involves finding the best parameters by minimizing a loss function:

$$
\hat{\theta} = \arg\min_{\theta} \sum_{n=1}^{N} \mathcal{L}(y_n, f(x_n; \theta))
$$

- $\mathcal{L}$ is the loss function (e.g., MSE, cross-entropy)  
- Optimization is typically done using algorithms like SGD or Adam

<br>

**<span style="font-size:1.5em;">Evaluation</span>**

The trained model is tested on unseen data to assess its generalization.

- Metrics depend on the task: accuracy, RMSE, F1-score, etc.  
- Helps identify overfitting or underfitting

<br>

**<span style="font-size:1.5em;">Deployment and Monitoring</span>**

Once validated, the model is deployed into real-world applications.

- Can be integrated into apps or systems  
- Monitoring ensures performance remains acceptable over time  
- May require periodic retraining with new data

<br>
