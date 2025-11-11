Here’s a **short, compact cheat-sheet** that includes the key formulas **and** their shortest clean derivations.

---

# ✅ **Cheat Sheet: Total Expectation & Total Variance (with mini-derivations)**

---

## ✅ **1. Law of Total Expectation**

### **Formula**

[
E[X] = E(E[X\mid Y])
]

### **Mini-Derivation (discrete (Y))**

[
E[X] = \sum_x x,P(X=x)
= \sum_x x\sum_y P(X=x\mid Y=y)P(Y=y)
]
Swap sums:
[
E[X] = \sum_y \sum_x x,P(X=x\mid Y=y)P(Y=y)
]
Inner sum is (E[X\mid Y=y]):
[
E[X] = \sum_y E[X\mid Y=y],P(Y=y) = E(E[X\mid Y])
]

(Continuous version: replace sums with integrals — same steps.)

---

## ✅ **2. Law of Total Variance**

[
\text{Var}(X) = E[\text{Var}(X\mid Y)] + \text{Var}(E[X\mid Y])
]

### **Mini-Derivation**

Start from:
[
\text{Var}(X) = E[X^2] - (E[X])^2
]
Apply total expectation to (X^2):
[
E[X^2] = E(E[X^2\mid Y])
]
Use the definition:
[
\text{Var}(X\mid Y) = E[X^2\mid Y] - (E[X\mid Y])^2
\Rightarrow E[\text{Var}(X\mid Y)]
= E[E[X^2\mid Y]] - E[(E[X\mid Y])^2]
= E[X^2] - E[(E[X\mid Y])^2]
]
Also:
[
\text{Var}(E[X\mid Y]) = E[(E[X\mid Y])^2] - (E[X])^2
]
Add both:
[
E[\text{Var}(X\mid Y)] + \text{Var}(E[X\mid Y])
= \big(E[X^2] - E[(E[X\mid Y])^2]\big)

* \big(E[(E[X\mid Y])^2] - (E[X])^2\big)
  = E[X^2] - (E[X])^2
  = \text{Var}(X)
  ]

---

## ✅ **Interpretation in one line**

* Total expectation: average the conditional mean using the distribution of (Y)
* Total variance: total randomness = randomness inside each (Y) + randomness because (Y) itself varies

---

That’s the shortest clean cheat-sheet with derivations included.
