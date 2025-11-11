## 1. Setup

* Let random variables be i.i.d.:
  $$ X_1, X_2, \dots, X_n \quad\text{i.i.d.} $$
* Each has
  $$ \mathbb{E}[X_i] = \mu, \quad \mathrm{Var}(X_i) = \sigma^2 $$

---

## 2. Sum of i.i.d. random variables

Let
$$ S_n = X_1 + X_2 + \dots + X_n $$

### **Expectation**

$$ \mathbb{E}[S_n] = \mathbb{E}[X_1] + \dots + \mathbb{E}[X_n] = n\mu $$

### **Variance** (independence required)

$$ \mathrm{Var}(S_n) = \mathrm{Var}(X_1) + \dots + \mathrm{Var}(X_n) = n\sigma^2 $$

---

## 3. Average of i.i.d. random variables

Let
$$ \bar{X} = \frac{S_n}{n} $$

### **Expectation**

$$ \mathbb{E}[\bar{X}] = \mu $$

### **Variance**

$$ \mathrm{Var}(\bar{X}) = \frac{\sigma^2}{n} $$

---

## 4. Special Case: Bernoulli(p)

* Each $(X_i \in {0,1})$
* $$ \mu = p,\quad \sigma^2 = p(1-p) $$

So

* Sum:
  $$ \mathbb{E}[S_n] = np,\quad \mathrm{Var}(S_n) = np(1-p) $$
* Mean:
  $$ \mathbb{E}[\bar{X}] = p,\quad \mathrm{Var}(\bar{X}) = \frac{p(1-p)}{n} $$

---