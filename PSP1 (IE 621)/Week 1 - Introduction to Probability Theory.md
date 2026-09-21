
> [!tip]- Random Experiments, Outcomes, and Sample Spaces
> Probability theory is a mathematical framework to study experiments involving **randomness**.
> * **Random Experiment:** A **repeatable** activity where all possible **outcomes** are known in advance, but the exact outcome of any single attempt cannot be predicted with certainty.
> * **Outcome ($\omega$):** A result of a random experiment, denoted by $\omega \in \Omega$.
> * **Sample Space ($\Omega$):** The set containing **all possible** outcomes of a random experiment:
>   $$\Omega = \{ \omega : \omega \text{ is a possible outcome} \}$$
>
>---
>
> > [!tip]- Types of Sample Space
> >
> >   > [!tip]- Finite Sample Space: $|\Omega| < \infty$
> >   > * **Single Coin Toss:** $\Omega = \{H, T\}$
> >   > * **Double Coin Toss:** $\Omega = \{HH, HT, TH, TT\}$
> > 
> >   > [!tip]- Countably Infinite Sample Space: $|\Omega| = |\mathbb{N}_0|$
> >   > * **Daily Coffee Shop Visitors:** $\Omega = \{0, 1, 2, \dots\} = \mathbb{N}_0$
> > 
> >   > [!tip]- Uncountable Sample Space: $|\Omega| = |\mathbb{R}|$ or an interval in $\mathbb{R}$
> >   > * **Breaking a Stick of Unit Length:** $\Omega = [0, 1]$
> >   > * **Stock Price Next Monday:** $\Omega = (0, \infty)$

> [!tip]- Events and Set Operations
> **Event ($E$):** A subset of the sample space ($E \subseteq \Omega$). An event $E$ occurs if the realized outcome lies within $E$, i.e., $\omega \in E$.
> * **Certain Event ($\Omega$):** The entire sample space; always occurs because $\omega \in \Omega$ is guaranteed.
> * **Impossible Event ($\emptyset$):** The empty set; never occurs because no outcome $\omega$ lies in $\emptyset$.
>
>---
>
> > [!tip]- Fundamental Set Operations on Events
> > * **Complement ($A^c$ or $\Omega \setminus A$):** Event $A$ does not occur.
> >   $$A^c = \{ \omega \in \Omega : \omega \notin A \}$$
> > 
> > * **Union ($A \cup B$):** Either event $A$ or event $B$ occurs (or both).
> >   $$A \cup B = \{ \omega \in \Omega : \omega \in A \text{ or } \omega \in B \}$$
> > 
> > * **Intersection ($A \cap B$):** Both events $A$ and $B$ occur simultaneously.
> >   $$A \cap B = \{ \omega \in \Omega : \omega \in A \text{ and } \omega \in B \}$$
> > 
> > * **Set Difference ($A \setminus B$):** Event $A$ occurs, but event $B$ does not occur.
> >   $$A \setminus B = \{ \omega \in \Omega : \omega \in A \text{ and } \omega \notin B \}$$
> > 
> > * **Symmetric Difference ($A \Delta B$):** Either $A$ occurs or $B$ occurs, but not both.
> >   $$A \Delta B = (A \setminus B) \cup (B \setminus A)$$
> > 
> > * **Disjoint / Mutually Exclusive:** Events $A$ and $B$ cannot occur together.
> >   $$A \cap B = \emptyset$$
> > 
> > * **Event Inclusion ($A \subseteq B$):** Event $B$ necessarily occurs whenever event $A$ occurs.
> >   $$A \subseteq B \implies (\omega \in A \implies \omega \in B)$$

---

> [!tip]- Discrete Probability Spaces $(\Omega, p)$
> * **Discrete Sample Space ($\Omega$):** A sample space that is either finite ($|\Omega| < \infty$) or countably infinite ($|\Omega| = |\mathbb{N}_0|$).
> * **Probability Mass Function ($p$):** A function $p: \Omega \rightarrow [0, 1]$ assigning a likelihood or weight to each individual outcome $\omega \in \Omega$.
>
>---
>
> > [!tip]- Axiomatic Requirements & Formal Tuple
> > * **Normalization Axiom:** The sum of probabilities over all outcomes in the sample space must equal $1$:
> >   $$\sum_{\omega \in \Omega} p(\omega) = 1$$
> > 
> > * **Discrete Probability Space:** Formally defined as the ordered tuple $(\Omega, p)$:
> >   $$(\Omega, p)$$
> 
> > [!tip]- Probability of an Event $P(E)$
> > * **Event Probability $P(E)$:** For any event $E \subseteq \Omega$, its probability is the sum of the probabilities of its constituent outcomes:
> >   $$P(E) = \sum_{\omega \in E} p(\omega)$$
> > 
> > * **Properties:**
> >   * $0 \le P(E) \le 1$ for all $E \subseteq \Omega$
> >   * $P(\Omega) = 1$ and $P(\emptyset) = 0$
> 
> > [!tip]- Equally Likely Outcomes (Laplace's Classical Definition)
> > * **Equally Likely Assumption:** If all outcomes in a finite sample space $\Omega$ are equally likely, then for every $\omega \in \Omega$:
> >   $$p(\omega) = \frac{1}{|\Omega|}$$
> > 
> > * **Uniform Probability Formula:** The probability of an event $E \subseteq \Omega$ simplifies to the ratio of favorable outcomes to total outcomes:
> >   $$P(E) = \frac{|E|}{|\Omega|} = \frac{\text{Number of outcomes in } E}{\text{Total number of possible outcomes in } \Omega}$$

> [!tip]- Countable Additivity
> A fundamental property of a probability measure $P$ stating that the probability of a countable union of mutually exclusive (disjoint) events is equal to the sum of their individual probabilities.
>
>---
>
> > [!tip]- Mathematical Formulation
> > * **Disjoint Sequence Condition:** Let $A_1, A_2, A_3, \dots \in \mathcal{F}$ be a sequence of pairwise disjoint events such that:
> >   $$A_i \cap A_j = \emptyset \quad \text{for all } i \neq j$$
> > 
> > * **Additivity Identity:**
> >   $$P\left( \bigcup_{i=1}^\infty A_i \right) = \sum_{i=1}^\infty P(A_i)$$
> 
> > [!tip]- Key Implications & Notes
> > * **Finite Additivity:** Implies that for any finite collection of disjoint events $A_1, \dots, A_n$:
> >   $$P\left( \bigcup_{i=1}^n A_i \right) = \sum_{i=1}^n P(A_i)$$
> > * **Disjoint Union Notation:** Often written using the disjoint union symbol $\bigsqcup$:
> >   $$P\left( \bigsqcup_{i\ge 1} A_i \right) = \sum_{i=1}^\infty P(A_i)$$
>
> > [!tip]- Countable Subadditivity (Boole's Inequality)
> > A fundamental property of probability measures stating that the probability of a countable union of events is **less than or equal to** the sum of their individual probabilities. 
> > * **Mathematical Statement:** For **any** sequence of events $A_1, A_2, A_3, \dots \in \mathcal{F}$ (whether they overlap/intersect or are disjoint): 
> > $$P\left( \bigcup_{i=1}^\infty A_i \right) \le \sum_{i=1}^\infty P(A_i)$$

> [!tip]- Motivation for Measure Theory: Continuous Spaces
> * **Uncountable Sample Space Problem:** When modeling continuous experiments (e.g., breaking a unit stick where $\Omega = [0, 1]$), standard intuition dictates assigning probabilities based on interval lengths:
>   $$P([a, b]) = b - a \quad \text{for all } 0 \le a \le b \le 1$$
> 
> * **Zero Probability of Single Points:** A direct consequence of this uniform length assignment is that every individual outcome has zero probability:
>   $$P(\{\omega\}) = 0 \quad \text{for all } \omega \in \Omega$$
>
>---
>
> > [!tip]- The Mathematical Impossibility & Solution
> > * **Non-Existence Theorem:** It is mathematically impossible to construct a set function $P: 2^{[0, 1]} \rightarrow [0, 1]$ defined on the full power set $2^{[0, 1]}$ (all subsets) that simultaneously satisfies:
> >   1. **Uniform Length Matching:** $P([a, b]) = b - a$
> >   2. **Countable Additivity:** $P\left(\bigcup_{i=1}^\infty A_i\right) = \sum_{i=1}^\infty P(A_i)$ for disjoint sets
> > 
> > * **Measure-Theoretic Solution:** Restrict the domain of $P$ from the power set $2^\Omega$ to a restricted collection of "measurable" subsets called a **$\sigma$-field** ($\mathcal{F}$).

> [!tip]- $\sigma$-Fields ($\sigma$-Algebras)
>A non-empty collection $\mathcal{F}$ of subsets of $\Omega$ that defines the family of all "measurable events" to which probabilities can be validly assigned.
>
>---
>
> > [!tip]- Axiomatic Definition
> > A collection $\mathcal{F} \subseteq 2^\Omega$ is a $\sigma$-field if it satisfies the following three structural conditions:
> > 1. **Boundary Inclusion:** 
> >    $$\emptyset \in \mathcal{F} \quad \text{and} \quad \Omega \in \mathcal{F}$$
> > 2. **Closure Under Complementation:** 
> >    $$A \in \mathcal{F} \implies A^c \in \mathcal{F}$$
> > 3. **Closure Under Countable Unions:** 
> >    $$A_1, A_2, A_3, \dots \in \mathcal{F} \implies \bigcup_{i=1}^\infty A_i \in \mathcal{F}$$
> 
> > [!tip]- Important Examples
> > * **Trivial $\sigma$-Field:** The smallest possible $\sigma$-field on any sample space:
> >   $$\mathcal{F}_{\text{trivial}} = \{\emptyset, \Omega\}$$
> > 
> > * **Single-Event Generated $\sigma$-Field:** For any set $A \subset \Omega$:
> >   $$\mathcal{F}_A = \{\emptyset, \Omega, A, A^c\}$$
> > 
> > * **Power Set $\sigma$-Field:** The largest possible $\sigma$-field (used for discrete sample spaces):
> >   $$\mathcal{F}_{\text{discrete}} = 2^\Omega$$
> > 
> > * **Borel $\sigma$-Field ($\mathcal{B}([0, 1])$):** The non-trivial collection containing all open intervals, closed intervals, and countable unions/intersections of continuous intervals in $[0, 1]$:
> >   $$\mathcal{B}([0, 1]) \subset 2^{[0, 1]}$$

> [!tip]- General Probability Space $(\Omega, \mathcal{F}, P)$
>A formal mathematical framework consisting of a $3-$tuple $(\Omega, \mathcal{F}, P)$ that **models** any random experiment (discrete or continuous).
>
>---
>
> > [!tip]- Components of the Triple $(\Omega, \mathcal{F}, P)$
> >* **Sample Space ($\Omega$):** The set of all possible outcomes.
> >* **$\sigma$-Field ($\mathcal{F}$):** A $\sigma$-field of subsets of $\Omega$ defining the set of all valid, measurable events.
> >* **Probability Measure ($P$):** A set function $P: \mathcal{F} \rightarrow [0, 1]$ mapping each event in $\mathcal{F}$ to a real value in $[0, 1]$.
> 
> > [!tip]- Kolmogorov's Axioms for $P$
> > * **Non-negativity:** $$P(A) \ge 0, \forall A \in \mathcal{F}$$
> >* **Normalization:** 
> >$$P(\emptyset) = 0 \quad \text{and} \quad P(\Omega) = 1$$
> >
> >* **Countable Additivity:** For any sequence of pairwise disjoint events $A_1, A_2, A_3, \dots \in \mathcal{F}$ where $A_i \cap A_j = \emptyset$ for $i \neq j$:
>   >$$P\left( \bigcup_{i=1}^\infty A_i \right) = \sum_{i=1}^\infty P(A_i)$$
> 
> > [!tip]- Lebesgue Measure $(\lambda)$
> >* **Continuous Uniform Space:** For $\Omega = [0, 1]$ and the Borel $\sigma$-field $\mathcal{B}([0, 1])$, the unique probability measure assigning length to intervals is called the **Lebesgue measure** ($\lambda$):
>  > $$\lambda([a, b]) = b - a \quad \text{for all } 0 \le a \le b \le 1$$
> >
> >* **Formal Continuous Probability Space:** Formally denoted as:
> > $$([0, 1], \mathcal{B}([0, 1]), \lambda)$$

> [!tip]- Elementary Properties of Probability Measures $(P)$
> **Context:** Let $(\Omega, \mathcal{F}, P)$ be a probability space and let $A, B \in \mathcal{F}$ be events.
> 
> > [!tip]- Property 1: Complement Rule
> > * **Statement:** $P(A^c) = 1 - P(A)$
> > * **Proof Sketch:** $A$ and $A^c$ are disjoint ($A \cap A^c = \emptyset$) and $A \cup A^c = \Omega$. By normalization and additivity:
> >   $$1 = P(\Omega) = P(A \cup A^c) = P(A) + P(A^c)$$
> 
> > [!tip]- Property 2: Monotonicity
> > * **Statement:** If $A \subseteq B$, then $P(B) = P(A) + P(B \setminus A) \ge P(A)$
> > * **Proof Sketch:** Since $A \subset B$, $B$ can be written as the disjoint union $B = A \sqcup (B \setminus A)$. By additivity and non-negativity of $P$:
> >   $$P(B) = P(A) + P(B \setminus A) \ge P(A)$$
> 
> > [!tip]- Property 3: Two-Set Inclusion-Exclusion
> > * **Statement:** $P(A \cup B) = P(A) + P(B) - P(A \cap B)$
> > * **Proof Sketch:** 
> >   * Since $A \subset A \cup B$, Property 2 gives $P(A \cup B) = P(A) + P((A \cup B) \setminus A)$.
> >   * Decomposing $B$ into disjoint components gives $B = (A \cap B) \sqcup ((A \cup B) \setminus A)$, so $P(B) = P(A \cap B) + P((A \cup B) \setminus A)$.
> >   * Rearranging and substituting for $P((A \cup B) \setminus A)$ yields the result.

---

> [!tip]- Frequentist Approach to Probability
> **Core Philosophy:** Probability is the long-run **relative frequency** of an outcome when an experiment is repeated infinitely under identical conditions.
>
>---
>
> > [!tip]- Mathematical Formulation
> > * **Relative Frequency:** Let $N$ be the total number of independent trials, and let $N(\omega)$ be the number of times outcome $\omega$ occurs. The relative frequency is:
> >   $$\text{Relative Frequency} = \frac{N(\omega)}{N}$$
> > 
> > * **Limit Definition:** As $N \to \infty$, the relative frequency approaches a stable constant, which is defined as the probability assignment $p(\omega)$:
> >   $$p(\omega) := \lim_{N \to \infty} \frac{N(\omega)}{N}$$
> 
> > [!tip]- Key Examples
> > * **Fair Coin Toss:** Repeating a fair coin toss millions of times yields a ratio of Heads $\frac{N(H)}{N} \to \frac{1}{2}$, setting $p(H) = p(T) = \frac{1}{2}$.
> > * **Fair Die Roll:** For $\Omega = \{1, 2, 3, 4, 5, 6\}$, each face appears $\sim \frac{1}{6}$ of the time in the long run, setting $p(\omega) = \frac{1}{6}$ for all $\omega \in \Omega$.
> > * **First Heads in Repeated Coin Tosses:** Measuring how many trials $n$ it takes to see the first Heads yields $p(n) = \frac{1}{2^n}$ based on the long-run pattern $T T \dots T H$.

> [!tip]- De Morgan's Laws
> Fundamental set identities used for manipulating and simplifying complements of combined **events**.
>
>---
>
> > [!tip]- Two-Set Formulation
> > * **Complement of Union:** The complement of a union is the intersection of the complements:
> >   $$(A \cup B)^c = A^c \cap B^c$$
> > * **Complement of Intersection:** The complement of an intersection is the union of the complements:
> >   $$(A \cap B)^c = A^c \cup B^c$$
> 
> > [!tip]- General Countable Formulation
> > $$\left( \bigcup_{i=1}^\infty A_i \right)^c = \bigcap_{i=1}^\infty A_i^c \quad \text{and} \quad \left( \bigcap_{i=1}^\infty A_i \right)^c = \bigcup_{i=1}^\infty A_i^c$$

> [!tip]- Inclusion-Exclusion Principle
>A rule **extending** probability calculations to arbitrary (potentially non-disjoint) events by correcting for **overcounted** outcomes in **intersections**.
>
>---
>
> > [!tip]- Two-Event Case
> > $$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$
> 
> > [!tip]- Three-Event Case
> > $$P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(A \cap B) - P(A \cap C) - P(B \cap C) + P(A \cap B \cap C)$$

> [!tip]- Non-Measurable Sets: Why $\mathcal{F} \neq 2^\Omega$
> **The Core Paradox:** On continuous spaces like $\Omega = [0, 1]$, we cannot assign a consistent probability (or length) to *every possible subset* (the power set $2^\Omega$).
>
>---
>
> > [!tip]- Intuitive Breakdown: The Banach–Tarski / Vitali Paradox
> > * **The 3 Incompatible Desires:** We want a probability measure $P$ on $[0, 1]$ that satisfies three reasonable properties for all subsets:
> >   1. **Length-Matching:** Intervals have expected lengths ($P([0, 0.5]) = 0.5$).
> >   2. **Translation Invariance:** Shifting a set left or right does not change its total probability.
> >   3. **Countable Additivity:** The probability of a disjoint union is the sum of their individual probabilities.
> > 
> > * **The Breaking Point (Vitali Set):** Using the Axiom of Choice, we can slice $[0, 1]$ into infinitely many disjoint pieces that are all exact shifted copies of one another (a **Vitali set**).
> >   * If $P(\text{piece}) = 0$, then by countable additivity, $P([0, 1]) = 0 + 0 + \dots = 0$ (Contradiction! It must be $1$).
> >   * If $P(\text{piece}) > 0$, then adding infinitely many equal positive values forces $P([0, 1]) = \infty$ (Contradiction! It cannot exceed 1).
> 
> > [!tip]- Resolution: Measure Theory
> > * **The Solution:** We accept that "pathological" or fractal-like sets exist that simply do not have a defined probability.
> > * **Restricting the Domain:** We restrict valid events to a well-behaved collection of subsets called a **$\sigma$-field** $\mathcal{F}$ (such as the Borel $\sigma$-field $\mathcal{B}([0, 1])$), which includes all reasonable sets (intervals, points, countable unions) while excluding non-measurable sets.

---

> [!tip]- The Birthday Problem
> **Problem Statement:** In a group of $n$ randomly chosen people, what is the probability $P(E)$ that at least two people share the same birthday? (Assuming $d = 365$ equally likely days in a year and independent birthdays).
>
>---
>
> > [!tip]- Complementary Calculation
> > * **Strategy:** Calculate the probability of the complement event $E^c$ (that all $n$ people have distinct birthdays) and subtract from 1:
> >   $$P(E) = 1 - P(E^c)$$
> > 
> > * **Derivation:**
> >   * Total possible birthday assignments: $|\Omega| = d^n = 365^n$
> >   * Favorable assignments with all distinct birthdays: $|E^c| = d \times (d-1) \times \dots \times (d-n+1) = \frac{d!}{(d-n)!}$
> >   $$P(E^c) = \frac{d \times (d-1) \times \dots \times (d-n+1)}{d^n} = \prod_{k=0}^{n-1} \left(1 - \frac{k}{d}\right)$$
> >   $$P(E) = 1 - \prod_{k=0}^{n-1} \left(1 - \frac{k}{d}\right)$$
> > 
> > * **Counterintuitive Result:** For $n = 23$ people, $P(E) \approx 0.5073$ ($>50\%$ chance). For $n = 57$, $P(E) \approx 0.990$ ($99\%$ chance).
> 
> > [!tip]- Connection to Balls-in-Bins Model
> > * **Abstraction:** The Birthday Problem is a classic instance of throwing balls uniformly at random into bins:
> >   * **Balls ($n$):** The $n$ people.
> >   * **Bins ($d$):** The $d = 365$ days of the year.
> > 
> > * **Collision Threshold:** Asking for at least two people with the same birthday is equivalent to finding the probability of at least one **bin collision** (a bin containing $\ge 2$ balls).












