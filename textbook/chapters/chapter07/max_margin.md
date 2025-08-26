# Maximum Margin Classifier

**<span style="font-size:1.5em;">Support Vector Classifier (SVC): Constrained Optimization</span>**

The Support Vector Classifier seeks the separating hyperplane with **maximum margin**.  
Formally, we solve:

$$
\min_{\mathbf{w}} \ \|\mathbf{w}\|^2
\quad \text{subject to} \quad v_n \,\mathbf{w}^\top \mathbf{x}_n \ge 1,
\quad n=1,\ldots,N .
$$

- Objective: minimize $\|\mathbf{w}\|^2$ (maximize margin).  
- Constraints: all samples lie **on or outside** the margin boundaries.

---

**<span style="font-size:1.5em;">Why is This Constrained?</span>**

- With no constraint, the trivial minimizer is $\mathbf{w}=\mathbf{0}$.  
- Constraints enforce correct classification:  
  $$
  v_n \,\mathbf{w}^\top \mathbf{x}_n \ge 1 .
  $$  
- With $N$ samples, there are $N$ linear constraints.  
- Thus, the problem is a **quadratic program with linear constraints**.

---

**<span style="font-size:1.5em;">Visual Illustration</span>**

Support vectors are those points **exactly on the margin boundaries**.  
They uniquely determine the separating hyperplane.

<div style="text-align: center;">
  <img src="../../_static/svm2.jpg" alt="Support Vectors"/>
</div>

