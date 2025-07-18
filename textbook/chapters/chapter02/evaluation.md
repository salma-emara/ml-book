## Risk Minimization Framework for Soft Clustering**

Clustering can be reformulated in a **probabilistic learning framework**, where we treat the problem as minimizing a loss over **soft assignments** of data points to clusters.

---

**<span style="font-size:1.8em;"> Problem Setup </span>**

We are given a dataset of $N$ samples:

$$
\mathbb{D} = \{ x_n \in \mathbb{R}^d : n = 1, \dots, N \}
$$

We assume the existence of $K$ clusters, represented by centroids $\{ \mu_k \}_{k=1}^K$.

Instead of assigning each point to a single cluster, we define a **soft assignment vector**:

$$
\gamma_n \in \Delta_K \subset \mathbb{R}^K, \quad \text{where} \quad \Delta_K := \left\{ \gamma \in \mathbb{R}^K \, \bigg| \, \sum_{k=1}^K \gamma_k = 1, \gamma_k \geq 0 \right\}
$$

Here, $\gamma_{n,k}$ denotes the probability (or responsibility) that point $x_n$ belongs to cluster $k$.

---

**<span style="font-size:1.8em;"> Clustering as Risk Minimization</span>**

We define a **loss function** measuring the cost of assigning $x_n$ to cluster $k$:

$$
\ell(x_n, \mu_k) = \| x_n - \mu_k \|^2
$$

The **expected loss** (or empirical risk) is then:

$$
\mathcal{L}(\{\mu_k\}, \{\gamma_n\}) = \frac{1}{N} \sum_{n=1}^N \sum_{k=1}^K \gamma_{n,k} \, \ell(x_n, \mu_k)
= \frac{1}{N} \sum_{n=1}^N \sum_{k=1}^K \gamma_{n,k} \, \| x_n - \mu_k \|^2
$$

The goal is to jointly optimize over the centroids and soft assignments:

$$
\min_{\{\mu_k\}, \{\gamma_n\}} \quad \mathcal{L}(\{\mu_k\}, \{\gamma_n\}) \quad \text{subject to} \quad \gamma_n \in \Delta_K
$$

---

**<span style="font-size:1.8em;">Interpretation</span>**

This framework offers a **continuous relaxation** of the hard clustering problem:
- In hard clustering, $\gamma_{n,k} \in \{0,1\}$ with exactly one non-zero entry.
- In soft clustering, we allow $\gamma_{n,k}$ to take any value in $[0,1]$ as long as they sum to 1.

Such formulations are useful for **probabilistic models** (e.g., Gaussian Mixture Models) and **EM-style algorithms**, where we alternate between estimating $\gamma_n$ and updating $\mu_k$.

---
