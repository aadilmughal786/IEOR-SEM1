
#### 1 Partially Ordered Set

>[!tip] POSet
>A relation $R$ on a set $S$ is called a partial ordering or partial order if it is **reflexive**, **antisymmetric**, and **transitive**.
>
>A set $S$ together with a partial ordering $R$ is called a partially ordered set, or poset, and is denoted by $(S, R)$.

The word **_partial_** is used to indicate that not every pair of elements needs to be **_comparable_**; that is, there may be pairs for which neither element precedes the other. 

---

>[!tip] TOSet
>Partial orders further generalize **total orders**, in which every pair is comparable.

`Okey!`
![[Pasted image 20240315153406.png]]

---

| ![[Pasted image 20240903131116.png]] | ![[Pasted image 20240903131145.png]] |
| ------------------------------------ | ------------------------------------ |


#### 2 Digraph Of a Relation

👉 **digraph** is short for **directed graph**.

Let $A=\{0,1,2,3\},$ and let $R={(0,0),(0,3),(1,2),(2,1),(3,2),(2,0)}$

![[Pasted image 20240315154254.png]]

---

The actual location of the vertices in a digraph is immaterial. The main idea is to place the vertices in such a way that the graph is easy to read. After drawing a rough-draft graph of a relation, we may decide to relocate the vertices so that the final result will be neater.

![[Pasted image 20240315154509.png]]

#### 3 Hasse Diagrams

It is a graphical representation of a **poset**. It omits edges implied by **reflexivity**, **transitivity** and placing “smaller” elements lower on the diagram instead of using arrows.

`Nice`
![[Pasted image 20240609234909.png]]

>[!tip] Note
>A smaller element is one that is "lower" in the diagram compared to the element it is related to. If there is a directed edge from vertex $a$ to vertex $b$, it means $a \leq b$ in the poset.


#### 4 Well-Ordered Set

A **well-ordered set** is a special type of totally ordered set in which every non-empty subset has a least element.

>[!tip] Least Element
>An element $m$ such that $m \leq x$ for all $x$ in the subset.

| Property          | Poset                    | Toset                    | Well-Ordered Set                                 |
| ----------------- | ------------------------ | ------------------------ | ------------------------------------------------ |
| **Reflexive**     | Yes                      | Yes                      | Yes                                              |
| **Antisymmetric** | Yes                      | Yes                      | Yes                                              |
| **Transitive**    | Yes                      | Yes                      | Yes                                              |
| **Comparability** | Not required             | Every pair is comparable | Every pair is<br>comparable                      |
| **Least Element** | Not required             | Not required             | Every non-empty subset has a **_least element_** |


#### 5 Maximal and Minimal Elements


>[!tip] Maximal and Minimal
>An element of a poset is called **_maximal_** if it is not less than any element of the poset.
>Similarly, an element of a poset is called **_minimal_** if it is not greater than any element of the poset.

Maximal and minimal elements are easy to spot 👀 using a Hasse diagram. They are the “top” and “bottom” elements in the diagram.

---

>[!Question]
>Which elements of the poset $\{2, 4, 5, 10, 12, 20, 25\}$ with the divisibility relation $|$ are maximal, and which are minimal?

![[Pasted image 20240610113252.png]]

The Hasse diagram in Figure for this poset shows that the maximal elements are $12$, $20$, and $25$, and the minimal elements are $2$ and $5$.

As this example shows, a poset can have more than one maximal element and more than one minimal element.

---

>[!tip] Greatest and Least Element
>Sometimes there is an element in a poset that is greater than every other element. Such an element is called the **_greatest element_**. 
>
>Likewise, an element is called the **_least element_** if it is less than all the other elements in the poset.

`Example`
![[Pasted image 20240610113504.png]]

| Hasse Diagram | Least Element | Greatest Element |
|---------------|---------------|------------------|
| (a)           | $a$           | None             |
| (b)           | None          | None             |
| (c)           | None          | $d$              |
| (d)           | $a$           | $d$              |

---

>[!tip] Upper and Lower Bound (subset)
>Sometimes it is possible to find an element that is greater than or equal to all the elements in a **_subset_** $A$ of a poset $(S, \preceq)$. If $u$ is an element of $S$ such that $a \preceq u$ for all elements $a \in A$, then $u$ is called an **_upper bound_** of $A$.
>
>Likewise, there may be an element less than or equal to all the elements in $A$. If $l$ is an element of $S$ such that $l \preceq a$ for all elements $a \in A$, then $l$ is called a **_lower bound_** of $A$.

`Example`
![[Pasted image 20240610114615.png]]

>[!Question]
>Find the lower and upper bounds of the subsets $\{a, b, c\}$, $\{j, h\}$, and $\{a, c, d, f\}$ in the poset with the Hasse diagram shown in Figure.

| Set            | Upper Bounds   | Lower Bounds         |
| -------------- | -------------- | -------------------- |
| $\{a, b, c\}$    | $\{e, f, j, h\}$ | $\{a\}$                |
| $\{j, h\}$       | $\{\}$           | $\{a, b, c, d, e, f\}$ |
| $\{a, c, d, f\}$ | $\{f, h, j\}$    | $\{a\}$                |

---

The element $x$ is called the **_least upper bound_** of the **subset** $A$ if $x$ is an upper bound that is less than every other upper bound of $A$. Because there is only one such element, if it exists, it makes sense to call this element **_the_** least upper bound.

Similarly, the element $y$ is called the **_greatest lower bound_** of $A$ if $y$ is a lower bound of $A$ and $z \preceq y$ whenever $z$ is a lower bound of $A$. The greatest lower bound of $A$ is unique if it exists.

>[!tip] Note
>The greatest lower bound and least upper bound of a subset $A$ are denoted by $\text{glb}(A)$ and $\text{lub}(A)$, respectively.

---

>[!Question] 
>Find the greatest lower bound and least upper bound of the sets $\{3, 9, 12\}$ and $\{1, 2, 4, 5, 10\}$, if they exist, in the poset $(\mathbb{Z}^+, |)$.

| Set                | Greatest Lower Bound | Least Upper Bound |
| ------------------ | -------------------- | ----------------- |
| $\{3, 9, 12\}$       | $\{3\}$                | $\{36\}$            |
| $\{1, 2, 4, 5, 10\}$ | $\{1\}$                | $\{20\}$            |


#### 6 Lattice

A partially ordered set in which **_every pair_** of elements has both a least upper bound(**_supremum_**) and the greatest lower bound (**_infimum_**) is called a lattice.

>[!tip] Note
>**_Additionally_**, a lattice can be described using two binary operations: 
>1. **_join_**
>2. **_meet_**.

---

Let $L$ be a partially ordered set (poset) where for **_any two elements_** $a,b∈L$, there exists a **_unique_** supremum denoted by $a∨b$ and a **_unique_** infimum denoted by $a∧b$.

$$\implies \begin{cases}
\forall x,y\in L,GLB(x,y)\ne \phi \\
 \\
\forall x,y\in L,LUB(x,y)\ne \phi \\
\end{cases}$$


| Definition          | Symbol      |
| ------------------- | ----------- |
| Greatest Element    | $1$         |
| Least Element       | $0$         |
| Complement of $x$   | $\neg x$    |
| Join of $x$ and $y$ | $x \lor y$  |
| Meet of $x$ and $y$ | $x \land y$ |

---

>[!tip] Note
>When determining if a partially ordered set forms a lattice, always pay attention to **_non-comparable elements_**. While **_comparable elements_** naturally possess `LUB` and `GLB`

**_Example→_** Is this given Hasse diagram a lattice?

![[Pasted image 20240315192101.png]]

👉 Just focus on pairs of non-comparable elements

$e,f \implies GLB(e,f)=b\quad LUP(e,f)=g$
$c,d \implies GLB(c,d)=b\quad LUP(c,d)=g$
$e,d \implies GLB(e,d)=b\quad LUP(e,d)=g$
$c,f \implies GLB(c,f)=b\quad LUP(c,f)=g$

So here for every pair we have **_unique_** `GLB` and `LUP` **_exist_**. So this poset is lattice.

---

>[!tip] Note
>It is important to note that **_not all partially ordered sets are lattices_**.

![[Pasted image 20240315162651.png]]

☝️**Non-lattice poset:** ${\displaystyle c}$ and ${\displaystyle d}$ have no common upper bound.


![[Pasted image 20240315163001.png]]

☝️ **_Non-lattice poset:_** ${\displaystyle b}$ and ${\displaystyle c}$ have common upper bounds ${\displaystyle d,e,}$ and ${\displaystyle f,}$ but none of them is the least upper bound.

---

`Example 1`
![[Pasted image 20240315193359.png]]

`Example 2`
![[Pasted image 20240315193451.png]]

`Example 3`
![[Pasted image 20240315193525.png]]

`Example 4`
![[Pasted image 20240315194605.png]]

`Example 5`
![[Pasted image 20240315194626.png]]

`Example 6`
![[Pasted image 20240315194710.png]]

`Example 7`
![[Pasted image 20240315194848.png]]

---

$\implies x∨x=x \to LUB(x,x)=x$
$\implies x∧x=x \to GUB(x,x)=x$

$\implies x ∨ y=y∨x$
$\implies x ∧ y=y∧x$

$\implies x∨(y∨z)=(x∨y)∨z$
$\implies x∧(y∧z)=(x∧y)∧z$

$\implies x∨(x∧y)=x$
$\implies x∧(x∨y)=x$

---

**1) Complete Lattice**

A complete lattice is a lattice in which every subset has both a supremum (join) and an infimum (meet).

`Example`
![[Pasted image 20240610143322.png]]

---

**2) Bounded Lattice**

A bounded lattice is a lattice that has both a greatest element$(1)$ (top element) and a least element$(0)$ (bottom element).

>Every finite lattice has a least element and a greatest element.

- $x \lor 1 = 1$
- $x \land 1 = x$
- $x \lor 0 = x$
- $x \land 0 = 0$

---

**3) Complemented Lattice**

A lattice is called complemented if every element $x$ has a complement, denoted as $\neg x$, such that $x \lor \neg x = 1$ and $x \land \neg x = 0$.

---

**4) Distributive Lattice**

Lattices do not necessarily follow the distributive law. Lattices that satisfy the distributive law are called distributive lattices.

$$\forall x,y,z\in L\implies \begin{cases}
x \lor (y \land z) = (x \lor y) \land (x \lor z) \\ \\
x \land (y \lor z) = (x \land y) \lor (x \land z) \\
\end{cases}$$





