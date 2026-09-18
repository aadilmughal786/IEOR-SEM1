**Graph operations** refer to ways in which new graphs can be constructed from existing ones.

These operations help in graph **decomposition, transformation, and combination**, and are essential in areas such as **network design, algorithm analysis, and optimization**.

---

| **Operation**                                 | **Definition**                                                                              |
| --------------------------------------------- | ------------------------------------------------------------------------------------------- |
| **Union <br>($G_1 \cup G_2$)**                | The graph containing all vertices and edges of $G_1$ and $G_2$.                             |
| **Intersection <br>($G_1 \cap G_2$)**         | The graph containing only the common vertices and edges of $G_1$ and $G_2$.                 |
| **Difference <br>($G_1 - G_2$)**              | The graph containing edges present in $G_1$ but not in $G_2$.                               |
| **Complement <br>($\overline{G}$)**           | A graph where edges exist between vertices **not connected** in $G$.                        |
| **Cartesian Product <br>($G_1 \square G_2$)** | A graph where vertices are pairs $(u,v)$ and edges exist if either coordinate is adjacent.  |
| **Tensor Product <br>($G_1 \times G_2$)**     | A graph where vertices are pairs $(u,v)$, and edges exist if both coordinates are adjacent. |
| **Strong Product <br>($G_1 \boxtimes G_2$)**  | Combination of **Cartesian** and **Tensor** products.                                       |
| **Line Graph <br>($L(G)$)**                   | A graph where each edge in $G$ becomes a vertex in $L(G)$.                                  |
| **Subdivision <br>($S(G)$)**                  | A graph where edges are split by inserting new vertices.                                    |
| **Graph Power <br>($G^k$)**                   | A graph where vertices are connected if they have a path of at most length $k$.             |

