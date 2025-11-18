# Birth–Death Chains: Expanded Short Cheat Sheet

## 1. How to Recognize a Birth–Death Chain

A Markov chain is a **birth–death chain** if:

* States lie on a line: $0,1,\dots,m$ (or infinite).
* From any state $i$, you may only move to:

  * $i+1$ (birth),
  * $i-1$ (death),
  * $i$ (holding).

Formally:

$$
P_{i,j} = 0 \quad \text{whenever } |i-j| > 1.
$$

This “nearest-neighbor on a line” structure is the defining feature.



## 2. When Is a Birth–Death Chain Reversible?

Reversibility requires **two-way movement across every edge**:

$$
P_{i,i+1} > 0 \quad \text{and} \quad P_{i+1,i} > 0.
$$

If this holds for all adjacent $i$, then:

* No cycles exist (the graph is a path),
* No directional circulation can occur,
* Therefore the chain is **automatically reversible**.

Self-loops $P_{i,i}$ do not affect reversibility.



## 3. Detailed Balance (Key Equation)

Reversibility means the equilibrium probability flow across each edge balances:

$$
\pi_i P_{i,i+1} = \pi_{i+1} P_{i+1,i}.
$$

This gives the core recurrence:

$$
\frac{\pi_{i+1}}{\pi_i}
=\frac{P_{i,i+1}}{P_{i+1,i}}.
$$

Thus:

$$
\pi_i = \pi_0 \prod_{k=0}^{i-1}
\frac{P_{k,k+1}}{P_{k+1,k}}.
$$

This is the fastest method to find $\pi$.

Normalize via $\sum_i \pi_i = 1$ (finite chain) or check convergence (infinite
chain).



## 4. Infinite Birth–Death Chains

Detailed balance still gives:

$$
\pi_i = \pi_0 \prod_{k=0}^{i-1}
\frac{P_{k,k+1}}{P_{k+1,k}}.
$$

But you must verify:

$$
\sum_{i=0}^\infty \pi_i < \infty.
$$

* If the sum is finite → proper stationary distribution exists.
* If infinite → chain is reversible but **has no stationary distribution** (e.g., simple symmetric walk on $\mathbb{Z}$).



## 5. Practical Problem-Solving Workflow

1. **Identify** nearest-neighbor structure → birth–death.
2. **Check** both directions are positive → reversible.
3. **Apply detailed balance** to find all $\pi_i / \pi_0$.
4. **Normalize** (finite) or **check convergence** (infinite).
5. **Write final stationary distribution**.


