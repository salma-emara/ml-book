# Chapter 13: Introduction to Reinforcement Learning (RL)

**<span style="font-size:1.5em;">Introduction</span>**

Reinforcement Learning focuses on how an agent can learn to act in an environment to maximize long-term reward.  
Unlike supervised learning, where correct outputs are given, RL relies on interaction: the agent observes a state, takes an action, and receives a reward along with the next state.

The goal of RL is to learn a behavior, or **policy**, that maximizes expected return. Formally, the interaction is modeled as a sequence:

$$
s_t,\, a_t,\, r_{t+1},\, s_{t+1},\, a_{t+1},\, \dots
$$

The agent must balance immediate and future rewards. Future returns are commonly represented using discounted sums:

$$
G_t = \sum_{k=0}^{\infty} \gamma^k r_{t+k+1}, \qquad 0 \le \gamma \le 1
$$

Reinforcement learning provides systematic ways to evaluate policies, compute value functions, and improve decision-making over time.

This chapter introduces the foundations of RL and prepares the reader for the following sections:

13.1 Agent–Environment Interaction  
13.2 Markov Decision Processes (MDPs)  
13.3 Reward Signal and Return  
13.4 Policy, Value Function, and Q-Function  
13.5 Exploration vs. Exploitation Trade-off  
13.6 Applications of RL  
13.7 Basic RL Algorithms
