# Reinforcement Learning Algorithms

Reinforcement Learning (RL) is a unique aspect of machine learning where the agent learns by having interactions with the chosen environment. 

This is distinctly different from other methods because learning is achieved through trial and error that is guided by feedback via rewards and penalties. How the agent responds to the feedback is how policies are developed.

A Policy is a strategy the agent uses to maximize cumulative rewards over time.

There are two types of Reinforcement Learning algorithms, Model-Based and Model-Free agents.

Model-Based Reinforcement Learning is when the agent develops a model of the environment and uses it to predict future states. You can think of this as being able to view a map before you solve a maze - this reduces the amount of trial and error needed to develop policies.

Model-Free Reinforcement Learning is when the agent learns from experience, relying solely on trial and error to determine policies. The model explores different pathing in an explorative way to determine reward and punishment distributions.

#### Core Concepts

An Agent is the learner and decision-maker within reinforcement learning systems. This agent interacts with the environment 

The State is the current conditions or situation within the environment. It is like a snapshot of the available information and includes aspects of the environment like agent position, object positions, or known variables.

Actions are decisions made by the agent that affect the environment, and the environment responds to actions made by the agent. 

A Reward is feedback from the environment that reflects desirability of outcome after agent actions. This is rendered as a scalar value that is positive, negative, or zero.

A Policy is a strategy or mapping algorithm to describe relationships between actions and feedback. This is the decision making part of the process and determines the action an agent will make in a given state. 

Deterministic Policy is when the same action is always selected for a given state.

Stochastic Policy is when actions are selected based on known probabilities. 

A Value Function is used to estimate long-term values of being in a specific state or choosing specific actions. This is often a vital part of RL algorithms that guides agents towards choosing actions that lead to higher positive feedback.

State-Value Functions estimate the expected cumulative rewards from starting in a given state and following particular policies.

Action-Value Functions estimate expected cumulative rewards from taking specific actions in a given state and then following a particular policy.

The Discount Factor (y) is a parameter for determining future rewards value in the present, ranging in value between 0 and 1 - where 1 favors long-term rewards and 0 favors short-term rewards.

Episodic tasks are when the agent interacts with the environment in episodes that end in a terminal state.

Continuous Tasks continue indefinitely and have no determined end.

### Related:
- [Hack The Box Academy](https://academy.hackthebox.com/ "Hack The Box Academy Home page")
- [HTB Reinforcement Learning Algorithms](https://academy.hackthebox.com/module/290/section/3258 "HTB Reinforcement Learning Algorithms")