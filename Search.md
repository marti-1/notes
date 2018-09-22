# Search

* **Informed search** -- some sort of heuristic can tell us how worthy is expansion of some further node.
* **Uninformed search** -- we have node idea about which is the best node to expand next.

**Measuring problem solving performance**

* Completeness -- is the algorithm guaranteed to find a solution when there is one?
* Optimality
* Time complexity
* Space complexity

## Search algorithms

* BFS:
    - complete -- guaranteed to find a solution if the branching factor is finite;
    - exponential time and space complexity;
    - optimal if action costs are nondecreasing;
* Uniform Search Strategies:
    - informed BFS?
    - optimal;
    - exponential in time and space complexity?
* DFS:
    - space complexity is low;
    - not guaranteed to find a solution if there are branches with infinite depth;

### Greedy BFS
Using a greedy algorithm, expand the first successor of the parent. After a successor is generated:

* If the successor's heuristic is better than its parent, the successor is set at the front of the queue (with the parent reinserted directly behind it), and the loop restarts.
* Else, the successor is inserted into the queue (in a location determined by its heuristic value). The procedure will evaluate the remaining successors (if any) of the parent.

Properties:

* Complete -- only if we can recognize loops;
* Non-optimal

    
### A*

```
f(n) = g(n) + h(n)
```

where g(n) is cost to getting to node `n` and `h(n)` is heuristic estimate to the node leading to the goal.

A* chooses what to explore next based on `f(n)`.

Provided that the heuristic function h(n) satisfies certain conditions, A* search is both complete and optimal.

**Conditions for optimality**:

* admissibility -- if heuristic always underestimates the cost -- the solution is guaranteed to be optimal; we are minimizing subject to it, since it is smaller than the possible best solution, we are guaranteed to visit the most optimal node.
* consistency:

```
h(n) ≤ c(n, a, n′) + h(n′)
```

where `c` is cost of action `a` and `n'` is successor state to `n`. `n'` can't have cheaper cost + cost to get to it from `n` than cost of `n` state. Think **triangle inequality** in case of geometric tasks.