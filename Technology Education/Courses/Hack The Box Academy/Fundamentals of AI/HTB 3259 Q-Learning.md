# Q-Learning

Q-learning is a model-free reinforcement learning algorithm that develops optimal policy implementation via q-values.

A Q-Value represents the expected cumulative reward an agent can obtain by taking specific actions during a given state and then following the optimal policy after. Q-Learning is the way that cars with automated driving features learn the roads and rules for driving.

A Q-Table is one of the main components of Q-learning as it stores all Q-values for all possible state-action pairs. This is a lookup table that guides the agent's decision making processes.

The rows of a Q-table represent the states.

The columns of a Q-table represent the actions.

Each cell of the Q-table holds the Q-value for pursuing a specific action in a specific state.

Q-values are updated via the Q-Learning update rule that is abased on the Bellman equation:

>Q(s, a) = Q(s, a) + a \* \[r + y \* max(Q(s', a')) - Q(s, a)]

- Q(s, a) is the current Q-value for taking action a in state s.
- a is the learning rate that determines the weight assigned to new information.
- r is the reward recieved after taking action a from state s.
- Y (gamma) is the discount factor that determines the importance of future rewards.
- max(Q(s', a')) is the maximum Q-value of the next state s' and any action a'

The iterative steps for utilizing Q-learning are below:

1. Initialization - the q-table is initialized with arbitrary values or all zeroes, occasionally some knowledge is provided.
2. Choosing Actions - the agent selects an action while balancing exploration and exploitation. This ensures that the agent will continue to explore instead of continuously seeking known rewards.
3. Observe Actions - the agent performs actions and observes ensuing consequences. This may includes new states during transitions as well as the immediate reward or punishment recieved from the environment. This is how the agent determines the effectiveness of it's actions.
4. Update Q-values - the state-action pair is modified based on the update rule that incorporated the received and estimated future rewards from the news state.
5. Update State - the agent updates the current state to the new state it transitioned to after taking an action. This prepares the model for the next stage of the algorithm.
6. Iteration - previous steps are repeated until the Q-values reach their optimal values and determined an effective policy for the agent. Alternatively a predefined stopping condition might be developed during this time.

Due to the iterative nature of this process, policies are continuously refined to improve decision making over time and generate more cumulative rewards over the life of the agent.

#### Dilemma

The main problem with Q-learning is finding a balance between exploration and exploitation.