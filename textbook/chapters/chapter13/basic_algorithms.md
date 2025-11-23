# Basic RL Algorithms

**<span style="font-size:1.5em;">Basic RL Algorithms</span>**

Reinforcement Learning algorithms aim to evaluate policies, improve them, or directly learn optimal value functions.  
Most classical RL methods are based on the Bellman equations and iterative updates.

---

**Policy Evaluation**

Given a policy $\pi$, policy evaluation computes its value function:

$$
V^{\pi}(s) = 
\sum_{a} \pi(a \mid s) 
\sum_{s'} p(s' \mid s,a)\,
\big(r(s,a) + \gamma V^{\pi}(s')\big)
$$

Iterative policy evaluation updates:

$$
V_{k+1}(s) =
\sum_{a} \pi(a \mid s)
\sum_{s'} p(s' \mid s,a)\,
\big( r(s,a) + \gamma V_k(s') \big)
$$

---

**Policy Improvement**

Given value estimates, a new policy is formed by choosing the best action:

$$
\pi_{\text{new}}(s) = 
\arg\max_{a}\;
\sum_{s'} p(s' \mid s,a)\,
\big( r(s,a) + \gamma V^{\pi}(s') \big)
$$

---

**Policy Iteration**

Policy iteration alternates between evaluation and improvement:

1. Evaluate current policy  
2. Improve policy  
3. Repeat until convergence

This process converges to the optimal policy $\pi^{*}$.

---

**Value Iteration**

Value iteration combines evaluation and improvement in a single update:

$$
V_{k+1}(s) = 
\max_{a} \sum_{s'} p(s' \mid s,a)\,
\big( r(s,a) + \gamma V_k(s') \big)
$$

Once $V^{*}$ converges, the optimal policy is:

$$
\pi^{*}(s) = \arg\max_{a}
\sum_{s'} p(s' \mid s,a)\,
\big( r(s,a) + \gamma V^{*}(s') \big)
$$

---

**Q-Learning**

Q-learning learns the optimal action-value function directly through experience:

$$
Q_{t+1}(s_t, a_t) =
Q_t(s_t, a_t)
+ \alpha
\left[
r_{t+1}
+ \gamma \max_{a'} Q_t(s_{t+1}, a')
- Q_t(s_t, a_t)
\right]
$$

The learned Q-values approximate $Q^{*}$, and the greedy policy:

$$
\pi(s) = \arg\max_a Q(s,a)
$$

becomes optimal as learning converges.

Basic RL algorithms provide the foundation for learning policies that maximize long-term return.
