## Env State
---
- Agent senses: collect information about the env at a point in time
	- Let us assume we have the state of the world $s_t$ at time $t$

- Given $s_t$, our agent must produce an action $a_t$ (also at time $t$).
- World transitions to new state $s_{t + 1}$
	- If static, world transitions to $s_{t + 1}$ after $a_{t}$ is made
	- If dynamic, world may have made transition before $a_t$ was made.

## Agents that Search
---
- For now, let's assume the state of the world is unstructured
	- Book uses term atomic: meaning state contains no internal structure

- Lets consider goal agents
	- Agents equipped with goal function
	- Remember: goal function $g(s_t)v \to \mathbb{B}$

- How can we use the goal function to decide actions?

## Worlds with Known States
---
- Lets consider worlds where all states are known beforehand
- Construct graph of states $G_{env} = (V_{env}, E_{env})$
	- $V_{env} =$ set of all states in the world
	- $(u, v) \in E_{env}$ (undirected) if there exists an action which transitions $u$ to $v$

- Example: Maze solving in a grid world
	- State determined by position of player (and position of obstacles).
	- Actions: {up, down, left, right}

## Uninformed (Blind) Search Strategies
---
### Breadth First Search (BFS)
- Start at source vertex
	- Then visit all **neighbors**                                                     1st neighborhood $N_1 (src)$ 
	- Then visit all **neighbor's neighbors**                            2nd neighborhood $N_2 (src)$ 
	- Then visit all **neighbor's neighbor's neighbors**   3rd neighborhood $N_3 (src)$ 
	- ...
	- Stop when you reach the goal vertex

- Key: Only explore **simple paths**2

### Problem with BFS
- Current form does not work with action costs, i.e. weighted edges.
- Tons of memory, $O(|V|^2)$
	- Need to store all edges: $|E| \leq |V|^2$
- BFS is blind

### Depth First Search
- Recursively probe "deep" into paths.
	- Can also implement with a stack
- Finding simple paths: do not expand a node that is already visited
	- Algorithm has unbounded time if not.
- NOT optimal: returns first path found. Not guaranteed to find shortest path.
- Much better memory complexity: $O(|V|^2)$ worst case
- Can bind depth (hyperparameter): depth limited search
	- Called diameter of state space
- Iterative deepening DFS:
	- Gradually increase depth limit and rerun DFS (diameter = 0, 1, 2, ...)
	- Stop when first solution is found
	- Better average memory complexity.
	- Optimal when path cost is monotonically-increasing as function of vertex depth.
### Problems with DFS
- Path it finds may not be optimal
- Just guarantees a path exists
- DFS is blind

### Dijkstra's Algorithm
- Modification of BFS
- Key idea:
	- Shortest paths **contain** shortest paths

- BFS has right spirit
- Neighbors don't necessarily correspond to longer paths.
- Idea:
	- Keep collection of paths we've explored so far
	- Expand the smallest one
		- Wherever that path leads, that's the shortest path to there/
			- If it wasn't we would have seen shortest path before this one.
		- Expand path = visit neighbors of path
		- Examine neighbors:
			- If the neighbor is brand new: Add to collection
			- If a path to the neighbor already exists:
				- Is the path we just found better?
					- If so, forget older version. If not, forget new path.

- Pros:
	- Works with arbitrary positive edge weights.

- Cons:
	- Still **blind**
	- Not feasible for large graphs $O(|E| + |V|\log |V|)$ runtime, $O(|V| + |E|)$ memory.

### Making Dijkstra Less Blind
- Only a single goal state
	- If more than one: add an artificial goal state

- Design Goal:
	- Make Dijkstra's algorithm **aware** of goal state
	- Choose to expand paths that lead "towards" the goal
	- Rather than sort by true path cost (i.e. known path cost)
		- Sort by **estimated** path cost from src -> goal.

- How to estimate the path cost from src -> goal?
	- Utility function!

## Utilities and Estimating Cost to Goal
---
- Utility function estimates path cost from a vertex to the goal.
- Total estimated cost from src -> goal = true path cost + estimated cost.

- Warning: When we get a shortest path so far:
	- Dijkstra claims that's the correct answer (to wherever that path leads)
	- Are we breaking that by sorting by src -> goal cost.

## Utility Constraints
---
- Cost function = path cost + utility cost (heuristic)
- As long as utility is **admissible** and **consistent**: A* is optimal:
	- Admissible = never overestimates the true cost (i.e. utility is optimistic)
	- Consistent = Triangle inequality but for action spaces: $$f(u) \leq c(u,a,v) + f(v)$$ where $f(u)$ is the cost of vertex $u$, $f(v)$ is the cost of vertex $v$, and $c(u, a, v)$ is the cost of using action $a$ to transition from $u$ to $v$.
- Every consistent utility is admissible.

## The A* Algorithm
---
- Mostly a modification of Dijkstra's Algorithm.
	- Get shortest path so far based on total estimated cost src -> goal
	- Everything else is the same.

- Dijkstra's algorithm where path comparison is done via src -> goal
	- Rather than true path cost (Dijkstra)

- **Warning**: Utility (heuristic) needs to be engineered **for every world**
	- Consistency is determined on a **world-by-world basis**.