# 🧮 Linear Algebra Review — Key Concepts from MIT Lecture

## 📘 1. Matrices and Linear Transformations

A **matrix** is more than a table of numbers — it represents a **linear transformation**.

$$
A: \mathbb{R}^n \to \mathbb{R}^m
$$

It takes an input vector in $n$-dimensions and transforms it into another vector in $m$-dimensions.

---

## 🟩 2. Square Matrices and Eigenvalues

### Definition

For a square matrix $A \in \mathbb{R}^{n \times n}$:

$$
A v = \lambda v
$$

* $\lambda$: eigenvalue (scalar)
* $v$: eigenvector (nonzero vector)

---

### Characteristic Equation

$$
\det(A - \lambda I) = 0
$$

This gives a degree-$n$ polynomial — it **always has at least one (complex) root**, so **every square matrix has at least one eigenvalue**.

---

### Geometric Meaning

Eigenvectors are directions that remain unchanged under $A$;
Eigenvalues are the factors by which those directions are scaled.

```
     ^ y
     |
     |         Original v
     |        /
     |       /
     |      /
     |     /
     |    /
     |   /
     |  /
     | /______________> x
          Av = λv (stretched or flipped)
```

---

## 🔶 3. Real and Symmetric Matrices

### Symmetric Matrix

$$
A = A^T
$$

### Properties

1. **Always diagonalizable:**
   $A = U D U^T$
2. **All eigenvalues are real**
3. **Eigenvectors form an orthonormal basis**

---

### Geometric Meaning

A symmetric matrix **stretches space along orthogonal directions** — the eigenvectors are perpendicular, and each is scaled by its eigenvalue.

```
Before (unit circle):               After (ellipse stretched along eigenvectors):

        y                                   y
        |                                   |
     *--|--*                             *--|--*
    *   |   *                           *   |   *
     *--|--*                             *--|--*
        |                                   |
        +---------- x              λ1>λ2 -> ellipse stretched more in v1 direction
```

---

## 🔷 4. SVD — The Analogy for Rectangular Matrices

When $A$ is **not square or not symmetric**, eigenvalues may not exist.
Instead, we use the **Singular Value Decomposition (SVD):**

$$
A = U \Sigma V^T
$$

* $U \in \mathbb{R}^{m \times m}$: left singular vectors
* $V \in \mathbb{R}^{n \times n}$: right singular vectors
* $\Sigma \in \mathbb{R}^{m \times n}$: diagonal matrix of singular values $\sigma_i \ge 0$

---

### Connection to Eigenvalues

$$
A^T A v_i = \sigma_i^2 v_i
$$

So SVD is a **generalization** of eigen-decomposition. Note that $A^TA$ is symmetric

---

### Geometric Meaning

In SVD, the original transformation $A$ acts on the right-singular vectors $v_i$
(from matrix $V$) and produces scaled left-singular vectors $u_i$ (from matrix $U$):

$$
A v_i = \sigma_i u_i
$$

```
   Input space (R^n)                     Output space (R^m)
   ----------------------------------    ----------------------------------
        v1, v2, v3   ∈  columns(V)              u1, u2, u3  ∈  columns(U)

          |                                       |
          |                                       |
          |       ┌──────────────────────┐        |
          |       │      A = UΣVᵀ       │        |
          |       └──────────────────────┘        |
          |                                       |
          |---->   Av₁ = σ₁u₁                     |
          |---->   Av₂ = σ₂u₂                     |
          |---->   Av₃ = σ₃u₃                     |
          
   ⇒  Transformation A sends each vᵢ (input direction)
      to a corresponding uᵢ (output direction),
      scaled by σᵢ (the singular value).
```

> So, **in SVD**, the transformation $A$ “rotates and stretches” —
> taking the basis $V$ in the input space and producing the basis $U$ in the output space.

---

## 🧭 5. Practical Meaning

* **Eigenvalues / Eigenvectors:** Describe internal structure of square transformations.
* **SVD:** Works for any data matrix; reveals dominant modes and correlations.
* **Applications:**

  * Data compression
  * Principal Component Analysis (PCA)
  * Noise reduction
  * Latent semantic analysis
  * Covariance/correlation analysis

---

## 🧠 6. Key Takeaways

✅ Eigenvalues exist only for **square** matrices
✅ Symmetric matrices → **real eigenvalues** and **orthogonal eigenvectors**
✅ SVD generalizes eigen-decomposition to **any** matrix
✅ Eigenvectors = directions of invariant scaling
✅ Singular values = strengths of action between spaces
✅ Both capture the **geometry of transformations**

---

### Mental Shortcut Summary

| Concept | Works for              | Matrix Form        | Scalars         | Directions                  | Geometric Meaning                    |
| ------- | ---------------------- | ------------------ | --------------- | --------------------------- | ------------------------------------ |
| **EVD** | Square, diagonalizable | $A = U D U^T$      | Eigenvalues     | Eigenvectors                | Stretch along same basis             |
| **SVD** | Any $m \times n$       | $A = U \Sigma V^T$ | Singular values | Left/right singular vectors | Stretch between two orthogonal bases |
