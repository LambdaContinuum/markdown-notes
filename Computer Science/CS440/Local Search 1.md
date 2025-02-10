## Problems with Classical Search
---
- Blind search + Informed Search are nice:
	- optimality (most algorithms)
	- Find solution to problem
		- Path to the goal (from start)

-  What happens if we don't care about the path?

- Not appropriate for large-scale worlds
- Does not model some real-world problems

## Optimization
---
- Find the best state according to an objective state $$s = \text{argmin}_{s\in W} f(s) \text{ OR } s = \text{argmax}_{s \in W} f(s)$$
- Can always convert a min <-> max
- Classical search is optimization (for paths):
	- Path cost is an objective function
	- Find the path (from source to dest) with min cost.

## How to Optimize 101
---
- Geometric angle
	- For every state, use objective to get value of state ("objective value")
		- Draw the curve.
	- Algorithms "move" along the surface of the curve. 