# 2. Defining Multi-Party Computation

## 2.1 Notations and Conventions

- Secure multi-party computation == MPC
- There exists a secure communication channels between the partcipants
- *m* is the message and *k* is the key
- Encryption = *Enc(m, k)*
- Decryption = *Dec(m, k)*
- Protocol participants = *parties*, *players* = *P1*, *P2*, ...
- Adversary = *A*;
- Neglijable function = $v : \mathbb{N} \rightarrow \mathbb{R}$
  - $\forall p,\ v(n) < \frac{1}{p(n)}$ where p is a polynomial
- **Computational security parameters** = how hard is for an adversary to break a scheme
- **Computational** security parameter = $k$
  - hardness of the problems that can be broken by an offline adversary
  - this can be seen as the key size
  - you want this you be low, a high value means the adversary is "strong"
- **Statistical** security parameter = $\sigma$
  - hardness of a given attack
  - measures the probability for the adversary to break the schema

    Security is violated with probability $2^{-\sigma} + v(k)$.

    When adversaries have infinite resources $k \rightarrow \inf$, the requirement is that $v = 0$.

- uniformly random sampling = $\in_{R}$
  - Ex: sample using the randomized algorithm A on input x = $v \in_{R}A(x)$
- $D_1,D_2$ two distributions that are *indistinguishable*
  $$
  \forall\ algorithms\ A \ \exists v\ \Longrightarrow Pr[A(D_1(n)) = 1] - Pr[A(D_2(n)) = 1] \le v(n)
  $$
  - **Computational indistinguishability**, only non-uniform, polynomial-time algorithms A
  - **Statistical indistinguishability**
    - The new bound becomes the *statistical distance* or the total variation distance between the distribution (**EXTRA**: x should be a countable set)
    $$

        \Delta(D_1(n), D_2(n)) = \frac{1}{2}\sum_{x}|Pr[x=D_1(n)] - Pr[x=D_2(n)]|
    $$
    - Extra: how the total variation is related to the [Kullback-Leibler divergence](https://www.countbayesie.com/blog/2017/5/9/kullback-leibler-divergence-explained):
    $$
         \Delta(D_1(n), D_2(n)) \le \sqrt{\frac{1}{2}D_{KL}(D_1(n)||D_2(n))}
    $$