The AI "Umbrella":
- Search
- Natural Language Processing
- Computer Vision
- Robotics
- Biometrics
- Reinforcement Learning
- All of this falls under Learning Theory


## Our Plan
---
1. Common verbiage
	- Agent
	- World
	- Representation

2. [[Local Search 1|Search]] & Planning
	- [[Search|A* algorithm]] (Generalization of Dijkstra's Algorithm)
	- Tree/graph expansion
	- $\alpha - \beta$  pruning

3. Probabilistic Representation & Problem Solving
	- [[A User's Guide to Bayes Theorem|Bayesian Networks]]
	- Belief

4. Supervised & Reinforcement Learning
	- Decision Trees
	- Neural Networks
	- Reward functions
	- Bellman Equation

5. Special Topics (**If we have time**)


## Agents
---
- An entity in AI which makes decisions on its own behalf is called an **agent**.
- **Agent function:** How the agent works (internally)
- An agent can make multiple decisions at once (and often simultaneously)
- Agents exist in the "digital" realm
- Agents accept data in the "digital" realm and take **actions** in the "digital realm"

## Environment/World
---
- Agent's interact with the physical world through an environment (often called a "world")
- Agents must "sense" their world in order to receive data.
	- i.e. robots have sensors
	- Digital worlds have representations

## Rational Agents
---
- A Rational Agent is an agent that "does the right thing"
	- Evaluated by a performance metric
	- Performance metric examines environment state
	- Agent that produces desired environment states -> rational
		- "For every sequence of environment states, a rational agent selects the action that will optimize the performance given only the states it has seen (so far) and its 'internal knowledge'."
- Rationality is different than omniscience!
	- Rationality optimizes expected performance, omniscience optimizes actual performance

## Task Environment
---
- Rationality requires four things:
	- Performance metric
	- Environment (Desciption/Software/Interface, etc)
	- Agent senses
	- Agent actions

- Task environment is these four attributes as a quadruple.

## Flavors of Task Environments
---
- Fully observable
	- Agent has access to complete state of environments
- Partially observable
	- Some information hidden from agent

- Deterministic
	- Environment's next state completely dependent on action + previous states
- Stochastic
	- Environment's next state is [[Probability Overview|probabilistic]]

- Single Agent
- Multi-Agent
	- Competitive / Cooperative
	- Communication?

- ...

## Flavors of Agents
---
- Simple Reflex Agent
	- Only looks at current env state to decide action
- Model-based Reflex Agent
	- Maintains internal state (agent state) + can use history of env states
- Goal-base Agent
	- Goal function assists agent in making decisions (helps identify favorable states)
- Utility-based Agent
	- Utility function = Internal performance metric....used to assist agent
	- Utility function does not need to match the Task env performance metric
- Learning Agent
	1. Learning element: component that makes adjustments to the Agent
	2. Action element: component that selects external actions
	3. Critic: feedback component (used by the learning element)
	4. Problem generator: component that suggests novel experiences