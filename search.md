# Search
## Agent
Entity that perceives its environment and acts upon that environment.
## State
A confirguration of the agent and its environment.
## Initial State
The state in which the agent begins.
## Actions
Choices that can be made in a state.
```
actions(s) returns the set of actions that can be executed in state s.
```
## Transition Model
A description of what state results from performing any applicable action in any state.
```
results(s, a) returns the state resulting from performing action a in state s.
```
## State Space
The set of all states reachable from the initial state by any sequence of actions.
## Goal Test
Way to determine whether a given state is a goal state.
## Path Cost
Numerical cost associated with a given path.
## Search Problems
- Initial State
- Actions
- Transition Model
- Goal Test
- Path Cost Function
## Solution
A sequence of actions that leads from the initial state to a goal state.
## Optimal Solution
A solution that has the lowest path cost among all solutions.
## Node
A data structure that keeps track of:
- A state
- A parent (node that generated this node)
- An action (action applited to parent to get node)
- A path cost (from initial state to node)
