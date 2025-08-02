---
layout: default
title: "1. Borel's Number Theorem"
---

**Problem 1.1**

**(a)** Suppose $$(\Omega, \mathcal{F}, P)$$ is a discrete probability space with $$A_n \in \mathcal{F}$$ for all $$n$$. Let $$i \in I \subseteq \mathbb{N}$$ index the elements of $$\Omega$$.
Pick $$\omega_i \in \Omega$$ and suppose $$\omega_i \in A_n$$ infinitely often. That is,
there exists a subsequence $$\{n_k\}$$ for which $$\omega_i \in A_{n_k}$$ for all $$k$$. For any index $$K$$, we have  

$$
P(\{\omega_i\}) \leq P\left(\bigcap_{k=1}^K A_{n_k}\right) = \prod_{k=1}^K P(A_{n_k}) = \frac{1}{2^K}
$$  

Since $$K$$ can be made arbitrarily large, $$P(\{\omega_i\}) = 0$$.

Now suppose $$\omega_i \in A_n$$ only finitely often. Then it must be the case that $$\omega_i \in A_n^c$$ infinitely often.
But then by a similar argument, we can show $$P(\{\omega_i\}) = 0$$.

We therefore conclude  

$$
P(\Omega) = P\left(\bigcup_{i \in I} \{\omega_i\}\right) = \sum_{i \in I} P(\{\omega_i\}) = 0
$$  

Since $$P(\Omega) = 1$$, this is a contradiction.

**(b)** Again fix $$\omega_i \in \Omega$$ and let  

$$
E_n = \begin{cases}A_n^c & \text{if } \omega_i \in A_n \\[2ex] A_n & \text{otherwise}\end{cases}
$$  

Since $$P(E_n) \geq \alpha_n$$, we must have $$\sum_{n=1}^\infty P(E_n) \geq \sum_{n=1}^\infty \alpha_n$$.
Therefore $$\sum_{n} P(E_n)$$ diverges if $$\sum_{n} \alpha_n$$ diverges.

By the second Borel–Cantelli lemma (Theorem 4.4), $$P(\limsup_{n} E_n) = 1$$.
But since $$\omega \in E_n^c$$ for all $$n$$, we have  

$$
P(\{\omega_i\}) \leq P\left(\liminf_{n} E_n^c\right) = 1 - P\left(\limsup_{n} E_n\right) = 0
$$  

We therefore arrive at the same contradiction as in part (a).

---

**Problem 1.2**

Pick $$x \in (0, 1]$$ and let $$J$$ denote an open interval containing $$x$$. Since $$J$$ is open, there exists a pair of indices $$k, n$$ for which $$k \cdot 2^{-n} \in J$$. Label this point $$\omega$$ and observe that  

$$
\frac{1}{n}\sum_{i=1}^\infty d_i(\omega) \to 1
$$  

Therefore $$\omega \in N^c$$. This shows that $$N^c$$ is dense in $$(0, 1]$$.

Now suppose $$J$$ does not contain any points in $$N$$. Then $$J \subseteq N^c$$. But this would imply that $$N^c$$ is not negligible, contradicting Theorem 1.2. Therefore $$J$$ and $$N$$ cannot be disjoint, which implies that $$N$$ is dense in $$(0, 1]$$.

---

**Problem 1.3**

**(a)** Let $$A$$ be a trifling set and fix $$\epsilon > 0$$.
There exists a finite collection of intervals $$\{I_k\}_{k=1}^n$$ that cover $$A$$ and satisfy  
$$\sum_{k = 1}^n |I_k| < \epsilon$$
But since we can do this for any $$\epsilon> 0$$, $$A$$ is negligible.

**(b)** Since $$A$$ is trifling, there exists a finite collection of intervals $$\{(a_k, b_k]\}_{k=1}^n$$ that covers $$A$$ and satisfies  

$$\sum_{k = 1}^n |b_k - a_k| < \frac{\epsilon}{2}$$

Define  

$$
I_k'=\left(a_k - \frac{\epsilon}{2 \cdot n}, b_k\right]
$$  

Pick $$x \in A^-$$. There exists a sequence $$\{x_m\}$$ in $$A$$ for which $$x_m \to x$$.
If $$x$$ were not in any of the closed intervals $$[a_k, b_k]$$, then there would be an open ball around $$x$$ disjoint from all $$(a_k, b_k]$$.
This would contradict that $$x_m \in (a_k, b_k]$$ for large $$m$$.
Thus $$x \in [a_k, b_k] \subset I_k'$$ for some $$k$$.

We conclude that $$\{I_k'\}_{k=1}^n$$ is a finite collection covering $$A^-$$ with total length less than $$\epsilon$$.

**(c)** Let $$A$$ denote the set of rational numbers in $$(0, 1]$$.
Since $$A$$ is countable, it is negligible.

Suppose $$\{(a_k, b_k]\}_{k=1}^n$$ is a finite collection of intervals that covers $$A$$.
WLOG, we can assume $$0 = a_1 \leq a_2 \leq \cdots \leq a_n$$ and $$b_1 \leq b_2 \leq \cdots \leq b_n = 1$$.

Suppose some $$k$$ satisfies $$b_k < a_{k+1}$$. Since the rationals are dense in $$(0, 1]$$, there exists a rational in $$(b_k, a_{k+1}]$$.
Then $$\{(a_k, b_k]\}_{k=1}^n$$ would not cover $$A$$—a contradiction.

So we must have $$b_k \geq a_{k+1}$$ for all $$k=1, \dots, n-1$$.
But then:

$$
\sum_{k=1}^n |(a_k, b_k]| = \sum_{k=1}^n (b_k - a_k) \geq b_n - a_1 = 1
$$  

Thus no such finite collection can have total length less than 1. So $$A$$ is not trifling.

**(d)** By Theorem 1.2, $$N^c$$ is negligible. But in 1.2, we showed that $$N^c$$ is dense in $$(0, 1]$$.
So the closure of $$N^c$$ is $$(0,1]$$ itself, which cannot be negligible by Theorem 1.3.

**(e)** Let $$\{A_k\}_{k=1}^n$$ be trifling sets. Fix $$\epsilon > 0$$.

For each $$k$$, find a finite collection $$\{I_{jk}\}_{j=1}^{J_k}$$ such that  

$$
A_k \subseteq \bigcup_{j=1}^{J_k} I_{jk}, \quad \sum_{j=1}^{J_k} |I_{jk}| < \frac{\epsilon}{n}
$$  

Then  

$$
\bigcup_{k=1}^n A_k \subseteq \bigcup_{k=1}^n \bigcup_{j=1}^{J_k} I_{jk}, \quad \sum_{k=1}^n \sum_{j=1}^{J_k} |I_{jk}| < \epsilon
$$  

Now consider $$\{\{q\}\}_{q \in \mathbb{Q} \cap (0, 1]}$$. Each singleton $$\{q\}$$ is trivially trifling, but we showed in (c) that the full set of rationals is **not** trifling.

---

**Problem 1.4**

**(a)** Let $$C_r(i)$$ denote the set of numbers in $$(0, 1]$$ whose first digit...


