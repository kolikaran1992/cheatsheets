# Stochastic Processes — Cheat Sheet

## 1. Stochastic Processes

A **stochastic process** is a collection of random variables indexed by time:
- Discrete time: $X_0, X_1, X_2, \dots$
- Continuous time: $X(t),\ t \ge 0$

### Path View
A **path** (trajectory) is one full possible evolution of the process: $$\omega
= (X_0(\omega), X_1(\omega), X_2(\omega), \dots)$$ This is a function $t \mapsto
X_t(\omega)$, and the process can be seen as a **probability distribution over
paths**.



## 2. Questions Studied

1. **Dependencies:** How the past affects the future.  
2. **Long-term behavior:** LLN, CLT, variance growth.  
3. **Boundary/rare events:** Crossing thresholds, extreme events.



## 3. Simple Random Walk (SRW)

Define $Y_i \in \{\pm 1\}$ with probability $1/2$. Then:
$$X_t = \sum_{i=1}^t Y_i,\quad X_0 = 0.$$

### Key Properties

- Expectation: $\mathbb{E}[X_t] = 0$  
- Independent increments  
- Stationary increments  
- CLT scaling: $X_t / \sqrt{t} \Rightarrow N(0,1)$

### Hitting Probabilities

Boundaries at $+B$ and $-A$. Define:
$$f(k) = \mathbb{P}(\text{hit } +B \text{ before } -A \mid X_0 = k).$$

Boundary conditions: $$f(B) = 1,\quad f(-A) = 0.$$

Recurrence: $$f(k) = \tfrac12 f(k+1) + \tfrac12 f(k-1).$$

Solution:
$$f(0) = \frac{A}{A+B}.$$

**Intuition:**  
From $k$, the next step is $k+1$ or $k-1$ with probability $1/2$, and the walk
is memoryless.



## 4. Markov Chains

A process is a **Markov chain** if:
$$\mathbb{P}(X_{t+1}=s \mid X_0,\dots,X_t) = \mathbb{P}(X_{t+1}=s \mid X_t).$$

### Transition Matrix

$$P_{ij} = \mathbb{P}(X_{t+1}=j \mid X_t=i).$$

$k$-step transitions:
$$P^{(k)} = P^k.$$

### Stationary Distribution

A vector $\pi$ satisfying: $$\pi = \pi P,\quad \sum_i \pi_i=1.$$

For positive transition matrices, Perron–Frobenius ensures a unique stationary
distribution.



## 5. Martingales

A process $(X_t)$ is a **martingale** if:
$$\mathbb{E}[X_{t+1} \mid X_1,\dots,X_t] = X_t.$$

### Intuition

A martingale is a **fair game**:
- No expected gain or loss  
- Future is centered at the present  
- The process can fluctuate, but the **expected drift is zero**

**Example: Simple Random Walk**
$$\mathbb{E}[X_{t+1} \mid X_t] = X_t.$$
So SRW is a martingale.



## 6. Stopping Times

A random time $\tau$ is a **stopping time** if the event $\{\tau \le k\}$ depends only on $X_1,\dots,X_k$.

### Examples

**Stopping time:**
$$\tau = \min\{t : X_t = +100 \text{ or } X_t = -50\}.$$

**Not a stopping time:**  
The time of first peak (requires looking at future values).

Note: Section 3 asked *which boundary is hit first*. Here we care about *when* a
boundary is hit.



## 7. Optional Stopping Theorem (OST)

### Informal Statement

If $(X_t)$ is a martingale and $\tau$ is a suitable stopping time, then:
$$\mathbb{E}[X_\tau] = \mathbb{E}[X_0].$$

Stopping cannot change expected value in a fair game.

### Key Idea

A stopping rule can decide **when** to stop, but cannot create drift in a
process with zero drift.

Any strategy based only on past information (e.g., “stop when up 5”, “stop after 200 steps”, “stop after a pattern”) satisfies:
$$\mathbb{E}[X_\tau] = \mathbb{E}[X_0].$$

### Drunk Walker Intuition

A drunk takes random left/right steps.  
You try clever rules to stop at a “good” moment, but each future step is still
50/50 and cannot be predicted from past steps.  
A stopping rule cannot extract information about the future → cannot create
positive or negative expected drift.

### Why Non-Obvious

“Quit while ahead” feels like it should help, but randomness has **no memory**.  
A rule based on past values cannot influence future expected movement.

### Application to SRW Boundary

If $X_\tau$ is $100$ w.p. $p$ and $-50$ w.p. $(1-p)$:
$$\mathbb{E}[X_\tau] = 0.$$
Thus:
$$100p - 50(1-p) = 0 \Rightarrow p = \tfrac13.$$

Matches the boundary-hitting result.


