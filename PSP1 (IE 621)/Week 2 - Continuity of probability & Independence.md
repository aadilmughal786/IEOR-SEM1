
> [!tip]- Continuity of Probability
> A fundamental property stating that the probability measure $P$ is continuous under limits of monotonic sequences of events.
>
>---
>
> > [!tip]- Monotone Increasing Sequences (Continuity from Below)
> > **Theorem:** Let $A_1 \subseteq A_2 \subseteq A_3 \subseteq \dots$ be an increasing sequence of events in $\mathcal{F}$, and let $$A = \bigcup_{i=1}^\infty A_i = \lim_{n \to \infty} A_n$$ Then:
> >   $$P(A) = P\left( \bigcup_{i=1}^\infty A_i \right) = \lim_{n \to \infty} P(A_n)$$
> 
> > [!tip]- Proof Sketch
> > * This property is essentially equivalent to countable additivity.
> > * Express $A$ as a disjoint union of increments: $A = A_1 \sqcup (A_2 \setminus A_1) \sqcup (A_3 \setminus A_2) \sqcup \dots$
> > * Apply Countable Additivity:
> >   $$P(A) = P(A_1) + \sum_{i=2}^\infty P(A_i \setminus A_{i-1}) = P(A_1) + \lim_{n \to \infty} \sum_{i=2}^n \big(P(A_i) - P(A_{i-1})\big) = \lim_{n \to \infty} P(A_n)$$

---

> [!tip]- Conditional Probability
>- The probability of an event $A$ occurring given that another event $B$ with $P(B) > 0$ has occurred.
>- We want to assign probability to events in $\mathcal{F}$, given the occurrence of another event.
>
>---
>
> > [!tip]- Formal Definition & Frequentist Intuition
> > * **Formula:**
> >   $$P(A \mid B) := \frac{P(A \cap B)}{P(B)}$$
> > * **Frequentist Intuition:** If an experiment is repeated $N$ times, $N(B)$ is the count of occurrences of $B$, and $N(A \cap B)$ is the count where both occur:
> >   $$P(A \mid B) \approx \frac{N(A \cap B)}{N(B)} = \frac{N(A \cap B)/N}{N(B)/N} \xrightarrow{N \to \infty} \frac{P(A \cap B)}{P(B)}$$
> 
> > [!tip]- Two-Child Gender Paradox Example
> > * **Experiment:** Sample space $\Omega = \{GG, GB, BG, BB\}$, each outcome having probability $\frac{1}{4}$.
> > * **Case 1: Given at least one boy ($B_1 = \{GB, BG, BB\}$):**
> >   $$P(BB \mid B_1) = \frac{P(BB \cap B_1)}{P(B_1)} = \frac{P(BB)}{P(B_1)} = \frac{1/4}{3/4} = \frac{1}{3}$$
> > * **Case 2: Given the younger child is a boy ($B_2 = \{GB, BB\}$):**
> >   $$P(BB \mid B_2) = \frac{P(BB \cap B_2)}{P(B_2)} = \frac{P(BB)}{P(B_2)} = \frac{1/4}{1/2} = \frac{1}{2}$$

> [!tip]- Law of Total Probability
>A fundamental rule that computes the total probability of an event $A$ by decomposing it across a collection of exhaustive, mutually exclusive scenarios (a partition of the sample space $\Omega$).
>
>---
>
> > [!tip]- Partition Formulation & Mathematical Derivation
> > * **Partition Definition:** A collection of events $\{B_1, B_2, \dots, B_n\}$ forms a partition of $\Omega$ if the events are pairwise disjoint ($B_i \cap B_j = \emptyset$ for all $i \neq j$) and collectively exhaustive ($\bigcup_{i=1}^n B_i = \Omega$).
> > 
> > * **Intersection Expression (Disjoint Decomposition):** Since $\bigcup_{i=1}^n B_i = \Omega$, we can decompose $A$ into a disjoint union of its intersections with each partition element:
> >   $$A = A \cap \Omega = A \cap \left( \bigcup_{i=1}^n B_i \right) = \bigsqcup_{i=1}^n (A \cap B_i)$$
> > 
> > * **Total Probability Formula:** Applying finite additivity followed by the definition of conditional probability $P(A \cap B_i) = P(A \mid B_i)P(B_i)$ (assuming $P(B_i) > 0$ for all $i$):
> >   $$P(A) = \sum_{i=1}^n P(A \cap B_i) = \sum_{i=1}^n P(A \mid B_i) P(B_i)$$
> 
> > [!tip]- Two-Bin Ball Pick Example
> > * **Setup:** Bin 1 contains 2 White, 3 Blue. Bin 2 contains 3 White, 4 Blue. One ball is picked at random from Bin 1 and transferred to Bin 2. Then, a ball is picked at random from Bin 2.
> > * **Events:** Let $A = \{\text{picked ball from Bin 2 is Blue}\}$ and $B = \{\text{moved ball from Bin 1 is Blue}\}$.
> > * **Partition:** $\{B, B^c\}$ forms a valid partition of $\Omega$, where $B^c = \{\text{moved ball from Bin 1 is White}\}$.
> > * **Calculation:**
> >   * **Prior probabilities:** $P(B) = \frac{3}{5}, \quad P(B^c) = \frac{2}{5}$
> >   * **Conditional probabilities:** $P(A \mid B) = \frac{5}{8}, \quad P(A \mid B^c) = \frac{4}{8} = \frac{1}{2}$
> >   * **Law of Total Probability:**
> >     $$P(A) = P(A \cap B) + P(A \cap B^c) = P(A \mid B)P(B) + P(A \mid B^c)P(B^c)$$
> >     $$P(A) = \left(\frac{5}{8} \times \frac{3}{5}\right) + \left(\frac{1}{2} \times \frac{2}{5}\right) = \frac{3}{8} + \frac{1}{5} = \frac{23}{40}$$
> 
> > [!tip]- Structural Insight: Implicit Probability Spaces
> > In practical problem-solving, we rarely need to explicitly write down every element of $(\Omega, \mathcal{F}, P)$ in detail to calculate probabilities correctly. However, mathematical rigor requires keeping in mind that a formal probability space $(\Omega, \mathcal{F}, P)$ always exists in the background governing these operations.

> [!tip]- Bayes' Theorem vs. Law of Total Probability
> * **Core Distinction:** 
>   * **Law of Total Probability (Forward Reasoning):** Aggregates cause-to-effect probabilities to find the total likelihood of an observed event $A$ by summing over all possible scenarios $B_i$.
>   * **Bayes' Theorem (Inverse Reasoning / Inference):** Reverses the conditional direction to evaluate the probability that a specific underlying cause $B_k$ occurred, *given* that the effect $A$ has already been observed.
>
>---
>
> > [!tip]- Mathematical Formulation
> > * **Bayes' Formula:** For a collection of events $\{B_1, B_2, \dots, B_n\}$ partitioning $\Omega$ with $P(A) > 0$ and $P(B_i) > 0$:
> >   $$P(B_k \mid A) = \frac{P(A \cap B_k)}{P(A)} = \frac{P(A \mid B_k) P(B_k)}{\sum_{i=1}^n P(A \mid B_i) P(B_i)}$$
> > 
> > * **Component Terminology:**
> >   * **Prior Probability $P(B_k)$:** The initial probability of scenario $B_k$ before observing outcome $A$.
> >   * **Likelihood $P(A \mid B_k)$:** The probability of observing outcome $A$ given that scenario $B_k$ occurs.
> >   * **Marginal Likelihood $P(A)$:** The total probability of outcome $A$ across all partitions (calculated via the Law of Total Probability in the denominator).
> >   * **Posterior Probability $P(B_k \mid A)$:** The updated probability of scenario $B_k$ after incorporating the evidence that outcome $A$ occurred.
> 
> > [!tip]- Structural Comparison
> > | Feature | Law of Total Probability | Bayes' Theorem |
> > | :--- | :--- | :--- |
> > | **Goal** | Compute $P(A)$ | Compute $P(B_k \mid A)$ |
> > | **Direction** | Cause $\to$ Effect (Forward) | Effect $\to$ Cause (Inverse) |
> > | **Role in Inference** | Provides the normalizing constant (denominator) | Calculates updated belief/hypothesis given evidence (posterior) |
> > | **Formula Structure** | $P(A) = \sum_{i=1}^n P(A \mid B_i) P(B_i)$ | $P(B_k \mid A) = \frac{\text{Prior} \times \text{Likelihood}}{\text{Law of Total Probability}}$ |

---

> [!tip]- Event Independence & Mutual Independence
> Two events $A$ and $B$ are independent if the occurrence of $B$ does not alter the likelihood of $A$, meaning $P(A \mid B) = P(A)$.
>
>---
>
> > [!tip]- Pairwise Independence vs. Mutual Independence
> > * **Two-Event Independence:**
> >   $$P(A \cap B) = P(A)P(B)$$
> > * **Pairwise Independence:** A collection $\{A_i\}_{i \in I}$ is pairwise independent if every pair satisfies:
> >   $$P(A_i \cap A_j) = P(A_i)P(A_j) \quad \forall i \neq j$$
> > * **Mutual Independence:** A collection $\{A_i\}_{i \in I}$ is mutually independent if for *every* finite subset $J \subseteq I$:
> >   $$P\left( \bigcap_{i \in J} A_i \right) = \prod_{i \in J} P(A_i)$$
> > * **Important Distinction:** Pairwise independence **does not** imply mutual independence.
> 
> > [!tip]- Card Suit vs. Rank Example
> > * In a standard 52-card deck, let $A =$ {Suit is Diamonds} ($P(A) = \frac{13}{52} = \frac{1}{4}$) and $B =$ {Rank is Queen} ($P(B) = \frac{4}{52} = \frac{1}{13}$).
> > * $P(A \cap B) = P(\text{Queen of Diamonds}) = \frac{1}{52} = \frac{1}{4} \times \frac{1}{13} = P(A)P(B)$, proving $A$ and $B$ are independent.

> [!tip]- Conditional Independence
> Events $A$ and $B$ are conditionally independent given an event $C$ (where $P(C) > 0$) if:
>   $$P(A \cap B \mid C) = P(A \mid C) P(B \mid C)$$
> 
>- Conditional independence given $C$ **neither implies nor is implied by** independence of $A$ and  $B$.

> [!tip]- Product Spaces $(\Omega_1 \times \Omega_2, \mathcal{F}, P)$
> * **Purpose:** Constructs a single probability framework to describe two separate or independent experiments.
> * **Sample Space:** $\Omega = \Omega_1 \times \Omega_2 = \{(\omega_1, \omega_2) : \omega_1 \in \Omega_1, \omega_2 \in \Omega_2\}$.
> * **$\sigma$-Field ($\mathcal{F}$):** The smallest $\sigma$-field containing all product sets $\mathcal{F}_1 \times \mathcal{F}_2$.
> * **Probability Measure ($P$):** Defined on product rectangles as:
>   $$P(A_1 \times A_2) = P_1(A_1) P_2(A_2) \quad \forall A_1 \in \mathcal{F}_1, A_2 \in \mathcal{F}_2$$


