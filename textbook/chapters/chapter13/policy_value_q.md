# Policy, Value Function, and Q-Function

**<span style="font-size:1.5em;">Policy, Value Function, and Q-Function</span>**

A **policy** $\pi$ defines the agent’s behavior.  
It specifies what action to take in each state:

$$
\pi(a \mid s) = \text{Prob}(a_t = a \mid s_t = s)
$$

The goal of RL is to find a policy that maximizes expected return.

---

**State Value Function**

The value function measures how good a state is under policy $\pi$:

$$
V^{\pi}(s) = \mathbb{E}_{\pi}[\, G_t \mid s_t = s \,]
$$

Using the MDP structure, this satisfies the **Bellman expectation equation**:

$$
V^{\pi}(s) = 
\sum_{a} \pi(a \mid s)
\sum_{s'} p(s' \mid s, a)\,
\big( r(s,a) + \gamma V^{\pi}(s') \big)
$$

---

**Action-Value Function (Q-Function)**

The Q-function evaluates the expected return when taking action $a$ in state $s$ and then following policy $\pi$:

$$
Q^{\pi}(s,a) = \mathbb{E}_{\pi}[\, G_t \mid s_t=s, a_t=a \,]
$$

Its Bellman equation is:

$$
Q^{\pi}(s,a) =
\sum_{s'} p(s' \mid s,a)\,
\big( r(s,a) + \gamma 
\sum_{a'} \pi(a' \mid s')\, Q^{\pi}(s', a') \big)
$$

---

**Optimal Value Functions**

The optimal value of a state is:

$$
V^{*}(s) = \max_{\pi} V^{\pi}(s)
$$

The optimal action-value function is:

$$
Q^{*}(s,a) = \max_{\pi} Q^{\pi}(s,a)
$$

These satisfy the **Bellman optimality equations**:

$$
V^{*}(s) = 
\max_{a} \sum_{s'} p(s' \mid s,a)\,
\big( r(s,a) + \gamma V^{*}(s') \big)
$$

$$
Q^{*}(s,a) =
\sum_{s'} p(s' \mid s,a)
\big( r(s,a) + \gamma \max_{a'} Q^{*}(s',a') \big)
$$

Value functions and Q-functions form the foundation for evaluating policies and improving them toward optimal behavior.
