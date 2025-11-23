# Agent–Environment Interaction

**<span style="font-size:1.5em;">Agent–Environment Interaction</span>**

Reinforcement Learning is built around continuous interaction between an agent and an environment. At each time step $t$, the agent observes a state $s_t$ and selects an action $a_t$. The environment responds with a reward $r_{t+1}$ and a new state $s_{t+1}$.

This interaction forms a trajectory:

$$
s_t \rightarrow a_t \rightarrow r_{t+1} \rightarrow s_{t+1} \rightarrow a_{t+1} \rightarrow \dots
$$

The agent’s objective is to choose actions that maximize long-term return, not just immediate reward.  
The environment defines the consequences of actions, transitioning from one state to another and generating reward signals.

The loop consists of:

1. **Observation:** agent receives state $s_t$  
2. **Action:** agent selects $a_t$  
3. **Transition:** environment moves to $s_{t+1}$  
4. **Reward:** environment outputs $r_{t+1}$  

The agent improves its behavior by analyzing the experienced transitions and rewards. Over time, this iterative interaction allows the agent to learn effective strategies for achieving high cumulative reward.
