# Chapter 3: Probabilistic Modeling and Density Estimation

This chapter introduces the foundational tools of probabilistic modeling, a central paradigm in modern machine learning. Rather than assuming fixed relationships between inputs and outputs, probabilistic models treat observations as outcomes of random processes. This perspective enables reasoning under uncertainty, learning from limited data, and generating new samples.

We begin with the concept of **density estimation**, which aims to infer the underlying distribution from which observed data is drawn. This forms the basis for generative modeling and anomaly detection.

Next, we present two key estimation principles:

- **Maximum Likelihood Estimation (MLE)**: a classical method that fits parameters to maximize the likelihood of observed data.
- **Maximum A Posteriori Estimation (MAP)**: an extension of MLE that incorporates prior knowledge, particularly useful when data is scarce.

We then extend the modeling capacity using **Gaussian Mixture Models (GMMs)**, a flexible approach that models complex, multimodal distributions as mixtures of simple Gaussian components. This naturally leads to applications in soft clustering, density estimation, and generative modeling.

By the end of this chapter, the reader will be equipped with a robust understanding of how to represent, estimate, and reason about data distributions. These concepts form an essential foundation for downstream tasks such as unsupervised learning, Bayesian inference, and deep generative modeling.
