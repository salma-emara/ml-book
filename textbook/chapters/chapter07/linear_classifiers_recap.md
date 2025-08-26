# Linear Classifiers Recap

**<span style="font-size:1.5em;">Classification with Confidence</span>**

We previously studied classifiers that not only assign labels but also output **confidence levels**.  
A key extension is to prefer classifiers with a **large margin**, where the margin is the distance between the separating hyperplane and the nearest training points.

---

**<span style="font-size:1.5em;">Classifying with Maximal Margin</span>**

The goal is to find a linear classifier that maximizes the margin with respect to a set of critical training samples — the **support vectors**.

<div style="text-align: center;">
  <img src="../../_static/svm2.jpg" alt="Support Vectors"/>
</div>
---

**<span style="font-size:1.5em;">Support Vector Classifier (SVC)</span>**

The **Support Vector Classifier (SVC)** is the maximal-margin linear classifier.  
Its separating hyperplane is determined entirely by the **support vectors**.



---

**<span style="font-size:1.5em;">SVC Optimization Formulation</span>**

The training problem can be written as:

$$
\max_{\mathbf{w}} \ \frac{1}{\|\mathbf{w}\|}
\quad \text{subject to} \quad v_n \, \mathbf{w}^\top \mathbf{x}_n \ge 1,\ \ n=1,\ldots,N .
$$

This is equivalent to the more convenient **primal problem**:

$$
\min_{\mathbf{w}} \ \|\mathbf{w}\|^2
\quad \text{subject to} \quad v_n \, \mathbf{w}^\top \mathbf{x}_n \ge 1,\ \ n=1,\ldots,N .
$$

- The objective minimizes the squared norm of $\mathbf{w}$, maximizing margin.  
- The constraints enforce that all samples are classified **without error**.


