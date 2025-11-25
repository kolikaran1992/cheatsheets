
# 📘 Mini Financial Math Cheat Sheet

## **1. Discounting — Present Value**

$$
PV = \frac{FV}{(1+r)^t}
$$
**Intuition:** Future money is worth less today because you could earn return $r$ in the meantime.



## **2. Compounding — Future Value**

$$ FV = PV(1+r)^t $$ **Intuition:** Money grows geometrically because returns
earn returns.



## **3. Perpetuity (constant payment forever)**

$$
PV = \frac{x}{r}
$$
**Intuition:** Value = the amount of capital that must be invested at rate $r$ to generate $x$ forever.



## **4. Growing Perpetuity**

$$
PV = \frac{x}{r-g} \quad\text{(valid only if } g < r \text{)}
$$
**Intuition:** Payments rise at rate $g$, so the stream is worth more — unless $g \ge r$, where the formula breaks.



## **5. Annuity (payment $x$ for $n$ years)**

$$
PV = x\left(\frac{1 - (1+r)^{-n}}{r}\right)
$$
**Intuition:** A finite stream = perpetuity minus the discounted tail after year $n$.



## **6. Future Value of an Annuity**

$$
FV = x\left(\frac{(1+r)^n - 1}{r}\right)
$$
**Intuition:** Each payment compounds for fewer periods; this formula bundles all of them.



## **7. Continuous Compounding**

$$
FV = PV e^{rt}
\qquad
PV = FV e^{-rt}
$$
**Intuition:** Interest compounds every instant, producing true exponential growth/decay.

---