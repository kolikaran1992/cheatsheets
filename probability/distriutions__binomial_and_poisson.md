# 📌 Binomial & Poisson Distribution — Mini Cheat Sheet

## ✅ Binomial Distribution

- **Definition:** Number of successes in $n$ independent trials with success probability $p$.
- **Notation:** $X \sim \text{Bin}(n, p)$
- **PMF:**
$$
P(X = k) = \binom{n}{k} p^k (1-p)^{n-k}
$$
- **Mean:** 
$$
E[X] = np
$$
- **Variance:**
$$
\mathrm{Var}(X) = np(1-p)
$$

- **CDF (cumulative):**
$$
P(X \le k) = \sum_{r=0}^{k} \binom{n}{r} p^r(1-p)^{n-r}
$$

- **Normal approximation (when $np(1-p)$ large):**
$$
X \approx N(np,\; np(1-p))
$$


---

## ✅ Poisson Distribution

- **Definition:** Counts events occurring independently with average rate $\lambda$ in a fixed interval.
- **Notation:** $X \sim \text{Pois}(\lambda)$
- **PMF:**
$$
P(X = k) = \frac{e^{-\lambda}\lambda^k}{k!}
$$
- **Mean:**
$$
E[X] = \lambda
$$
- **Variance:**
$$
\mathrm{Var}(X) = \lambda
$$

- **CDF (no closed form):**
$$
P(X \le k) = \sum_{r=0}^{k} \frac{e^{-\lambda}\lambda^r}{r!}
$$

---

## ✅ Poisson Approximation to Binomial

When $n$ is large, $p$ small, $np = \lambda$ fixed:

$$
\text{Bin}(n,p)\ \approx\ \text{Pois}(\lambda)
$$

---