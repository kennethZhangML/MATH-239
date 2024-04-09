# Chapter 5: Trees

## 5.1 Trees
- **Definition 5.1.1:** A tree is a connected graph with no cycles.
- **Definition 5.1.2:** A forest is a graph with no cycles.
- **Lemma 5.1.3:** If $u$ and $v$ are vertices in a tree $T$, then there is a unique $u, v$-path in $T$.
- **Lemma 5.1.4:** Every edge of a tree $T$ is a bridge.
- **Theorem 5.1.5:** If $T$ is a tree, then $|E(T)| = |V(T)| - 1$.
- **Corollary 5.1.6:** If $G$ is a forest with $k$ components, then $|E(G)| = |V(G)| - k$.
- **Definition 5.1.7:** A leaf in a tree is a vertex of degree 1.
- **Theorem 5.1.8:** A tree with at least two vertices has at least two leaves.

## 5.2 Spanning Trees
- **Theorem 5.2.1:** A graph $G$ is connected if and only if it has a spanning tree.
- **Corollary 5.2.2:** If $G$ is connected, with $p$ vertices and $q = p - 1$ edges, then $G$ is a tree.
- **Theorem 5.2.3:** If $T$ is a spanning tree of $G$ and $e$ is an edge not in $T$, then $T + e$ contains exactly one cycle $C$. Moreover, if $e'$ is any edge on $C$, then $T + e - e'$ is also a spanning tree of $G$.
- **Theorem 5.2.4:** If $T$ is a spanning tree of $G$ and $e$ is an edge in $T$, then $T - e$ has 2 components. If $e'$ is in the cut induced by one of the components, then $T - e + e'$ is also a spanning tree of $G$.

## 5.3 Characterizing Bipartite Graphs
- **Lemma 5.3.1:** An odd cycle is not bipartite.
- **Theorem 5.3.2:** A graph is bipartite if and only if it has no odd cycles.

## 5.4 Breadth-First Search
- **Lemma 5.4.3:** The vertices enter a breadth-first search tree in non-decreasing order of level.
- **Theorem 5.4.4 (The primary property of breadth-first search):** In a connected graph with a breadth-first search tree, each non-tree edge in the graph joins vertices that are at most one level apart in the search tree (of course, each tree edge joins vertices that are exactly one level apart).

## 5.5 Applications of Breadth-First Search
- **Theorem 5.5.1:** A connected graph $G$ with breadth-first search tree $T$ has an odd cycle if and only if it has a non-tree edge joining vertices at the same level in $T$.
- **Theorem 5.5.2:** The length of a shortest path from $u$ to $v$ in a connected graph $G$ is equal to the level of $v$ in any breadth-first search tree of $G$ with $u$ as the root.

## 5.6 Minimum Spanning Tree
- **Theorem 5.6.1:** Prim’s algorithm produces a minimum spanning tree for $G$.
