# Markov Decision Processes (MDPs)

**<span style="font-size:1.5em;">Markov Decision Processes (MDPs)</span>**

A Markov Decision Process provides the formal framework for reinforcement learning.  
An MDP consists of:

- a set of states $\mathcal{S}$  
- a set of actions $\mathcal{A}$  
- a transition function  
  $$
  p(s' \mid s, a)
  $$
- a reward function  
  $$
  r(s, a) = \mathbb{E}[R_{t+1} \mid s_t = s, a_t = a]
  $$
- a discount factor $\gamma \in [0, 1]$

The **Markov property** states that the next state depends only on the current state and action:

$$
p(s_{t+1} \mid s_t, a_t, s_{t-1}, a_{t-1}, \dots) = p(s_{t+1} \mid s_t, a_t)
$$

An MDP defines how the environment evolves when actions are taken.  
The agent uses this structure to reason about the long-term consequences of its decisions.

A trajectory in an MDP follows:

$$
s_t, a_t, r_{t+1}, s_{t+1}, a_{t+1}, \dots
$$

MDPs serve as the mathematical backbone of RL, enabling precise definitions of return, value functions, and optimal policies.
