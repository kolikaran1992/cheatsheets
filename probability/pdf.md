# 📘 Joint, Marginal, and Conditional PDFs — Cheat Sheet

## 1. Probability Density Function (PDF)

- For a continuous random variable $X$:
  $$
  P(a < X < b) = \int_a^b f_X(x)\,dx
  $$
- Must satisfy: $f_X(x) \ge 0$, $\int_{-\infty}^{\infty} f_X(x)\,dx = 1$

---

## 2. Joint PDF

- For two random variables $(X, Y)$:
  $$
  P((X,Y) \in A) = \iint_A f_{X,Y}(x,y)\,dx\,dy
  $$
- Must satisfy:
  $$
  f_{X,Y}(x,y) \ge 0, \quad \iint f_{X,Y}(x,y)\,dx\,dy = 1
  $$

**Example (Independent Uniforms):**

$$
f_{X,Y}(x,y) =
\begin{cases}
1, & 0<x<1,\ 0<y<1\\
0, & \text{otherwise}
\end{cases}
$$

---

## 3. Marginal PDFs

- Obtained by integrating (summing out) other variables:

  $$
  f_X(x) = \int_{-\infty}^{\infty} f_{X,Y}(x,y)\,dy, \quad
  f_Y(y) = \int_{-\infty}^{\infty} f_{X,Y}(x,y)\,dx
  $$

**Example:**

For $f_{X,Y}(x,y)=2$ on $0<x<y<1$:

$$
f_X(x) = \int_x^1 2\,dy = 2(1-x), \quad
f_Y(y) = \int_0^y 2\,dx = 2y
$$

---

## 4. Conditional PDFs

- Define conditional density of $Y$ given $X=x$:
  $$
  f_{Y|X}(y|x) = \frac{f_{X,Y}(x,y)}{f_X(x)}, \quad f_X(x)>0
  $$
- Satisfies normalization:
  $$
  \int f_{Y|X}(y|x)\,dy = 1
  $$

**Example:**
If $f_{X,Y}(x,y)=2$ on $0<x<y<1$,  
then $f_{Y|X}(y|x)=1/(1-x)$ for $x<y<1$.

---

## 5. Independence

- $X$ and $Y$ are independent if:
  $$
  f_{X,Y}(x,y) = f_X(x)f_Y(y)
  $$
  which implies $f_{Y|X}(y|x) = f_Y(y)$

---

## 6. Multivariate (n-D) Joint PDFs

For $\mathbf{X} = (X_1, X_2, \dots, X_n)$:
$$
f_{\mathbf{X}}(x_1, \dots, x_n) \ge 0, \quad
\int_{\mathbb{R}^n} f_{\mathbf{X}}(\mathbf{x})\,d\mathbf{x} = 1
$$

### Marginalization
$$
f_{X_1,\dots,X_k}(x_1,\dots,x_k) =
\int_{\mathbb{R}^{n-k}} f_{X_1,\dots,X_n}(x_1,\dots,x_n)\,dx_{k+1}\dots dx_n
$$

### Conditioning
If $\mathbf{X}=(\mathbf{X}_1,\mathbf{X}_2)$,  
then
$$
f_{\mathbf{X}_1|\mathbf{X}_2}(\mathbf{x}_1|\mathbf{x}_2)
= \frac{f_{\mathbf{X}_1,\mathbf{X}_2}(\mathbf{x}_1,\mathbf{x}_2)}{f_{\mathbf{X}_2}(\mathbf{x}_2)}
$$

---

## 7. Dimensionality Notes

| Operation                   | Description                                | Dimensionality |
| --------------------------- | ------------------------------------------ | -------------- |
| Partition of one n-D vector | $\mathbf{X} = (\mathbf{X}_1,\mathbf{X}_2)$ | stays n-D      |
| Joint of two n-D vectors    | $(\mathbf{X}_1,\mathbf{X}_2)$              | becomes 2n-D   |

---

## 8. Examples Summary

| Case                              | PDF                   | Support          |
| --------------------------------- | --------------------- | ---------------- |
| Independent $X,Y \sim U(0,1)$     | $f_{X,Y}=1$           | $0<x<1, 0<y<1$   |
| Dependent $Y=X+Z$, $Z\sim U(0,1)$ | $f_{X,Y}=1$           | $0<x<1, x<y<x+1$ |
| Perfect dependence $Y=X$          | $f_{X,Y}=\delta(y-x)$ | Line $y=x$       |

---

## 9. Key Takeaways

- **Joint PDF:** probability density over all variables.  
- **Marginal PDF:** integrate out the others.  
- **Conditional PDF:** fix one subset and renormalize.  
- **Independence:** factorization of joint into product of marginals.  
- **Dimensional rule:** joint of distinct vectors → dimensions add.

---
