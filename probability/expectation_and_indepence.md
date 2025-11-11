# ✅ Cheat Sheet: Total Expectation & Total Variance (with mini-derivations)

---

## ✅ 1. Law of Total Expectation

**Formula**

$$
E[X] = E(E[X \mid Y])
$$

**Mini-derivation (discrete \(Y\))**

$$
E[X] = \sum_x x\,P(X=x)
     = \sum_x x\sum_y P(X=x \mid Y=y)\,P(Y=y)
$$

Swap sums:

$$
E[X] = \sum_y \sum_x x\,P(X=x \mid Y=y)\,P(Y=y)
$$

Inner sum is \(E[X \mid Y=y]\):

$$
E[X] = \sum_y E[X \mid Y=y]\,P(Y=y)
     = E(E[X \mid Y])
$$

---

## ✅ 2. Law of Total Variance

**Formula**

$$
\mathrm{Var}(X)
= E[\mathrm{Var}(X \mid Y)]
+ \mathrm{Var}(E[X \mid Y])
$$

**Mini-derivation**

Start from:

$$
\mathrm{Var}(X) = E[X^2] - (E[X])^2
$$

Apply total expectation to \(X^2\):

$$
E[X^2] = E(E[X^2 \mid Y])
$$

Definition:

$$
\mathrm{Var}(X \mid Y)
= E[X^2 \mid Y] - (E[X \mid Y])^2
$$

Take expectation:

$$
E[\mathrm{Var}(X \mid Y)]
= E[E[X^2 \mid Y]] - E[(E[X \mid Y])^2]
= E[X^2] - E[(E[X \mid Y])^2]
$$

Also:

$$
\mathrm{Var}(E[X \mid Y])
= E[(E[X \mid Y])^2] - (E[X])^2
$$

Add both:

$$
E[\mathrm{Var}(X \mid Y)]
+ \mathrm{Var}(E[X \mid Y])
= E[X^2] - (E[X])^2
= \mathrm{Var}(X)
$$

---

## ✅ Interpretation

- Total expectation: average the conditional mean using the distribution of \(Y\)
- Total variance: randomness inside each \(Y\) + randomness because \(Y\) itself varies
