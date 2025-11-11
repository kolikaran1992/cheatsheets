# MIT Probability Lecture — Summary Notes

> Review of key probability ideas leading from distributions → MGFs → Law of Large Numbers → CLT.

---

## 1. Random Variables

**Discrete:** pmf $f_X(x) \ge 0$, $\sum_x f_X(x) = 1$  
**Continuous:** pdf $f_Y(y) \ge 0$, $\int f_Y(y) \, dy = 1$

**Expectation:**
- $\mathbb{E}[X] = \sum_x x f_X(x)$  
- $\mathbb{E}[Y] = \int y f_Y(y)\,dy$

**Independence:**  
$X_1, X_2$ are independent if $P(X_1 \in A, X_2 \in B) = P(X_1 \in A)P(X_2 \in B)$  
- *Pairwise* ≠ *Mutual* independence.

---

## 2. Normal Distribution

A continuous r.v. $Y$ is normal if  
$$
f_Y(y) = \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{(y - \mu)^2}{2\sigma^2}}, \quad Y \sim \mathcal{N}(\mu, \sigma^2)
$$

Symmetric bell curve centered at $\mu$. Ubiquitous in modeling random noise and aggregate effects.

---

## 3. From Normal to Log-Normal (Change of Variables)

**Motivation:** Stock prices can’t be negative → model *log of price* as normal.

Define $X = e^Y$ with $Y \sim \mathcal{N}(\mu, \sigma^2)$.

CDF relation: $P(X \le x) = P(Y \le \log x)$  
Differentiate:

$$
f_X(x) = f_Y(\log x) \frac{d}{dx}(\log x) = \frac{f_Y(\log x)}{x}
$$

Substitute $f_Y$:

$$
\boxed{f_X(x) = \frac{1}{x\sigma\sqrt{2\pi}} \exp\!\Big[-\frac{(\log x - \mu)^2}{2\sigma^2}\Big]}, \quad x>0
$$

**Notes:**  
- $\mu,\sigma$ are parameters (not mean/variance of $X$).  
- $X$ is positive, skewed right.

---

## 4. Exponential Family

General pdf/pmf form:

$$
f_X(x|\theta) = h(x) C(\theta) \exp[\eta(\theta)^\top T(x)]
$$

Includes Normal, Poisson, Exponential, Bernoulli, etc.

- $h(x)$: base measure  
- $C(\theta)$: normalization term  
- $T(x)$: sufficient statistic  
- $\eta(\theta)$: natural parameter

**Why useful:** algebraic simplicity, factorization, conjugate priors.

---

## 5. Moment Generating Function (MGF)

$$
M_X(t) = \mathbb{E}[e^{tX}]
$$

**Moments:**
$$
M_X^{(k)}(0) = \mathbb{E}[X^k]
$$

**Series expansion:**
$$
M_X(t) = \sum_{k=0}^\infty \frac{t^k}{k!}\mathbb{E}[X^k]
$$

If two r.v.s have the same finite MGF $\Rightarrow$ same distribution.

⚠️ Log-normal has no finite MGF.  
Same moments ≠ same distribution if MGF doesn’t exist.

**Convergence:**  
If $M_{X_n}(t) \to M_X(t)$ pointwise ⇒ $X_n \xrightarrow{d} X$.

---

## 6. Weak Law of Large Numbers (WLLN)

Let $X_1,\dots,X_n$ be i.i.d. with $\mathbb{E}[X_i]=\mu$, $\mathrm{Var}(X_i)=\sigma^2$.

Sample mean: $\overline{X}_n = \frac{1}{n}\sum X_i$

$$
\boxed{\overline{X}_n \xrightarrow{P} \mu}
$$

**Proof (Chebyshev):**
$$
P(|\overline{X}_n - \mu| > \varepsilon) \le \frac{\sigma^2}{n\varepsilon^2} \to 0
$$

**Intuition:** averages stabilize; individual outcomes remain random.

---

## 7. Central Limit Theorem (CLT)

Let $X_i$ be i.i.d. with mean $\mu$, variance $\sigma^2$.  
Define standardized sum:

$$
Y_n = \frac{1}{\sqrt{n}}\sum_{i=1}^n (X_i - \mu)
$$

Then
$$
\boxed{Y_n \xrightarrow{d} \mathcal{N}(0, \sigma^2)}
$$

**Proof idea (via MGF):**
1. $M_{Y_n}(t) = \mathbb{E}[e^{tY_n}]$
2. Independence ⇒ product of expectations  
3. Taylor expand and take limit  
4. $M_{Y_n}(t) \to e^{\frac{1}{2}\sigma^2 t^2}$ (MGF of normal)

Thus sums of many independent variables approximate a normal distribution.

---

## 8. Summary Flow

| Concept | Essence | Link |
|----------|----------|------|
| Normal | baseline continuous model | → used in CLT |
| Log-normal | from change of variables | → finance modeling |
| Exponential family | unified structure | → includes normal, Poisson |
| MGF | encodes all moments | → tool for CLT |
| WLLN | averages → mean (in probability) | → convergence idea |
| CLT | normalized sums → normal | → explains universality |

---

**Takeaways**
- Change of variables connects distributions.  
- Exponential family unifies major forms.  
- MGFs summarize moment info.  
- LLN ensures stability of averages.  
- CLT explains why normality emerges.

---
