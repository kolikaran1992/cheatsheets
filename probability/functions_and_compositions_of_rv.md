# Expectation & Variance Cheat Sheet

## 1. Expectation of a Function of a Random Variable
Discrete:
$$
\mathbb{E}[f(X)] = \sum_x f(x)\,P(X=x)
$$

Continuous:
$$
\mathbb{E}[f(X)] = \int_{-\infty}^\infty f(x)\,f_X(x)\,dx
$$

---

## 2. Expectation of a Product (Independence)
If $X$ and $Y$ are independent:

Start with the law of total expectation:
$$
\mathbb{E}[f(X)g(Y)] = \mathbb{E}\big[\,\mathbb{E}[f(X)g(Y)\mid X]\,\big]
$$

Inside the inner expectation, treat $X$ as known:
- $f(X)$ is now a constant
- $Y$ is still random but independent of $X$

So:
$$
\mathbb{E}[f(X)g(Y)\mid X] = f(X)\,\mathbb{E}[g(Y)]
$$

Plug back:
$$
\mathbb{E}[f(X)g(Y)] = \mathbb{E}\big[f(X)\,\mathbb{E}[g(Y)]\big]
= \mathbb{E}[g(Y)]\,\mathbb{E}[f(X)]
$$

Thus:
$$
\boxed{\mathbb{E}[f(X)g(Y)] = \mathbb{E}[f(X)]\,\mathbb{E}[g(Y)]}
$$

Special case:
$$
\mathbb{E}[XY] = \mathbb{E}[X]\,\mathbb{E}[Y]
$$

---

## 3. Variance
$$
\mathrm{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2
$$

If $X$ and $Y$ are independent:
$$
\mathrm{Var}(X+Y) = \mathrm{Var}(X) + \mathrm{Var}(Y)
$$

More generally:
$$
\mathrm{Var}(aX + b) = a^2\,\mathrm{Var}(X)
$$

---

## 4. Intuition
- Independence means knowing $X$ tells you nothing about $Y$, so averaging $f(X)g(Y)$ splits into two separate averages.
- Variance measures spread; independent spreads add.
