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
$actions(s)$ returns the set of actions that can be executed in state $s$.
```
## Transition Model
A description of what state results from performing any applicable action in any state.
```
$results(s, a)$ returns the state resulting from performing action a in state $s$.
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
## Uninformed Search
Search strategy that uses no problem-specific knowledge
## Informed Search
Search strategy that uses problem-specific knowledge to find solutions more efficiently
## Greedy best-first Search
Search algorithm that expands the node that closest to the goal, as estimated by a heuristic function h(n)
## A* Search
Search algorithm that expands node with lowest value of $g(n) + h(n)$

$g(n)$ = cost to reach node
$h(n)$ = estimated cost to goal

Optimal if:
- $h(n)$ is admissible (never overestimates the true cost), and:
- $h(n)$ is consistent (for every node $n$ and successor $n$' with step cost $c$, $h(n) <= h(n') + c$)
## Adversarial Search
A competing search, such as an enemy in a game
## Minimax
In terms of tic-tac-toe:
- $MAX (X)$ aims to maximize score.
- $MIN (O)$ aims to minimize score.
### Given a state $s$:
- $MAX$ picks action $a$ in $actions(s)$ that produces the highest value of $min-value(result(s, a))$
- $MIN$ picks action $a$ in $actions(s)$ that produces the smallest value of $max-value(result(s, a))$

```
function max_value(state):
  if terminal(state):
    return utility(state)
  v = -infinity
  for action in actions(state):
    v = max(v, min-value(result(state, action)))
  return v
```
## Alpha-Beta Pruning
- Saves computation by pruning off states that cannot return the desired value
## Depth-Limited Minimax
- After a certain number of moves, stop and not consider additional moves
## Evaluation Function
function that estimates the expected utility of the game from a given state
