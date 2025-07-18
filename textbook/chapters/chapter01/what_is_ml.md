# Introduction to Machine Learning

Machine Learning (ML) is a subset of artificial intelligence that focuses on designing algorithms that can learn from data and make predictions or decisions without being explicitly programmed.

<br>

**<span style="font-size:1.5em;">What is Machine Learning?</span>**

At its core, ML involves using data to automatically improve a model's performance at a task. Rather than coding specific instructions, we allow the algorithm to "learn" the pattern from examples.

<br>

**<span style="font-size:1.5em;">Types of Machine Learning</span>**

- **Supervised Learning**: Learning from labeled data (e.g., classification, regression).  
- **Unsupervised Learning**: Learning from unlabeled data (e.g., clustering, dimensionality reduction).  
- **Reinforcement Learning**: Learning by interacting with an environment and receiving feedback in the form of rewards or penalties.

<br>

**<span style="font-size:1.5em;">Typical Workflow of ML</span>**

1. Data collection and preprocessing  
2. Model selection and training  
3. Evaluation and validation  
4. Deployment and monitoring

<br>

**<span style="font-size:1.5em;">Key Components of an ML System</span>**

In any ML system, there are three key components:

<div style="text-align: center;">
  <img src="../../_static/data-model.png" alt="ML Pipeline" style="width:300px; border-radius:50%;" />
</div>

**<span style="font-size:1.2em;">Dataset</span>**

A dataset consists of examples (data points) used to train and evaluate models. These examples may include:

- **Inputs (features)**: e.g., images, text, sensor data  
- **Outputs (labels)**: e.g., categories, values, actions  

**<span style="font-size:1.2em;">Model</span>**

The model is a mathematical function or structure (e.g., linear function, neural network) that maps inputs to outputs.

- It contains **parameters** that are adjusted during training  
- The goal is to learn the “best” parameters to make accurate predictions  

**<span style="font-size:1.2em;">Learning Objective</span>**

The model is trained to minimize some **loss function**, which measures how wrong its predictions are.

- Training is an optimization process  
- Evaluation ensures the model generalizes well to new data  

Together, these components form the foundation for all modern machine learning systems.
