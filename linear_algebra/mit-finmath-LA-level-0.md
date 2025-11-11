# 🧮 Linear Algebra Essentials — Cheat Sheet

---

## 🔹 Vector Spaces, Image & Kernel
A matrix $A \in \mathbb{R}^{m \times n}$ defines a linear map $T_A(x)=Ax$.

- **Image (Range):** all outputs $Ax$ → $\text{Im}(A)$.  
- **Kernel (Nullspace):** all inputs mapping to $0$ → $\ker(A)$.

**Rank–Nullity Theorem:**
$$\text{rank}(A) + \text{nullity}(A) = n.$$
Rank measures output dimension, nullity measures input redundancy.

---

## 🔹 Row & Column Rank
- **Row space:** span of row vectors → independent equations.  
- **Column space:** span of column vectors → independent outputs.  
They always have the same dimension:
$$\text{row rank}(A) = \text{col rank}(A) = \text{rank}(A).$$  
✅ Proves (a): row-rank equals column-rank for all matrices.

---

## 🔹 Rank Inequalities
For $A \in \mathbb{R}^{m \times n}$, $B \in \mathbb{R}^{n \times g}$:
$$\text{rank}(AB) \le \min(\text{rank}(A), \text{rank}(B)).$$
Because $\text{Im}(AB) = A(\text{Im}(B)) \subseteq \text{Im}(A)$ —  
$AB$ cannot produce more independent directions than $A$ or $B$.  
✅ Proves (b).

---

## 🔹 Left, Right, and Full Inverses
| Type | Definition | Condition | Interpretation |
|------|-------------|------------|----------------|
| Left inverse | $LA = I_n$ | Columns independent ($\text{rank}=n$) | One–one map |
| Right inverse | $AR = I_m$ | Rows independent ($\text{rank}=m$) | Onto map |
| Full inverse | $A^{-1}A = AA^{-1} = I_n$ | Square, full rank | Bijective map |

If both a left and right inverse exist, they are equal → $A^{-1}$.  
✅ Disproves (c): both inverses imply $A$ is invertible.

---

## 🔹 Full Rank and Invertibility
A square matrix is **invertible** iff it has **full rank**:
$$\det(A) \ne 0 \iff \text{rank}(A)=n.$$
Full rank means no redundant rows/columns, so $A$ is bijective.  
✅ Proves (d).

---

## 🔹 Symmetric Matrices
- Symmetric matrices satisfy $A=A^T$ and are **orthogonally diagonalizable**.  
- Some may have zero eigenvalues → singular (non-invertible).  
❌ Disproves (e).

Example:
$$
\begin{bmatrix}
1 & 0 & 1\\
0 & 0 & 0\\
1 & 0 & 1
\end{bmatrix}
$$
is symmetric but not invertible.

---

## 🔹 Eigenvalues, Invertibility & Diagonalizability
- $A$ is **invertible** ⇔ all eigenvalues $\ne 0$.  
- **Distinct eigenvalues** ⇒ $A$ is **diagonalizable**, but if one eigenvalue is 0 → not invertible.  
❌ Disproves (f).

- **Diagonalizable** ⇏ **invertible** (can have 0 eigenvalue).  
- **Invertible** ⇏ **diagonalizable** (may lack enough eigenvectors).  
❌ Disproves (g).

---

## 🔹 Quick Summary

| # | Statement | True / False | Key Concept |
|---|------------|--------------|--------------|
| (a) | Row-rank = Column-rank | ✅ | Equal dimensions of row/col spaces |
| (b) | $\text{rank}(AB) \le \text{rank}(A)$ | ✅ | Image containment |
| (c) | Left & right inverses unequal | ❌ | Both ⇒ same inverse |
| (d) | Full rank ⇔ Invertible | ✅ | $\det(A) \ne 0$ |
| (e) | All symmetric matrices invertible | ❌ | May have 0 eigenvalues |
| (f) | Distinct eigenvalues ⇒ invertible | ❌ | Possible 0 eigenvalue |
| (g) | Diagonalizable ⇔ invertible | ❌ | Independent properties |

---
