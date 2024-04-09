# Chapter 4: Graph Theory

## 4.3 Degree
- **Definition 4.3.4:** A complete graph is one in which all pairs of distinct vertices are adjacent.
- **Theorem 4.3.1:** For any graph $G$ we have $\sum_{v \in V(G)} \deg(v) = 2|E(G)|$.
- **Corollary 4.3.2:** The number of vertices of odd degree in a graph is even.
- **Corollary 4.3.3:** The average degree of a vertex in the graph $G$ is $\frac{2|E(G)|}{|V(G)|}$.

## 4.4 Bipartite Graphs
- **Definition 4.4.1:** For $n \geq 0$, the $n$-cube is the graph whose vertices are the $\{0,1\}$-strings of length $n$, and two strings are adjacent if and only if they differ in exactly one position.

## 4.6 Paths and Cycles
- **Definition 4.6.1:** A subgraph of a graph $G$ is a graph whose vertex set is a subset of $V(G)$ and whose edge set is a subset of those edges of $G$ that have both vertices in $U$.
- **Theorem 4.6.2:** If there is a walk from vertex $x$ to vertex $y$ in $G$, then there is a path from $x$ to $y$ in $G$.
- **Corollary 4.6.3:** Let $x, y, z$ be vertices of $G$. If there is a path from $x$ to $y$ in $G$ and a path from $y$ to $z$ in $G$, then there is a path from $x$ to $z$ in $G$.
- **Theorem 4.6.4:** If every vertex in $G$ has degree at least $2$, then $G$ contains a cycle.

## 4.8 Connectedness
- **Theorem 4.8.2:** Let $G$ be a graph and let $v$ be a vertex in $G$. If for each vertex $w$ in $G$ there is a path from $v$ to $w$ in $G$, then $G$ is connected.
- **Definition 4.8.4:** A component of $G$ is a subgraph $C$ of $G$ such that (a) $C$ is connected, (b) No subgraph of $G$ that properly contains $C$ is connected.

## 4.9 Eulerian Circuits
- **Definition 4.9.1:** An Eulerian circuit of a graph $G$ is a closed walk that contains every edge of $G$ exactly once.
- **Theorem 4.9.2:** Let $G$ be a connected graph. Then $G$ has an Eulerian circuit if and only if every vertex has an even degree.

## 4.10 Bridges
- **Definition 4.10.1:** An edge $e$ of $G$ is a bridge if $G-e$ has more components than $G$.
- **Lemma 4.10.2:** If $e = \{x, y\}$ is a bridge of a connected graph $G$, then $G-e$ has precisely two components; furthermore, $x$ and $y$ are in different components.
- **Theorem 4.10.3:** An edge $e$ is a bridge of a graph $G$ if and only if it is not contained in any cycle of $G$.
