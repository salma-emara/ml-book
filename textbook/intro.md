# Chapter 2: Introduction to clustering - Unsupervised Learning

Unsupervised learning is a fundamental branch of machine learning where models are trained on **unlabeled data**. That is, the input data $\mathbb{D} = \{ \mathbf{x}_1, \dots, \mathbf{x}_N \}$ contains **no target outputs**. The goal is to uncover **hidden patterns, structures, or groupings** that naturally exist in the data.

<br>

<div style="text-align: center;">
  <img src="../../_static/clusteringcover.png" alt="Clustering Visualization" style="width:300px; border-radius:12px;" />
</div>

<br>

**<span style="font-size:1.5em;">Key Goals of Unsupervised Learning</span>**

- Discover clusters or groupings of similar examples  
- Learn low-dimensional representations (dimensionality reduction)  
- Estimate data-generating distributions (density estimation)  
- Extract latent variables underlying the data

<br>

**<span style="font-size:1.5em;">Why is it Important?</span>**

- In many real-world applications, labels are **expensive or unavailable**  
- Enables exploratory data analysis and structure discovery  
- Forms the basis of pretraining and self-supervised learning in modern AI systems

<br>

**<span style="font-size:1.5em;">Core Problems in Unsupervised Learning</span>**

- **Clustering**: Partitioning data into groups based on similarity  
- **Dimensionality Reduction**: Projecting high-dimensional data into a lower-dimensional space  
- **Anomaly Detection**: Identifying outliers in the data  
- **Generative Modeling**: Modeling the underlying distribution of data

<br>

In this chapter, we will focus primarily on **clustering**, one of the most widely used and foundational unsupervised tasks. We will study its theoretical formulation, common algorithms (like K-means and GMMs), and evaluation techniques.

---

