# Search
## Agent
Entity that perceives its environment and acts upon that environment.
## State
A configuration of the agent and its environment.
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
- An action (action applied to parent to get node)
- A path cost (from initial state to node)
## Approach
- Start with a frontier that contains the initial state.
- Repeat:
  - If the frontier empty, then there is no solution.
  - Remove a node from the frontier.
  - If that node contains a goal state, return the solution.
  - Expand that node, add resulting nodes to the frontier.
## Revised Approach
- Start with a frontier that contains the initial state.
- Start with an empty explored set.
- Repeat:
  - If the frontier is empty, then no solution.
  - Remove a node from the frontier.
  - If node contains goal state, return the solution.
  - Add the node to the explored set.
  - Expand node, add resulting nodes to the frontier if they aren't already in the frontier or the explored set.
## Stack
Last-in first-out data type
## Depth-first Search
Search algorithm that always expands the deepest node in the frontier
## Breadth-first Search
Search algorithm that always expands the shallowest node in the frontier
## Queue
First-in first-out data type
