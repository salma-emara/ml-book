# K-Means Clustering

**K-Means** is one of the most widely used clustering algorithms due to its simplicity, scalability, and efficiency.

The algorithm assumes that data should be grouped around $K$ **centroids** (cluster centers) and aims to minimize the variance within each cluster.

---

**<span style="font-size:1.5em;">Problem Setup</span>**

Given a dataset:

$$
\mathbb{D} = \{x_1, x_2, \dots, x_N\} \subset \mathbb{R}^d
$$

and a fixed number of clusters $K$, the goal of K-Means is to find:

- A set of centroids $\{\mu_1, \dots, \mu_K\}$
- An assignment $z_n \in \{0, 1\}^K$ for each point, indicating which cluster it belongs to (one-hot encoded)

---

**<span style="font-size:1.5em;">Objective Function</span>**

The K-Means objective is to minimize the **sum of squared distances** between each point and its assigned centroid:

$$
\min_{\{z_n\}, \{\mu_k\}} \sum_{n=1}^N \sum_{k=1}^K z_{nk} \|x_n - \mu_k\|^2
$$

Subject to:

$$
z_{nk} \in \{0, 1\}, \quad \sum_{k=1}^K z_{nk} = 1
$$

This is a **non-convex** optimization problem that is solved via an **iterative heuristic algorithm**.

---

**<span style="font-size:1.5em;">K-Means Algorithm</span>**

The standard K-Means algorithm follows these steps:

1. **Initialization**  
   Randomly select $K$ points as initial centroids $\mu_1, \dots, \mu_K$

2. **Assignment Step**  
   Assign each data point to the **closest** centroid:

   $$
   z_n = \arg\min_k \|x_n - \mu_k\|^2
   $$

3. **Update Step**  
   Update each centroid as the **mean** of the points assigned to it:

   $$
   \mu_k = \frac{1}{|\mathcal{C}_k|} \sum_{x_n \in \mathcal{C}_k} x_n
   $$

4. **Repeat** steps 2 and 3 until convergence (no changes in assignments or centroids).

---

**<span style="font-size:1.5em;">Algorithm Properties</span>**

- **Convergence**: K-Means converges to a **local minimum** of the objective, typically within a few iterations.
- **Complexity**: Each iteration has time complexity $O(NKd)$.
- **Scalability**: Suitable for large datasets.

---

**<span style="font-size:1.5em;">Limitations</span>**

- Sensitive to initialization → poor local minima
- Requires $K$ to be known
- Only captures **spherical clusters** (assumes isotropic variance)
- Not robust to outliers

---
