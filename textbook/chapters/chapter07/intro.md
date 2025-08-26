# Support Vector Machine (SVM) 

**<span style="font-size:1.5em;">Motivation</span>**

Linear classifiers aim to separate data points using a hyperplane.  
However, if the data are linearly separable, there are infinitely many such hyperplanes.  
Which one should we choose?

Support Vector Machines (SVMs) resolve this ambiguity by selecting the hyperplane with the **maximum margin** — the largest distance between the boundary and the nearest data points.

---

**<span style="font-size:1.5em;">Support Vectors and Margin</span>**

- **Support vectors** are the critical samples lying closest to the decision boundary.  
- The **margin** is defined as the distance between these support vectors and the separating hyperplane.  
- Maximizing the margin improves the classifier’s robustness and generalization.

---

**<span style="font-size:1.5em;">Geometric Intuition</span>**

<div style="text-align: center;">
  <img src="../../_static/svm1.png" alt="SVM margins"/>
</div>

- Only the support vectors determine the decision boundary.  
- Points far from the hyperplane do not affect the classifier.

---

**<span style="font-size:1.5em;">Agenda for This Chapter</span>**

In this chapter we will:

1. Recap linear classifiers and introduce the concept of **maximum margin**.  
2. Formulate the **Support Vector Classifier (SVC)** as an optimization problem.  
3. Solve the optimization using the **dual formulation** and **KKT conditions**.  
4. Extend to nonlinear decision boundaries using the **kernel trick**.  
5. Incorporate robustness via the **soft-margin SVM**.  
6. Conclude with **practical aspects**, including kernels and parameter choices.

---

**<span style="font-size:1.5em;">References</span>**

- Bishop, *Pattern Recognition and Machine Learning*, Ch. 6  
- Hastie, Tibshirani, Friedman, *The Elements of Statistical Learning*, Ch. 12
