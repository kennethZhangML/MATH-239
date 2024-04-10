## Chapter 7: Planar Graphs

### 7.1 Planarity

#### Definition 7.1.1
A graph $G$ is **planar** if it has a drawing in the plane so that its edges intersect only at their ends, and so that no two vertices coincide. The actual drawing is called a **planar embedding** of $G$, or a **planar map**.

- For example, the 3-cube, previously considered in Figure 4.12, is a planar graph, with a planar embedding given in Figure 7.1.

#### Planar Embedding Details
A planar embedding partitions the plane into connected regions called **faces**; one of these regions, called the **outer face**, is unbounded.

- Consider a planar embedding of a connected graph $G$. The subgraph formed by the vertices and edges in a face is called the **boundary of the face**.
- Two faces are adjacent if they are incident with a common edge.
- As one moves around the entire perimeter of a face $f$, one encounters the vertices and edges in a fixed order, say $W_f = (v_0, e_1, v_1, e_2, v_2, ..., v_{n-1}, e_n, v_n)$ where $v_n = v_0$. This sequence is a closed walk of the graph $G$, and is called the **boundary walk** of face $f$.
- The number of edges in the boundary walk $W_f$ is called the **degree of the face $f$**.

For example, in a given diagram:
- $\deg(f1) = 6$,
- $\deg(f2) = 3$,
- $\deg(f3) = 5$,
- $\deg(f4) = 14$.

#### Corollary 7.1.3
If the connected graph $G$ has a planar embedding with $f$ faces, the average degree of a face in the embedding is $\frac{2|E(G)|}{f}$.

### 7.2 Euler’s Formula

Every planar embedding of a given connected planar graph has the same number of faces, a fact that we can deduce from Euler’s Formula.

#### Theorem 7.2.1 (Euler’s Formula)
Let $G$ be a connected graph with $p$ vertices and $q$ edges. If $G$ has a planar embedding with $f$ faces, then:

$p - q + f = 2$

**Proof:**
- We prove this result by induction on $q$. Given $G$ is connected, it has a spanning tree, so $q \geq p - 1$.
- Base Case: As a tree has no cycles, any planar embedding of a tree has just one face, and the theorem holds.
- Inductive Step: Assume true for graphs with fewer than $q$ edges. If removing an edge $e$ that is not a bridge (hence does not disconnect the graph), we reduce the number of faces by one, maintaining the balance required by Euler's formula.

### 7.3 Stereographic Projection

#### Theorem 7.3.1
A graph is planar if and only if it can be drawn on the surface of a sphere.

- **Stereographic Projection:** Transforms a planar embedding on the plane to a spherical embedding, making all faces bounded and maintaining planarity.
- **Details:** If embedding $G$ on a sphere, projecting from the sphere to the plane from a point opposite to the point of tangency (point $A$) maps every point uniquely and preserves the planar nature of the graph.

### 7.4 Platonic Solids

#### Theorem 7.4.1
There are exactly five platonic graphs: the tetrahedron, the cube, the octahedron, the dodecahedron, and the icosahedron, corresponding to the only five platonic solids.

#### Lemma 7.4.2
For a planar embedding with $p$ vertices, $q$ edges, and $s$ faces, where each vertex has degree $d \geq 3$ and each face has degree $d' \geq 3$, the pair $(d, d')$ is one of the following:
- $(3, 3)$,
- $(3, 4)$,
- $(4, 3)$,
- $(3, 5)$,
- $(5, 3)$.

**Proof Sketch:**
- Utilize Euler’s formula and face-vertex relationships to derive constraints on $d$ and $d'$.
- Demonstrate that only the above pairs can satisfy these constraints within a planar graph framework.


### 7.5 Nonplanar Graphs

#### Lemma 7.5.1
**Statement:** If $G$ contains a cycle, then in a planar embedding of $G$, the boundary of each face contains a cycle.

**Proof Outline:**
- Given $G$ has a cycle, it implies multiple faces.
- For a face $f$ and adjacent face $g$, consider an edge $e_1 = \{v_0, v_1\}$ incident to both $f$ and $g$.
- Define $H$ as the component in the boundary of $f$ containing $e_1$.
- The boundary walk $W_f$ of $H$ includes $e_1$ precisely once, ensuring $H$ contains a cycle.

#### Lemma 7.5.2
**Statement:** For a planar embedding $G$ with $p$ vertices and $q$ edges, if each face of $G$ has degree at least $d$, then:
$(d-2)q \geq d(p-2)$

**Proof Outline:**
- First handle the connected case: Apply Euler’s Formula where $s = q + 2 - p$ (number of faces).
- For disconnected graphs, convert to a connected planar embedding $G_0$ by adding edges within faces, maintaining planarity and the inequality.

#### Theorem 7.5.3
**Statement:** In a planar graph $G$ with $p \geq 3$ vertices and $q$ edges, $q \leq 3p - 6$.

**Proof Outline:**
- If $G$ is a forest (no cycles), $q \leq p - 1$.
- If $G$ contains a cycle, apply Lemma 7.5.1 and 7.5.2, with the fact that each face has degree at least 3, to show $q \leq 3(p-2)/2 = 3p - 6$.

#### Corollary 7.5.4
**Statement:** $K_5$ is not planar.

**Proof Outline:**
- For $K_5$, $p = 5$ and $q = 10$ (since $K_5$ is a complete graph with 5 vertices).
- If $q \leq 3p - 6$ were true, then $10 \leq 9$, which is false, thus $K_5$ violates the planar graph edge condition.

#### Corollary 7.5.5
**Statement:** A planar graph has a vertex of degree at most five.

**Proof Outline:**
- Derived from the average degree consideration using Theorem 7.5.3.

#### Theorem 7.5.6
**Statement:** In a bipartite planar graph $G$ with $p \geq 3$ vertices and $q$ edges, $q \leq 2p - 4$.

**Proof Outline:**
- If $G$ is a forest, then $q \leq p - 1$ applies.
- For cycles, no 3-length cycles (triangles) are in bipartite graphs, ensuring each cycle and hence each face has length at least 4.
- This gives a stricter bound as $q \leq 2(p-2)/2 = 2p - 4$.

#### Lemma 7.5.7
**Statement:** $K_{3,3}$ is not planar.

**Proof Outline:**
- For $K_{3,3}$, $p = 6$ and $q = 9$.
- If $q \leq 2p - 4$ were valid, then $9 \leq 8$, which is false, thus $K_{3,3}$ does not meet the bipartite planar graph condition.

### 7.7 Colouring and Planar Graphs

#### Definition 7.7.1
**k-colouring of a graph G:** A function from $V(G)$ to a set of size $k$ (whose elements are called colours), so that adjacent vertices always have different colours. A graph with a k-colouring is called a k-colourable graph.

For example, see a 4-colouring of a graph where the colours are the integers 1, 2, 3, 4, and the colour assigned to each vertex is written beside the vertex in the diagram (Figure 7.15).

#### Theorem 7.7.2
**Statement:** A graph is 2-colourable if and only if it is bipartite.

**Proof:**
- **If a graph has bipartition (A, B):** Assign one colour to all vertices in $A$, and the second colour to all vertices in $B$; no edge joins two vertices of the same colour since all edges join a vertex in $A$ to a vertex in $B$.
- **Conversely, if a graph has a 2-colouring:** Let the vertices of one colour be set $A$, and the vertices of the second colour be set $B$. Then $(A, B)$ is a bipartition since all edges join vertices of different colours.

#### Theorem 7.7.3
**Statement:** $K_n$ is $n$-colourable, and not $k$-colourable for any $k < n$.

**Proof:**
- Any graph on $n$ vertices is $n$-colourable by assigning different colours to the vertices, so no two vertices have the same colour.
- $K_n$ is not $k$-colourable for any $k < n$, since such a colouring would assign the same colour to some pair of adjacent vertices. But all pairs of vertices are adjacent in $K_n$, so this would violate the colouring rule.

#### Theorem 7.7.4
**Statement:** Every planar graph is 6-colourable.

**Proof:**
- Use induction on the number $p$ of vertices. Base case: all graphs on one vertex are 6-colourable.
- Inductive step: Assume true for $p \leq k$. For a planar graph $G$ on $p = k+1$ vertices, from Corollary 7.5.5, $G$ has a vertex $v$ with $\deg(v) \leq 5$. Removing $v$ and its incident edges gives a graph $G_0$ with $k$ vertices, which is 6-colourable by hypothesis. There are at most 5 different colours used by the vertices adjacent to $v$ in $G$, so there is at least one of the 6 colours remaining to colour $v$ such that it differs from all its adjacent vertices in $G$.

#### Definition 7.7.5
**Edge-contraction $G/e$:** For an edge $e = \{x, y\}$ in $G$, $G/e$ is obtained by identifying $x$ and $y$ into a new vertex $z$, and adjusting edges accordingly. $G/e$ is planar whenever $G$ is.

#### Theorem 7.7.6
**Statement:** Every planar graph is 5-colourable.

**Proof:**
- Use induction on the number $p$ of vertices. Base case: a graph on one vertex is 5-colourable.
- Inductive step: Assume true for $p \leq k$. For $G$ on $p = k+1$ vertices, if $G$ has a vertex of degree 4 or less, proceed as in the 6-colour theorem. Otherwise, $G$ has a vertex of degree 5. Contract edges to reduce vertex count and apply the hypothesis. The 5-colouring of the reduced graph extends to $G$ by properly colouring the contracted vertices and the vertex of degree 5.

#### Theorem 7.7.7
**Statement:** Every planar graph is 4-colourable.

**Remark:** The proof of the Four Colour Theorem involves complex inductions and computer-assisted verifications, covering many cases. It is a necessary condition for planarity but not sufficient, as shown by the example of $K_{3,3}$, which is 4-colourable but not planar.
