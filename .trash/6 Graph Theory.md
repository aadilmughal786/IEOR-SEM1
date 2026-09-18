
#### 1 Intro

>[!tip] Graph
>A graph is an **ordered pair** $G = (V, E)$ consisting of a **nonempty set** $V$ (called the **_vertices_**) and a set $E$ (called the **_edges_**) of two-element subsets of $V\text{.}$

---

>[!tip] Isomorphic
>Graphs that are basically the same (but perhaps **not equal**) are called **isomorphic**.
>
>![[Pasted image 20240216173934.png]]
>
>An isomorphism between two graphs $G_1$ and $G_2$ is a **bijection** $f:V_1 \to V_2$ between the vertices of the graphs such that $\{a,b\}$ is an edge in $G_1$ if and only if $\{f(a), f(b)\}$ is an edge in $G_2\text{.}$
>
>In this case, we write $G_1 \cong G_2\text{.}$

---

>[!tip] Subgraph vs. Induced Subgraph
>We say that $G' = (V', E')$ is a **subgraph** of $G = (V, E)\text{,}$ and write$(G' \subseteq G\text{,}$ provided $V' \subseteq V$ and $E' \subseteq E\text{.}$
>
>We say that $G' = (V', E')$ is an **induced subgraph** of $G = (V, E)$ provided $V' \subseteq V$ and every edge in $E$ whose vertices are still in $V'$ is also an edge in $E'\text{.}$


Notice that every **induced subgraph** is also an **ordinary subgraph**, **but not conversely**. Think of a subgraph as the result of deleting some vertices and edges from the larger graph. For the subgraph to be an induced subgraph, we can still delete vertices, but now we only delete those edges that included the deleted vertices.

---

>[!tip] Handshake Lemma
>In any graph, the sum of the degrees of vertices in the graph is always twice the number of edges.
>$$\begin{equation*} \sum_{v\in V} d(v) = 2e\text{.}\end{equation*}$$


>[!tip] Proposition
>
>In any graph, the number of vertices with odd degree must be even.


---

>[!tip] Bipartite vs. Complete Bipartite Graph
>We say a graph is **bipartite** if the vertices can be divided into two sets, $A$ and $B\text{,}$ with no two vertices in $A$ adjacent and no two vertices in $B$ adjacent.
>
>The vertices in $A$ can be adjacent to some or all of the vertices in $B\text{.}$ If each vertex in $A$ is adjacent to all the vertices in $B\text{,}$ then the graph is a **complete bipartite** graph, and gets a special name: $K_{m,n}\text{,}$ where $|A| = m$ and $|B| = n\text{.}$
>
>The graph in the houses and utilities puzzle is $K_{3,3}$


1. Graph is bipartite $⟷$ graph has no **odd length cycles**


---

Some graphs are used more than others, and get special names.

$K_n$ → The **complete graph** on $n$ vertices.

$K_{m,n}$ → The **complete bipartite graph** with sets of $m$ and $n$ vertices.

$C_n$ → The cycle on $n$ vertices, just one big loop.

$P_n$ → The path on $n+1$ vertices (so $n$ edges), just one long path.

![[Pasted image 20240216190812.png]]


---

| **Term**               | **Definition**                                                                                                                                              |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Adjacent**           | Two vertices are adjacent if they are connected by an edge. Two edges are adjacent if they share a vertex.                                                  |
| **Connected**          | A graph is connected if there is a path from any vertex to any other vertex.                                                                                |
| **Chromatic number**   | The minimum number of colors required in a proper vertex coloring of the graph.                                                                             |
| **Degree of a vertex** | The number of edges incident to a vertex.                                                                                                                   |
| **Planar**             | A graph which can be drawn without any edges crossing.                                                                                                      |
| **Tree**               | A connected graph with no cycles. Vertices in a tree with degree $1$ are called leaves. Without the connected requirement, the tree is called a **forest**. |



---

Lets **_minimum_** and **_maximum_** degree denoted as $δ(G)$ and $∆(G)$ respectively.

For any vertex $v$ of graph $G$, we have $\boxed{δ(G) \le deg(v) \le ∆(G)}$

>Minimum possible degree of a vertex is → $0$
>Maximum possible degree of a vertex is → $n-1$

$$\boxed{0 \le δ(G) \le deg(v) \le ∆(G) \le (n-1)}$$
Assuming no **_self loop_** and **_parallel edges_** allowed ☝

---

|    Graph     | Loop | Parallel Edge |
| :----------: | :--: | :-----------: |
| Simple Graph |  ❌   |       ❌       |
| Multi Graph  |  ❌   |       ✅       |
| Psudo Graph  |  ✅   |       ✅       |

We will only focus on **_Simple graphs_**

---

👉 Average degree of graph will be $\boxed{\frac{2e}{n}}$

$$\boxed{0 \le δ(G) \le \left( \frac{2e}{n} \right) \le ∆(G) \le (n-1)}$$

---

1. A **Eulerian Graph** is a graph where we can traverse each edge exactly once.
2. A graph with a **Eulerian Circuit** allows us to start and end at the same vertex while visiting each edge exactly once, requiring all vertices to have an even degree.
3. A graph with a **Eulerian Path** lets you traverse each edge exactly once without necessarily returning to the starting point, and requires exactly zero or two vertices to have an odd degree.



#### 2 Types of Simple Graph


##### 2.1 Complete Graph 

>Represented by $K_{n}$ where  $n\ge{1}$

![[Pasted image 20240202005142.png]]

$$\boxed{δ(G) = ∆(G) =\left( \frac{2e}{n} \right)= (n-1)}$$
Size(**e**) of $K_{n}=\frac{n(n-1)}{2}$

##### 2.2 Regular Graph

A graph $G$ is regular if every vertex of $G$ has the **_same degree_** and called as **_$r$-regular_** if its degree is $r$.
$$\boxed{δ(G) = \left( \frac{2e}{n} \right) = ∆(G) = r}$$

![[Pasted image 20240202011109.png]]


>**_Q_** → are all complete graphs regular graphs?
>A graph is said to be regular if all the vertices are of the same degree. **So a complete graph is always a (n-1)-regular graph**.


##### 2.3 Cycle Graph

>Represented by $C_{n}$ where  $n\ge{3}$

$$\boxed{δ(G) = \left( \frac{2e}{n} \right) = ∆(G) = 2}\to 2-\text{Regular Graph}$$

![[Pasted image 20240202011649.png]]

$\implies \frac{2e}{n}=2$
$\implies e=n$


$p$ : $C_{n}$ is a cycle graph.
$q$ : $n=e$
$p\to q$ : If $C_{n}$ is a cycle graph then $n=e$.

>$q \not\to p$ : If $n =e$ then $C_{n}$ is a cycle graph.

**_Contrapositive_** $\lnot q \to \lnot p$ : If $n\ne e$ then $C_{n}$ is not a cycle graph.


>**Note:** In graph theory, a “cycle graph” specifically refers to a graph that forms a closed loop or circuit. On the other hand, a “graph containing a cycle” simply indicates the presence of at least one cycle within the graph.

##### 2.4 Wheel Graph

>Represented by $W_{n}$ where  $n\ge{4}$

![[Pasted image 20240202014405.png]]

First take $(n-1)$ vertices and create a cycle graph, then put the remaining vertex in the middle and connect it to all $(n-1)$ vertices for the cycle graph.
$$\boxed{e=(n-1)+(n-1)=2(n-1)}$$
>$W_{n} \to e=2(n-1)$
>$e=2(n-1) \not\to W_{n}$

![[Pasted image 20240202020616.png]]


>Degree of center vertex → $(n-1)$
>Degree of other vertices→ $3$

![[Pasted image 20240202015919.png]]

##### 2.5 Complement Graph

Complement of graph $G$ denoted as $\overline{G}$

![[Pasted image 20240202020854.png]]

$\boxed{E(G) + E(\overline{G})=E(K_{n})=\frac{n(n-1)}{2}}$

>The **_empty graph_** of order $n$ is therefore $\overline{K_{n}}$

---

>Self complement graph → $G=\overline{G}$

![[Pasted image 20240202101124.png]]

For a self complement graph $\boxed{e+e=\frac{n(n-1)}{2}\implies e=\frac{n(n-1)}{4}}$

If $n = 6 \implies e = \frac{6\times 5}{4}=7.5 \to \text{ Not valid}$

>So no self complement graph possible for order $6$ graph.

Self complement graph, only possible if and only if
$$
\boxed{n\equiv 0(\text{mod } 4) \text{ Or } (n-1)\equiv 0(\text{mod } 4)}
$$
We can also write as
$$
\boxed{n\equiv 0\text{ or }1(\text{mod } 4)}
$$

---

>$\boxed{a\equiv b (\text{mod n})}$ means → remainder of $a$ and $b$ will be same with respect to $n$.

Or  $a\equiv b (\text{mod n}) \iff rem(a,n)=rem(b,n)$


##### 2.6 Hypercube graph

>Represented by $Q_{n}$ where $n$ is an $n$ bit signal

![[Pasted image 20240202105655.png]]

Total number of vertices in $Q_{n}$ will be → $2^n$

Ok, to find the number of edges we need, let's take $n=3$. Pick any vertex, for example $\boxed{0}\boxed{0}\boxed{1}$. To get the idea of how many edges (degree) this vertex has. If we only change one bit at a time, it will create an edge.
This is not difficult to conclude that every vertex have same degree $n$. Now we can easily find edges.

$\implies 2^n \times n = 2e$
$\implies e = n\times  2^{n-1}$

**_So_**
$n=1 \implies e=1\times 2^{1-1}=1$
$n=2 \implies e=2\times 2^{2-1}=4$
$n=3 \implies e=3\times 2^{3-1}=12$

![[Pasted image 20240202105655.png]]


##### 2.7 Bipartite Graph

>Bi (Two) partition of **_vertices_**

- This graph always has two sets, $X$ and $Y$, with the vertices.
- In this graph, the vertices of set $X$ can only have a connection with the set $Y$.
- We cannot join the vertices within the same set.


![[Pasted image 20240202150044.png]]

Every [tree](https://www.wikiwand.com/en/Tree_(graph_theory) "Tree (graph theory)") is bipartite.
![[Pasted image 20240202150418.png]]

[Cycle graphs](https://www.wikiwand.com/en/Cycle_graph "Cycle graph") with an **even number of vertices** are bipartite.

![[Pasted image 20240202150634.png]]

>It is obvious that if a graph has an **odd length cycle**, then **it cannot be Bipartite**.

---

>[!tip] Note
>In the bipartite graph, the maximum possible number of edges on '$n$' vertices is equal to the $\frac{n^2}{4}={\frac{n}{2}.{\frac{n}{2}}}$


##### 2.8 Complete Bipartite Graph

$\implies K_{m,n}$
$\implies m\times n + n\times m = 2e \implies e=m\times n$

![[Pasted image 20240202153227.png]]

**_Star Graph_** → $K_{1,n-1}$

![[Pasted image 20240202153953.png]]


##### 2.9 Line Graph

$\implies L(G)$

Create edges as vertex and draw the edges if there is common vertex between them.

![[Pasted image 20240202154532.png]]

#### 3 Planar Graphs

When a **connected graph** can be drawn without any edges crossing, it is called **planar**. When a planar graph is drawn in this way, it divides the plane into regions called **faces**.

>Notice that the definition of planar includes the phrase “**it is possible to.**” This means that even if a graph does not look like it is planar, it still might be.

---

For any connected planar graph with $v$ vertices, $e$ edges and $f$ faces, we have
$$\text{Euler's Formula}\implies \boxed{\begin{equation*} v-e + f = 2\text{.} \end{equation*}}$$

---

>Not all graphs are planar. If there are too many edges and too few vertices, then some edges will need to intersect. The smallest **complete graph** where this happens is $K_5\text{.}$ So, $K_5$ is not planar.

![[Pasted image 20240217013322.png]]

The other simplest graph which is not planar is $K_{3,3}$

![[Pasted image 20240217013803.png]]

---

Another area of mathematics where you might have heard the terms “vertex,” “edge,” and “face” is **geometry**.

A **polyhedron** is a geometric solid made up of flat polygonal faces joined at edges and vertices.

We are especially interested in **convex polyhedra**, which means that any line segment connecting two points on the interior of the polyhedron must be entirely contained inside the polyhedron.

Notice for cube that since $8 - 12 + 6 = 2\text{,}$ the vertices, edges and faces of a cube satisfy Euler's formula for planar graphs.

This is not a coincidence. We can represent a cube as a planar graph by projecting the vertices and edges onto the plane. One such projection looks like this:

![[Pasted image 20240217014650.png]]

In fact, **_every_** convex polyhedron can be projected onto the plane without edges crossing.

---

A **cube** is an example of a **convex polyhedron**. It contains $6$ identical squares for its faces, $8$ vertices, and $12$ edges. The cube is a **regular polyhedron** (also known as a Platonic solid) because each face is an identical **regular polygon** and each vertex joins an equal number of faces.

There are exactly four **other** regular polyhedra: the tetrahedron, octahedron, dodecahedron, and icosahedron with $4, 8, 12$ and $20$ faces respectively.

>There are **exactly** five **regular** polyhedra.


#### 4 Trees

One very useful and common approach to studying graph theory is to restrict your focus to graphs of a particular kind. For example, you could try to really understand just complete graphs or just bipartite graphs, instead of trying to understand all graphs in general. That is what we are going to do now, looking at **trees**. 


>[!tip] Tree vs. Forest
>A **tree** is a connected graph containing no cycles.
>
>A **forest** is a graph containing no cycles. Note that this means that a connected forest is a tree.

---

1. A graph $T$ is a tree **if and only if** between every pair of distinct vertices of $T$ there is a **unique** path.
2. A graph $F$ is a forest **if and only if** between any pair of vertices in $F$ there is **at most one** path.
3. Any tree with at least two vertices, has at least two vertices of degree one.
4. Let $T$ be a tree with $v$ vertices and $e$ edges. Then $e = v-1\text{.}$
5. Every tree is a **bipartite graph**.

---

1. Given a connected graph $G\text{,}$ a **spanning tree** of $G$ is a subgraph of $G$ which is a **tree** and includes all the vertices of $G\text{.}$
2. Every connected graph has a spanning tree.


#### 5 DFS and BFS

[Depth First Search Algorithm | DFS Example | Gate Vidyalay](https://www.gatevidyalay.com/depth-first-search-dfs-algorithm/)
[Breadth First Search Algorithm | BFS Example | Gate Vidyalay](https://www.gatevidyalay.com/breadth-first-search-bfs-algorithm/)

---

**Hamiltonian Path:** A Hamiltonian path in a graph is a path that visits each vertex exactly once. Unlike a Hamiltonian cycle, it does not need to start and end at the same vertex.


#### 6 Matching

| **Concept**         | **Description**                                                                                 |
|---------------------|-------------------------------------------------------------------------------------------------|
| **Matching**        | A set of edges with no shared vertices, but not all vertices need to be included.               |
| **Perfect Matching**| A matching where every vertex in the graph is included, and all vertices are paired perfectly.  |


#### 7 Coloring

**Proper Coloring:** In graph theory, a proper coloring is an assignment of colors to the vertices of a graph such that no two adjacent vertices share the same color.

**Chromatic Number:** The chromatic number of a graph is the smallest number of colors needed to achieve a proper coloring of the graph, where no two adjacent vertices share the same color.



#### 8 Graph Representation

WIP

#### 9 Terminologies


1. **Directed Graph:** A graph where edges have a direction, indicating a one-way relationship between vertices.
2. **Undirected Graph:** A graph where edges have no direction, indicating a two-way relationship between vertices.

---

1. **Weighted Graph:** A graph where edges are assigned weights, representing the cost or distance between vertices.
2. **Unweighted Graph:** A graph where edges have no weights, treating all connections equally.

---

1. **Cyclic Graph:** A graph that contains at least one cycle, where a path starts and ends at the same vertex.
2. **Acyclic Graph:** A graph that contains no cycles, meaning no path starts and ends at the same vertex.

---

1. **Component:** In an undirected graph, a subgraph where all vertices are connected, and no connections exist to vertices outside the subgraph.
2. **Strongly Connected Component:** In a directed graph, a subgraph where every vertex is reachable from every other vertex within the subgraph.

---

[Walk in Graph Theory | Path | Trail | Cycle | Circuit | Gate Vidyalay](https://www.gatevidyalay.com/walk-in-graph-theory/)

`Nice`
![[Pasted image 20240828093305.png]]

---

**Topological Sorting (or Ordering):** In graph theory, topological sorting is the linear ordering of vertices in a directed acyclic graph (DAG) such that for every directed edge from vertex $u$ to vertex $v$, $u$ comes before $v$ in the ordering. This process is only possible in a DAG and is often used to schedule tasks where certain tasks must be completed before others.


#### 10 Articulation Point

An **articulation point** (or cut vertex) in a graph is a vertex that, when removed along with its associated edges, increases the number of connected components of the graph.

In other words, it's a critical vertex whose removal would disconnect the graph, making it more fragmented. Articulation points are important in network design and analysis, as they indicate vulnerabilities in the connectivity of the graph.


#### 11 Independent Set

In graph theory, an **independent set** is a set of vertices in a graph, no two of which are adjacent.

This means that there is no edge connecting any pair of vertices within the independent set.

Independent sets are important in various applications, such as resource allocation, where conflicts (represented by edges) must be avoided.


