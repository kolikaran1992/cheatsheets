# Moment Generating Functions (MGFs) — Quick Cheat Sheet

### Definition
- MGF of a random variable $X$:
  $$
  M_X(t) = \mathbb{E}[e^{tX}]
  $$
- Generates moments:
  $$
  M_X^{(n)}(0) = \mathbb{E}[X^n]
  $$

### Key Properties
- If the MGF exists near $t = 0$, it uniquely determines the distribution.
- For independent $X$ and $Y$:
  $$
  M_{X+Y}(t) = M_X(t)\,M_Y(t)
  $$

### Useful MGFs
- Normal $N(\mu, \sigma^2)$:
  $$
  M_X(t) = \exp\!\left(\mu t + \tfrac{1}{2}\sigma^2 t^2\right)
  $$
- Bernoulli($p$):
  $$
  M_X(t) = (1-p) + p e^t
  $$
- Exponential($\lambda$):
  $$
  M_X(t) = \frac{\lambda}{\lambda - t},\quad t < \lambda
  $$

---

## Short Derivation for Normal MGF
Let $X \sim N(\mu, \sigma^2)$.

Start with
$$
M_X(t) = \mathbb{E}[e^{tX}]
= \int_{-\infty}^{\infty} e^{tx}\,f_X(x)\,dx
$$

Combine exponent terms and complete the square:
$$
tx - \frac{(x-\mu)^2}{2\sigma^2}
= -\frac{(x-(\mu+\sigma^2 t))^2}{2\sigma^2}
+ \mu t + \tfrac{1}{2}\sigma^2 t^2
$$

So
$$
M_X(t) = e^{\mu t + \tfrac{1}{2}\sigma^2 t^2}
\int_{-\infty}^\infty
\frac{1}{\sqrt{2\pi\sigma^2}}
\exp\!\left(-\frac{(x-(\mu+\sigma^2 t))^2}{2\sigma^2}\right)\,dx
$$

The integral is $1$ (it's a Normal pdf), so:
$$
\boxed{M_X(t) = \exp\!\left(\mu t + \tfrac{1}{2}\sigma^2 t^2\right)}
$$

---
