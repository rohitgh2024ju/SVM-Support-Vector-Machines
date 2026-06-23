# Support Vector Machine (SVM)

## 1. Overview

Support Vector Machine (SVM) is a supervised machine learning algorithm used for classification and regression tasks. Its primary goal is to find a decision boundary that separates different classes while maximizing the margin between them.

---

## 2. Problem Statement

Given a dataset:

$$
D = {(x_i, y_i)}_{i=1}^{n}
$$

where:

* $x_i \in \mathbb{R}^d$ represents the feature vector
* $y_i \in {-1, +1}$ represents the class label

The objective is to find a hyperplane that correctly separates the classes.

---

## 3. Intuition

Consider two classes of points in a 2D plane.

Many lines can separate them.

SVM chooses the line that leaves the largest possible distance between the nearest points of both classes.

This distance is called the **margin**.

A larger margin generally leads to better generalization on unseen data.

---

## 4. Hyperplane

A hyperplane is defined as:

$$
w^T x + b = 0
$$

where:

* $w$ = weight vector
* $b$ = bias term

Prediction:

$$
f(x) = sign(w^T x + b)
$$

---

## 5. Support Vectors

Support vectors are the training samples closest to the decision boundary.

These points determine the position and orientation of the hyperplane.

Removing non-support vectors often does not change the decision boundary.

---

## 6. Margin

The margin is given by:

$$
\frac{2}{||w||}
$$

To maximize the margin, SVM minimizes:

$$
\frac{1}{2} ||w||^2
$$

subject to:

$$
y_i(w^T x_i + b) \ge 1
$$

---

## 7. Optimization Objective

The hard-margin SVM optimization problem is:

$$
\min_{w,b}
\frac{1}{2}
||w||^2
$$

subject to:

$$
y_i(w^T x_i+b)\ge1
$$

This is a constrained convex optimization problem.

---

## 8. Soft Margin SVM

Real-world data is rarely perfectly separable.

Slack variables $\xi_i$ are introduced:

$$
y_i(w^T x_i+b)\ge1-\xi_i
$$

The new objective becomes:

$$
\min_{w,b}
\frac12||w||^2 +
C\sum_{i=1}^{n}\xi_i
$$

where $C$ controls the trade-off between margin size and classification errors.

---

## 9. Kernel Trick

When data is not linearly separable, SVM can transform it into a higher-dimensional feature space.

Common kernels:

### Linear Kernel

$$
K(x,z)=x^Tz
$$

### Polynomial Kernel

$$
K(x,z)=(x^Tz+c)^d
$$

### RBF Kernel

$$
K(x,z)=\exp(-\gamma ||x-z||^2)
$$

---

## 10. Advantages

* Effective in high-dimensional spaces
* Works well with small datasets
* Strong theoretical foundations
* Can model nonlinear relationships using kernels

---

## 11. Limitations

* Training can be slow on large datasets
* Sensitive to kernel selection
* Less interpretable than decision trees
* Memory intensive for large numbers of support vectors

---

## 12. Applications

* Spam detection
* Text classification
* Image recognition
* Bioinformatics
* Handwriting recognition

---

## 13. Scikit-Learn Example

```python
from sklearn.svm import SVC

model = SVC(kernel="rbf")

model.fit(X_train, y_train)

predictions = model.predict(X_test)
```

---

## 14. Key Takeaways

* SVM finds the maximum-margin hyperplane.
* Support vectors define the boundary.
* Soft margins handle noisy data.
* Kernels allow nonlinear classification.
* SVM is fundamentally an optimization problem.
