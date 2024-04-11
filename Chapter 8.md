## Chapter 8: Matchings

### 8.1 Matching

A **matching** in a graph $G$ is a set $M$ of edges of $G$ such that no two edges in $M$ share a common vertex. The term "matching" refers to how $M$ pairs adjacent vertices. For example, if $M$ includes an edge $e$, then both vertices incident to $e$ are said to be *saturated* by $M$. Every graph contains at least the empty set as a matching, which is trivially a matching of size zero.

**Maximum Matching:** A largest possible matching in $G$. Not all graphs contain a *perfect matching* (a matching that saturates all vertices), but determining the presence of a maximum matching is a well-studied problem, especially in bipartite graphs.

**Bipartite Matching Problem:**
- Consider a set $A$ of workers and a set $B$ of jobs.
- Each job can be done by certain workers.
- Objective: Assign as many jobs as possible to workers, with each worker and each job assigned at most once.

This is equivalent to finding a maximum matching in a bipartite graph constructed such that there is a vertex for each worker and job, and an edge between a worker and a job if the worker can perform the job.

**Alternating and Augmenting Paths:**
- An *alternating path* with respect to a matching $M$ is a path that alternates between edges in $M$ and not in $M$.
- An *augmenting path* is an alternating path that starts and ends with vertices not saturated by $M$, which can be used to increase the size of the matching.

#### Lemma 8.1.1
If there exists an augmenting path with respect to $M$, then $M$ is not a maximum matching.

### 8.2 Covers

A **cover** of $G$ is a set of vertices such that every edge of $G$ has at least one end in the cover. Finding small covers and large matchings are dual problems in some sense, notably in bipartite graphs.

#### Lemma 8.2.1
If $M$ is a matching and $C$ is a cover, then $|M| \leq |C|$.

This lemma implies that the size of any matching is a lower bound on the size of any cover.

#### Lemma 8.2.2
If $M$ is a matching and $C$ is a cover with $|M| = |C|$, then $M$ is a maximum matching and $C$ is a minimum cover.

### 8.3 König’s Theorem

**König's Theorem** states that in bipartite graphs, the size of the maximum matching is equal to the size of the minimum vertex cover. This is a powerful result because it provides a constructive way to think about problems involving networks of preferences or capabilities.

#### Theorem 8.3.1 (König’s Theorem)
In a bipartite graph, the maximum size of a matching is equal to the minimum size of a cover.

### Applications of König’s Theorem

König's Theorem is particularly useful in operations research and network design, where problems can often be modeled as bipartite graphs—e.g., assigning tasks to resources or distributing goods to locations.

**Hall's Theorem** is a specific application of König’s Theorem, which deals with the existence of perfect matchings in bipartite graphs and provides conditions under which all vertices in set $A$ (one part of the bipartition $A, B$) are matched.

### Algorithm for Maximum Matching in Bipartite Graphs

The XY-construction combined with the concepts of alternating paths provides a method to find maximum matchings. This algorithm is iterative and modifies the matching by finding augmenting paths until no further improvements can be made.
# Bipartite Matching Algorithm

## Algorithm Steps:

### Step 0:
- Let $M$ be any matching of $G$.

### Step 1:
- Initialize $X^* = \{v \in A : v \text{ is unsaturated}\}$.
- Initialize $Y^* = \emptyset$.
- Initialize $pr(v)$ as undefined for all $v \in V(G)$.

### Step 2:
- For each vertex $v \in B \setminus Y^\*$ such that there is an edge $\{u, v\}$ with $u \in X^\*$:
  - Add $v$ to $Y^*$.
  - Set $pr(v) = u$.

### Step 3:
- If Step 2 added no vertex to $Y^*$:
  - Return the maximum matching $M$ and the minimum cover $C = Y^* \cup (A \setminus X^\*)$.
  - Stop.

## Additional Notes:

- The algorithm constructs sets $X^*$ and $Y^*$ iteratively, finding vertices reachable by alternating paths.
- Vertices are added to $X^*$ and $Y^*$ in levels, similar to breadth-first search.
- When creating an even level, the edge $\{u, v\}$ must be a matching edge.
- If an unsaturated vertex $v$ in $Y^*$ is found, an augmenting path can be traced from $v$ to a vertex $w \in X^*$.
- There is no need to construct the rest of $X^*$ and $Y^*$ in this case; the augmenting path can immediately be used to find a larger matching.

### Conclusion

Matching theory not only provides fundamental insights into graph theory but also supports various practical applications, from job assignments in human resources to task scheduling in computational systems. König's and Hall's theorems give powerful tools for analyzing and solving such problems efficiently.
