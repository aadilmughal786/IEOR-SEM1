
> [!important]- Continuity of Probability
>
> The set-function $P$ is **continuous** in the following sense: if a sequence of events gradually grows towards a limiting event, then their probabilities also converge to the probability of that limiting event.
>
> > [!abstract]- Proposition
> >
> > Let $A_1,A_2,\ldots$ be an **increasing sequence of events**:
> >
> > $$A_1\subseteq A_2\subseteq A_3\subseteq\cdots$$
> >
> > Define its limit by
> >
> > $$A=\bigcup_{i=1}^{\infty}A_i.$$
> >
> > Then
> >
> > $$\boxed{P(A)=\lim_{n\to\infty}P(A_n).}$$
> >
> > In other words, if
> >
> > $$A_n\uparrow A,$$
> >
> > then
> >
> > $$P(A_n)\uparrow P(A).$$
>
> > [!tip]- Intuition
> >
> > Think of $A_n$ as gradually expanding towards $A$:
> >
> > $$A_1\subseteq A_2\subseteq A_3\subseteq\cdots\subseteq A.$$
> >
> > As $n$ becomes larger, $A_n$ becomes a better approximation of $A$.
> >
> > Therefore,
> >
> > $$P(A_n)\longrightarrow P(A).$$
> >
> > This is why the property is called **continuity of probability**.
>
> > [!abstract]- Connection to Countable Additivity
> >
> > This continuity property is essentially equivalent to **countable additivity**.
> >
> > We will not prove the equivalence, but the proof of the proposition follows directly from countable additivity.
>
> > [!example]- Proof
> >
> > Since $A_n\subseteq A_{n+1}$, we can decompose $A$ into disjoint pieces:
> >
> > $$A=A_1\sqcup(A_2\setminus A_1)\sqcup(A_3\setminus A_2)\sqcup\cdots$$
> >
> > By countable additivity,
> >
> > $$P(A)=P(A_1)+\sum_{i=2}^{\infty}P(A_i\setminus A_{i-1}).$$
> >
> > Since
> >
> > $$A_i=A_{i-1}\sqcup(A_i\setminus A_{i-1}),$$
> >
> > we have
> >
> > $$P(A_i\setminus A_{i-1})=P(A_i)-P(A_{i-1}).$$
> >
> > Therefore,
> >
> > $$P(A)=P(A_1)+\sum_{i=2}^{\infty}\left[P(A_i)-P(A_{i-1})\right].$$
> >
> > The sum **telescopes**:
> >
> > $$P(A)=\lim_{n\to\infty}
> > \left[
> > P(A_1)+\sum_{i=2}^{n}\left(P(A_i)-P(A_{i-1})\right)
> > \right].$$
> >
> > Hence,
> >
> > $$P(A)=\lim_{n\to\infty}P(A_n).$$
>
> > [!important]- Key Idea
> >
> > An increasing sequence of events
> >
> > $$A_1\subseteq A_2\subseteq\cdots\uparrow A$$
> >
> > implies
> >
> > $$\boxed{P(A_n)\rightarrow P(A).}$$
> >
> > So **limits of events correspond to limits of their probabilities**.

> [!important]- Conditional Probability
>
> Let $(\Omega,\mathcal{F},P)$ be a probability space. So far, we have assigned probabilities to events in $\mathcal{F}$.
>
> Sometimes, however, we want to know the probability of an event **given some additional information**.
>
> For example:
>
> - Given that it is raining, what is the probability that the bus arrives on time?
> - A die is rolled three times. Given that the sum is $12$, what is the probability that all three outcomes are even?
>
> The idea is to assign a probability to an event $A$ **given that another event $B$ has occurred**.
>
> > [!abstract]- Frequentist Intuition
> >
> > Let $A$ and $B$ be events. Suppose we repeat the experiment $N$ times.
> >
> > Let $N(A\cap B)$ be the number of times both $A$ and $B$ occur, and let $N(B)$ be the number of times $B$ occurs.
> >
> > The fraction of times $A$ occurs **among the trials where $B$ occurs** is
> >
> > $$\frac{N(A\cap B)}{N(B)}.$$
> >
> > Rewrite this as
> >
> > $$\frac{N(A\cap B)/N}{N(B)/N}.$$
> >
> > For large $N$,
> >
> > $$\frac{N(A\cap B)}{N}\approx P(A\cap B)$$
> >
> > and
> >
> > $$\frac{N(B)}{N}\approx P(B).$$
> >
> > Therefore,
> >
> > $$P(A\mid B)\approx\frac{P(A\cap B)}{P(B)}.$$
> >
> > This motivates the formal definition.
>
> > [!important]- Definition
> >
> > Let $A$ and $B$ be events with $P(B)>0$.
> >
> > The **conditional probability of $A$ given $B$** is defined as
> >
> > $$\boxed{P(A\mid B)=\frac{P(A\cap B)}{P(B)}}$$
> >
> > The notation $P(A\mid B)$ is pronounced **"P of A given B."**
>
> > [!example]- Two Children: Given at Least One Is a Boy
> >
> > Suppose a family has two children. Assume each possible outcome is equally likely:
> >
> > $$\Omega=\{GG,GB,BG,BB\}.$$
> >
> > Each outcome has probability
> >
> > $$\frac14.$$
> >
> > We want the probability that **both children are boys**, given that **at least one is a boy**.
> >
> > Let
> >
> > $$A=\{BB\}$$
> >
> > and
> >
> > $$B=\{GB,BG,BB\}.$$
> >
> > Using conditional probability,
> >
> > $$P(BB\mid GB\cup BG\cup BB)
> > =\frac{P(BB\cap(GB\cup BG\cup BB))}
> > {P(GB\cup BG\cup BB)}.$$
> >
> > Since $BB\subseteq B$,
> >
> > $$P(BB\cap B)=P(BB)=\frac14.$$
> >
> > Also,
> >
> > $$P(B)=\frac34.$$
> >
> > Therefore,
> >
> > $$P(BB\mid B)
> > =\frac{\frac14}{\frac34}
> > =\boxed{\frac13}.$$
> >
> > **Why not $\frac12$?**
> >
> > Once we know that at least one child is a boy, the possible outcomes are no longer all four outcomes. The effective sample space becomes
> >
> > $$\{GB,BG,BB\}.$$
> >
> > Only one of these three outcomes has two boys.
>
> > [!example]- Two Children: Given the Younger Is a Boy
> >
> > Now suppose we know specifically that the **younger child is a boy**.
> >
> > The possible outcomes are
> >
> > $$\{GB,BB\}.$$
> >
> > We want
> >
> > $$P(BB\mid GB\cup BB).$$
> >
> > Using the definition,
> >
> > $$P(BB\mid GB\cup BB)
> > =\frac{P(BB\cap(GB\cup BB))}
> > {P(GB\cup BB)}.$$
> >
> > Since $BB\subseteq\{GB,BB\}$,
> >
> > $$P(BB\cap(GB\cup BB))=P(BB)=\frac14.$$
> >
> > Also,
> >
> > $$P(GB\cup BB)=\frac12.$$
> >
> > Therefore,
> >
> > $$P(BB\mid GB\cup BB)
> > =\frac{\frac14}{\frac12}
> > =\boxed{\frac12}.$$
>
> > [!tip]- Key Idea
> >
> > Conditional probability asks:
> >
> > **"After restricting our attention to the cases where $B$ happened, what fraction of those cases also have $A$?"**
> >
> > $$\boxed{P(A\mid B)=\frac{P(A\cap B)}{P(B)}}$$

> [!important]- Law of Total Probability
>
> > [!abstract]- Context: Why Do We Need It?
> >
> > In many probability problems, an event $A$ can happen through several **different scenarios**.
> >
> > Instead of calculating $P(A)$ directly, we can:
> >
> > - divide the sample space into **exhaustive and mutually exclusive cases**
> > - calculate the probability of $A$ within each case
> > - combine these probabilities using the probability of each case
> >
> > This is the basic idea behind the **law of total probability**.
> >
> > **Key idea:**
> >
> > $$\boxed{\text{Overall probability}=\sum(\text{conditional probability}\times\text{probability of the case})}$$
>
> > [!abstract]- Partition of the Sample Space
> >
> > A collection of events
> >
> > $$\{B_1,B_2,\dots,B_n\}$$
> >
> > forms a **partition** of $\Omega$ if:
> >
> > **Mutually exclusive:**
> >
> > $$B_i\cap B_j=\emptyset,\qquad i\neq j$$
> >
> > **Collectively exhaustive:**
> >
> > $$\bigcup_{i=1}^n B_i=\Omega$$
> >
> > Therefore, exactly **one** of the events $B_1,\dots,B_n$ occurs.
> >
> > **Intuition:** The partition divides the entire sample space into separate possible scenarios.
>
> > [!abstract]- Mathematical Derivation
> >
> > Since the partition covers the entire sample space,
> >
> > $$\bigcup_{i=1}^nB_i=\Omega.$$
> >
> > Therefore,
> >
> > $$A=A\cap\Omega$$
> >
> > $$=A\cap\left(\bigcup_{i=1}^nB_i\right)$$
> >
> > $$=\bigsqcup_{i=1}^n(A\cap B_i).$$
> >
> > The symbol $\bigsqcup$ means that the union is **disjoint**.
> >
> > Since the events $A\cap B_i$ are mutually disjoint, finite additivity gives
> >
> > $$P(A)=\sum_{i=1}^nP(A\cap B_i).$$
> >
> > Using
> >
> > $$P(A\cap B_i)=P(A\mid B_i)P(B_i),$$
> >
> > provided $P(B_i)>0$, we obtain
> >
> > $$\boxed{P(A)=\sum_{i=1}^nP(A\mid B_i)P(B_i).}$$
>
> > [!important]- General Law of Total Probability
> >
> > If $\{B_1,\dots,B_n\}$ is a partition of $\Omega$ and
> >
> > $$P(B_i)>0\qquad\text{for all }i,$$
> >
> > then
> >
> > $$\boxed{P(A)=\sum_{i=1}^nP(A\mid B_i)P(B_i).}$$
> >
> > This means that the probability of $A$ is obtained by considering **every possible scenario** $B_i$ through which $A$ can occur.
>
> > [!abstract]- Two-Event Version
> >
> > The simplest partition is
> >
> > $$\{B,B^c\}.$$
> >
> > Since $B$ and $B^c$ are disjoint and
> >
> > $$B\cup B^c=\Omega,$$
> >
> > they form a partition.
> >
> > Therefore,
> >
> > $$\boxed{P(A)=P(A\mid B)P(B)+P(A\mid B^c)P(B^c).}$$
> >
> > This is just the general law applied to two cases.
>
> > [!example]- Two-Bin Ball Pick Example
> >
> > **Setup:**
> >
> > - Bin 1 contains $2$ White and $3$ Blue balls.
> > - Bin 2 contains $3$ White and $4$ Blue balls.
> > - One ball is randomly picked from Bin 1 and transferred to Bin 2.
> > - Then one ball is randomly picked from Bin 2.
> >
> > Let
> >
> > $$A=\{\text{ball picked from Bin 2 is Blue}\}$$
> >
> > and
> >
> > $$B=\{\text{ball moved from Bin 1 is Blue}\}.$$
> >
> > The event $B^c$ means that the moved ball was White.
>
> > [!abstract]- Step 1: Identify the Partition
> >
> > The two possible scenarios for the transferred ball are:
> >
> > $$B=\{\text{Blue transferred}\}$$
> >
> > $$B^c=\{\text{White transferred}\}.$$
> >
> > These are mutually exclusive and exhaustive, so
> >
> > $$\{B,B^c\}$$
> >
> > is a partition of $\Omega$.
>
> > [!abstract]- Step 2: Prior Probabilities
> >
> > Initially, Bin 1 has $3$ Blue and $2$ White balls.
> >
> > Therefore,
> >
> > $$P(B)=\frac{3}{5}$$
> >
> > and
> >
> > $$P(B^c)=\frac{2}{5}.$$
>
> > [!abstract]- Step 3: Conditional Probabilities
> >
> > **Case 1: Blue ball was transferred**
> >
> > Bin 2 now contains:
> >
> > - $3$ White
> > - $5$ Blue
> >
> > So there are $8$ balls in total.
> >
> > Hence,
> >
> > $$P(A\mid B)=\frac{5}{8}.$$
> >
> > **Case 2: White ball was transferred**
> >
> > Bin 2 now contains:
> >
> > - $4$ White
> > - $4$ Blue
> >
> > Hence,
> >
> > $$P(A\mid B^c)=\frac{4}{8}=\frac12.$$
>
> > [!important]- Step 4: Apply the Law of Total Probability
> >
> > Using the partition $\{B,B^c\}$:
> >
> > $$P(A)=P(A\mid B)P(B)+P(A\mid B^c)P(B^c)$$
> >
> > Substituting:
> >
> > $$P(A)=\left(\frac58\right)\left(\frac35\right)
> > +\left(\frac12\right)\left(\frac25\right)$$
> >
> > $$=\frac38+\frac15$$
> >
> > $$=\boxed{\frac{23}{40}}.$$
>
> > [!tip]- Intuition Behind the Example
> >
> > We do not know whether the transferred ball was Blue or White.
> >
> > So we consider **both possible cases**:
> >
> > $$\text{Blue transferred}\quad\text{or}\quad\text{White transferred}.$$
> >
> > For each case, we calculate how likely $A$ is and then weight it by how likely that case itself is.
> >
> > $$\boxed{
> > P(A)=
> > \underbrace{P(A\mid B)P(B)}_{\text{contribution from case }B}
> > +
> > \underbrace{P(A\mid B^c)P(B^c)}_{\text{contribution from case }B^c}
> > }$$
> >
> > So the law of total probability is essentially a **weighted average of conditional probabilities**.
>
> > [!abstract]- Structural Insight: Implicit Probability Spaces
> >
> > In practical probability problems, we usually do **not** explicitly write down every element of
> >
> > $$(\Omega,\mathcal F,P).$$
> >
> > For example, in the bin problem, we directly talk about probabilities of transferring Blue or White balls.
> >
> > However, mathematically, all these events and probabilities are understood to exist within an underlying probability space
> >
> > $$(\Omega,\mathcal F,P).$$
> >
> > **Important:** Even when the probability space is not explicitly written, it is still the mathematical structure governing the experiment.
>
> > [!important]- Key Takeaway
> >
> > The law of total probability is useful whenever an event can be analyzed through several **separate cases**.
> >
> > $$\boxed{
> > P(A)=\sum_i P(A\mid B_i)P(B_i)
> > }$$
> >
> > Think:
> >
> > **Split into cases → solve each case → weight by case probability → add.**

> [!important]- Bayes' Theorem
>
> > [!abstract]- Context: What Problem Does Bayes' Theorem Solve?
> >
> > Suppose we know that an event $B$ has occurred, and we want to determine how likely a particular cause or scenario $A$ was.
> >
> > In other words, we want to **reverse a conditional probability**:
> >
> > $$P(B\mid A)\quad\longrightarrow\quad P(A\mid B).$$
> >
> > For example:
> >
> > - $A$ = a person has a disease
> > - $B$ = the medical test is positive
> >
> > We may know
> >
> > $$P(B\mid A)$$
> >
> > which tells us how likely a positive test is **given that the person has the disease**.
> >
> > But what we actually want may be
> >
> > $$P(A\mid B),$$
> >
> > the probability that the person has the disease **given that the test is positive**.
> >
> > Bayes' theorem provides exactly this reversal.
>
> > [!important]- Bayes' Theorem
> >
> > For events $A$ and $B$ with $P(B)>0$,
> >
> > $$\boxed{
> > P(A\mid B)=\frac{P(B\mid A)P(A)}{P(B)}
> > }$$
> >
> > This allows us to calculate the probability of $A$ **after observing $B$**.
> >
> > The three important quantities are:
> >
> > $$P(A) \quad\text{Prior probability}$$
> >
> > $$P(B\mid A) \quad\text{Likelihood}$$
> >
> > $$P(A\mid B) \quad\text{Posterior probability}$$
> >
> > $$P(B) \quad\text{Evidence / marginal probability}$$
>
> > [!abstract]- Derivation from Conditional Probability
> >
> > Start with the definition of conditional probability:
> >
> > $$P(A\mid B)=\frac{P(A\cap B)}{P(B)}.$$
> >
> > Also,
> >
> > $$P(B\mid A)=\frac{P(A\cap B)}{P(A)}.$$
> >
> > Therefore,
> >
> > $$P(A\cap B)=P(B\mid A)P(A).$$
> >
> > Substituting this into the first equation:
> >
> > $$P(A\mid B)
> > =\frac{P(B\mid A)P(A)}{P(B)}.$$
> >
> > Hence,
> >
> > $$\boxed{
> > P(A\mid B)=\frac{P(B\mid A)P(A)}{P(B)}
> > }.$$
>
> > [!important]- Where Does Total Probability Enter?
> >
> > The denominator in Bayes' theorem is
> >
> > $$P(B).$$
> >
> > Often, $P(B)$ is not directly known.
> >
> > Suppose $\{A_1,A_2,\dots,A_n\}$ is a partition of $\Omega$.
> >
> > Then the **law of total probability** gives:
> >
> > $$P(B)=\sum_{i=1}^nP(B\mid A_i)P(A_i).$$
> >
> > Therefore, Bayes' theorem becomes
> >
> > $$\boxed{
> > P(A_j\mid B)
> > =
> > \frac{P(B\mid A_j)P(A_j)}
> > {\sum_{i=1}^nP(B\mid A_i)P(A_i)}
> > }.$$
> >
> > This is the **Bayes theorem + total probability** form.
>
> > [!abstract]- The Key Relationship
> >
> > The relationship can be remembered as:
> >
> > $$\boxed{
> > \text{Bayes' theorem}
> > =
> > \frac{\text{reverse probability numerator}}
> > {\text{total probability of evidence}}
> > }$$
> >
> > More specifically:
> >
> > $$P(A\mid B)
> > =
> > \frac{
> > \underbrace{P(B\mid A)P(A)}_{\text{Bayes numerator}}
> > }{
> > \underbrace{P(B)}_{\text{often calculated using total probability}}
> > }.$$
> >
> > So **total probability often supplies the denominator of Bayes' theorem**.
>
> > [!example]- Medical Test Example
> >
> > Suppose:
> >
> > $$P(D)=0.01$$
> >
> > where $D$ means the person has a disease.
> >
> > Suppose the test has:
> >
> > $$P(+\mid D)=0.99$$
> >
> > and
> >
> > $$P(+\mid D^c)=0.05.$$
> >
> > We observe a positive test and want:
> >
> > $$P(D\mid +).$$
>
> > [!abstract]- Step 1: Use Total Probability
> >
> > The two possible cases are $D$ and $D^c$, which form a partition.
> >
> > Therefore:
> >
> > $$P(+)=P(+\mid D)P(D)+P(+\mid D^c)P(D^c).$$
> >
> > Substituting:
> >
> > $$P(+)
> > =(0.99)(0.01)+(0.05)(0.99)$$
> >
> > $$=0.0099+0.0495$$
> >
> > $$=0.0594.$$
>
> > [!abstract]- Step 2: Apply Bayes' Theorem
> >
> > $$P(D\mid +)
> > =\frac{P(+\mid D)P(D)}{P(+)}.$$
> >
> > Therefore:
> >
> > $$P(D\mid +)
> > =\frac{(0.99)(0.01)}{0.0594}$$
> >
> > $$\approx0.1667.$$
> >
> > Hence,
> >
> > $$\boxed{P(D\mid +)\approx16.67\%}.$$
> >
> > Notice what happened:
> >
> > **Total probability** calculated the probability of observing a positive test.
> >
> > **Bayes' theorem** used that probability to determine the probability of disease given a positive test.
>
> > [!important]- Total Probability vs Bayes' Theorem
> >
> > **Law of Total Probability:**
> >
> > $$\boxed{
> > P(B)=\sum_iP(B\mid A_i)P(A_i)
> > }$$
> >
> > It combines probabilities from different cases to find the **overall probability of an event**.
> >
> > **Bayes' Theorem:**
> >
> > $$\boxed{
> > P(A_j\mid B)
> > =
> > \frac{P(B\mid A_j)P(A_j)}
> > {P(B)}
> > }$$
> >
> > It uses observed evidence $B$ to find the probability of a particular case $A_j$.
>
> > [!abstract]- Direction of Reasoning
> >
> > This is one of the easiest ways to distinguish them.
> >
> > **Total Probability:**
> >
> > $$A_i\longrightarrow B$$
> >
> > We know the different cases $A_i$ and ask:
> >
> > **"What is the overall probability of $B$?"**
> >
> > **Bayes' Theorem:**
> >
> > $$B\longrightarrow A_i$$
> >
> > We observe $B$ and ask:
> >
> > **"Given that $B$ happened, how likely was case $A_i$?"**
> >
> > So:
> >
> > $$\boxed{
> > \text{Total Probability: cases → outcome}
> > }$$
> >
> > $$\boxed{
> > \text{Bayes: outcome → cases}
> > }$$
>
> > [!tip]- A Useful Mental Model
> >
> > Imagine several boxes containing balls.
> >
> > **Total Probability asks:**
> >
> > "If I randomly select a box and then a ball, what is the probability that I get a Blue ball?"
> >
> > $$\text{Box}\longrightarrow\text{Color}$$
> >
> > **Bayes asks:**
> >
> > "I got a Blue ball. What is the probability that it came from Box 2?"
> >
> > $$\text{Color}\longrightarrow\text{Box}$$
> >
> > The direction of reasoning is reversed.
>
> > [!important]- Bayes + Total Probability Together
> >
> > Suppose $\{A_1,\dots,A_n\}$ is a partition and we observe $B$.
> >
> > First, total probability calculates:
> >
> > $$P(B)=\sum_{i=1}^nP(B\mid A_i)P(A_i).$$
> >
> > Then Bayes' theorem calculates:
> >
> > $$P(A_j\mid B)
> > =
> > \frac{P(B\mid A_j)P(A_j)}
> > {\sum_{i=1}^nP(B\mid A_i)P(A_i)}.$$
> >
> > Thus, in many problems, the workflow is:
> >
> > $$\boxed{
> > \text{Partition}
> > \rightarrow
> > \text{Total Probability}
> > \rightarrow
> > \text{Bayes' Theorem}
> > }$$
> >
> > Total probability finds the **denominator**, and Bayes uses it to calculate the **posterior probability**.
>
> > [!abstract]- Important Terminology
> >
> > $$P(A)$$
> >
> > **Prior:** Probability of $A$ before observing $B$.
> >
> > $$P(B\mid A)$$
> >
> > **Likelihood:** Probability of observing $B$ if $A$ is true.
> >
> > $$P(B)$$
> >
> > **Evidence:** Overall probability of observing $B$.
> >
> > $$P(A\mid B)$$
> >
> > **Posterior:** Probability of $A$ after observing $B$.
>
> > [!important]- Final Takeaway
> >
> > **Law of Total Probability**
> >
> > $$\boxed{
> > \text{Break the problem into cases and add their contributions.}
> > }$$
> >
> > **Bayes' Theorem**
> >
> > $$\boxed{
> > \text{Use observed evidence to update the probability of a case.}
> > }$$
> >
> > They are closely connected:
> >
> > $$\boxed{
> > P(A\mid B)
> > =
> > \frac{P(B\mid A)P(A)}
> > {\underbrace{P(B)}_{\text{often found using total probability}}}
> > }$$
> >
> > **Memory trick:**
> >
> > $$\boxed{\text{Total Probability = combine cases}}
> > $$
> >
> > $$\boxed{\text{Bayes = reverse/update cases}}
> > $$

---

> [!important]- Independence
>
> > [!abstract]- Context: What Does Independence Mean?
> >
> > Recall that conditional probability is
> >
> > $$P(A\mid B)=\frac{P(A\cap B)}{P(B)},\qquad P(B)>0.$$
> >
> > Usually, knowing that $B$ occurred can change our assessment of whether $A$ occurred.
> >
> > But sometimes, knowing that $B$ occurred gives us **no additional information** about $A$.
> >
> > In that case, we expect
> >
> > $$P(A\mid B)=P(A).$$
> >
> > We say that $A$ and $B$ are **independent**.
> >
> > **Intuition:**
> >
> > $$\boxed{\text{Knowing }B\text{ does not change the probability of }A.}$$
>
> > [!example]- Coin Toss Example
> >
> > A fair coin is tossed twice.
> >
> > Let
> >
> > $$A=\{\text{first outcome is H}\}$$
> >
> > and
> >
> > $$B=\{\text{second outcome is H}\}.$$
> >
> > The first toss does not affect the second toss.
> >
> > Therefore, knowing that the second toss was H does not change the probability that the first toss was H:
> >
> > $$P(A\mid B)=P(A)=\frac12.$$
> >
> > Similarly,
> >
> > $$P(B\mid A)=P(B)=\frac12.$$
> >
> > Thus, $A$ and $B$ are independent.
>
> > [!important]- Definition
> >
> > Two events $A$ and $B$ are said to be **independent** if
> >
> > $$\boxed{P(A\cap B)=P(A)P(B).}$$
> >
> > This is the standard definition of independence.
> >
> > If $P(B)>0$, this is equivalent to
> >
> > $$P(A\mid B)=P(A).$$
> >
> > Indeed,
> >
> > $$P(A\mid B)
> > =\frac{P(A\cap B)}{P(B)}
> > =\frac{P(A)P(B)}{P(B)}
> > =P(A).$$
>
> > [!abstract]- Independence vs Conditional Probability
> >
> > Conditional probability asks:
> >
> > $$\boxed{\text{How does knowing }B\text{ affect the probability of }A?}$$
> >
> > Independence says:
> >
> > $$\boxed{\text{Knowing }B\text{ does not affect the probability of }A.}$$
> >
> > Therefore,
> >
> > $$A\perp B
> > \quad\Longleftrightarrow\quad
> > P(A\mid B)=P(A)$$
> >
> > when $P(B)>0$.
> >
> > Here $A\perp B$ is notation for "$A$ and $B$ are independent."
>
> > [!warning]- Independence Is Not the Same as Disjointness
> >
> > **Disjoint events** mean:
> >
> > $$A\cap B=\emptyset.$$
> >
> > Therefore,
> >
> > $$P(A\cap B)=0.$$
> >
> > **Independent events** mean:
> >
> > $$P(A\cap B)=P(A)P(B).$$
> >
> > If both $P(A)>0$ and $P(B)>0$, then independent events satisfy
> >
> > $$P(A\cap B)=P(A)P(B)>0.$$
> >
> > Therefore, they **cannot be disjoint**.
> >
> > **Key distinction:**
> >
> > $$\boxed{\text{Disjoint = cannot happen together}}$$
> >
> > $$\boxed{\text{Independent = occurrence of one does not affect the other}}$$
>
> > [!example]- Card Example: Suit and Rank
> >
> > Consider a standard deck of $52$ cards:
> >
> > - $4$ suits: Hearts, Diamonds, Spades, Clubs
> > - $13$ ranks in each suit
> >
> > A card is chosen uniformly at random.
> >
> > Let
> >
> > $$A=\{\text{suit is Diamonds}\}$$
> >
> > $$B=\{\text{rank is Queen}\}.$$
> >
> > There are $13$ Diamonds:
> >
> > $$P(A)=\frac{13}{52}=\frac14.$$
> >
> > There are $4$ Queens:
> >
> > $$P(B)=\frac{4}{52}=\frac1{13}.$$
> >
> > The only card that is both a Diamond and a Queen is the Queen of Diamonds:
> >
> > $$P(A\cap B)=\frac1{52}.$$
> >
> > Now:
> >
> > $$P(A)P(B)
> > =\frac14\cdot\frac1{13}
> > =\frac1{52}.$$
> >
> > Therefore,
> >
> > $$P(A\cap B)=P(A)P(B),$$
> >
> > so $A$ and $B$ are independent.
>
> > [!abstract]- Why Are Suit and Rank Independent?
> >
> > Knowing that the card is a Queen does not change the probability that its suit is Diamonds.
> >
> > Before knowing the rank:
> >
> > $$P(\text{Diamond})=\frac14.$$
> >
> > After knowing the rank is Queen:
> >
> > $$P(\text{Diamond}\mid\text{Queen})=\frac14.$$
> >
> > Therefore, knowing the rank gives no information about the suit.
>
> > [!important]- Independence of Multiple Events
> >
> > For a finite collection
> >
> > $$\{A_1,\dots,A_n\},$$
> >
> > the events are **independent** if
> >
> > $$\boxed{
> > P(A_1\cap A_2\cap\cdots\cap A_n)
> > =
> > \prod_{i=1}^nP(A_i)
> > }.$$
> >
> > For example, three events $A,B,C$ are independent if
> >
> > $$P(A\cap B\cap C)=P(A)P(B)P(C).$$
>
> > [!warning]- Important: Pairwise Independence Is Not Enough
> >
> > A collection $\{A_1,\dots,A_n\}$ is **pairwise independent** if every pair is independent:
> >
> > $$\boxed{
> > P(A_i\cap A_j)=P(A_i)P(A_j)
> > \qquad\text{for all }i\neq j.
> > }$$
> >
> > However, **pairwise independence does not necessarily imply mutual independence**.
> >
> > For three or more events, checking
> >
> > $$P(A\cap B)=P(A)P(B),$$
> >
> > $$P(A\cap C)=P(A)P(C),$$
> >
> > $$P(B\cap C)=P(B)P(C)$$
> >
> > is not enough.
> >
> > We also need
> >
> > $$P(A\cap B\cap C)=P(A)P(B)P(C).$$
> >
> > **Therefore:**
> >
> > $$\boxed{\text{Mutual independence}\Rightarrow\text{pairwise independence}}$$
> >
> > but
> >
> > $$\boxed{\text{Pairwise independence}\not\Rightarrow\text{mutual independence}.}$$
>
> > [!abstract]- General Definition for a Family of Events
> >
> > A family of events
> >
> > $$\{A_i:i\in I\}$$
> >
> > is independent if **every finite subcollection** is independent.
> >
> > That means for every finite subset $J\subseteq I$,
> >
> > $$\boxed{
> > P\left(\bigcap_{i\in J}A_i\right)
> > =
> > \prod_{i\in J}P(A_i).
> > }$$
> >
> > This definition also works when the family contains infinitely many events.
>
> > [!important]- Conditional Independence
> >
> > Independence can also be considered **after conditioning on another event**.
> >
> > Fix an event $C$ such that
> >
> > $$P(C)>0.$$
> >
> > Under the condition that $C$ occurred, we use the conditional probability
> >
> > $$P(A\mid C)=\frac{P(A\cap C)}{P(C)}.$$
> >
> > We can therefore ask whether $A$ and $B$ are independent **within the world where $C$ has occurred**.
>
> > [!important]- Definition of Conditional Independence
> >
> > Events $A$ and $B$ are said to be **conditionally independent given $C$** if
> >
> > $$\boxed{
> > P(A\cap B\mid C)
> > =
> > P(A\mid C)P(B\mid C).
> > }$$
> >
> > Compare this with ordinary independence:
> >
> > $$P(A\cap B)=P(A)P(B).$$
> >
> > Conditional independence simply replaces the ordinary probability $P(\cdot)$ with the conditional probability $P(\cdot\mid C)$.
>
> > [!abstract]- Another Way to Understand Conditional Independence
> >
> > Ordinary independence:
> >
> > $$\boxed{
> > A\text{ and }B\text{ do not affect each other}
> > }$$
> >
> > Conditional independence:
> >
> > $$\boxed{
> > A\text{ and }B\text{ do not affect each other once }C\text{ is known}
> > }$$
> >
> > In other words, $A$ and $B$ may be dependent in the full sample space, but after restricting our attention to $C$, they become independent.
>
> > [!warning]- Independence and Conditional Independence Are Different
> >
> > Conditional independence given $C$ does **not** imply ordinary independence.
> >
> > $$A\perp B\mid C
> > \not\Rightarrow
> > A\perp B.$$
> >
> > Likewise, ordinary independence does not necessarily imply conditional independence:
> >
> > $$A\perp B
> > \not\Rightarrow
> > A\perp B\mid C.$$
> >
> > Therefore:
> >
> > $$\boxed{
> > \text{Independence and conditional independence are different concepts.}
> > }$$
>
> > [!tip]- Big Picture
> >
> > **Independence**
> >
> > $$P(A\cap B)=P(A)P(B)$$
> >
> > asks whether $A$ and $B$ are unrelated under the original probability $P$.
> >
> > **Conditional independence**
> >
> > $$P(A\cap B\mid C)=P(A\mid C)P(B\mid C)$$
> >
> > asks whether $A$ and $B$ are unrelated **after we know that $C$ occurred**.
> >
> > **Pairwise independence**
> >
> > checks independence **two events at a time**.
> >
> > **Mutual independence**
> >
> > requires the appropriate product rule for **every finite subcollection**.
>
> > [!important]- Key Takeaways
> >
> > $$\boxed{A\perp B
> > \iff P(A\cap B)=P(A)P(B)}$$
> >
> > If $P(B)>0$:
> >
> > $$\boxed{A\perp B
> > \iff P(A\mid B)=P(A)}$$
> >
> > Disjointness:
> >
> > $$\boxed{A\cap B=\emptyset}$$
> >
> > is different from independence.
> >
> > Pairwise independence:
> >
> > $$\boxed{P(A_i\cap A_j)=P(A_i)P(A_j)}$$
> >
> > for every pair, but it does not necessarily imply mutual independence.
> >
> > Conditional independence:
> >
> > $$\boxed{
> > A\perp B\mid C
> > \iff
> > P(A\cap B\mid C)=P(A\mid C)P(B\mid C)
> > }$$
> >
> > **Mental model:**
> >
> > $$\boxed{
> > \text{Independence = no information transfer}
> > }$$
> >
> > $$\boxed{
> > \text{Conditional independence = no information transfer after knowing }C
> > }$$

> [!important]- Product Spaces
>
> > [!abstract]- Context: Why Do We Need Product Spaces?
> >
> > Sometimes we want to describe **two or more separate experiments within one probability framework**.
> >
> > For example:
> >
> > - Tossing one coin and rolling one die
> > - Running two independent experiments
> > - Observing the outcomes of two separate random processes
> >
> > Instead of describing the experiments separately, we can combine them into a **single probability space**.
> >
> > This combined space is called a **product space**.
>
> > [!abstract]- Starting with Two Probability Spaces
> >
> > Suppose we have two probability spaces:
> >
> > $$(\Omega_1,\mathcal F_1,P_1)$$
> >
> > and
> >
> > $$(\Omega_2,\mathcal F_2,P_2).$$
> >
> > Here:
> >
> > - $\Omega_1$ describes the possible outcomes of experiment 1.
> > - $\mathcal F_1$ describes the events of experiment 1.
> > - $P_1$ gives their probabilities.
> >
> > Similarly:
> >
> > - $\Omega_2$ describes the possible outcomes of experiment 2.
> > - $\mathcal F_2$ describes the events of experiment 2.
> > - $P_2$ gives their probabilities.
> >
> > We want to combine these two experiments into one probability space.
>
> > [!important]- Product Sample Space
> >
> > The combined sample space is the **Cartesian product**
> >
> > $$\boxed{\Omega=\Omega_1\times\Omega_2}$$
> >
> > where
> >
> > $$\Omega_1\times\Omega_2
> > =
> > \{(\omega_1,\omega_2):
> > \omega_1\in\Omega_1,\ \omega_2\in\Omega_2\}.$$
> >
> > Therefore, an outcome of the combined experiment is an **ordered pair**
> >
> > $$(\omega_1,\omega_2).$$
> >
> > The first component represents the outcome of experiment 1, and the second component represents the outcome of experiment 2.
>
> > [!example]- Simple Intuition
> >
> > Suppose experiment 1 is a coin toss:
> >
> > $$\Omega_1=\{H,T\}.$$
> >
> > Suppose experiment 2 is a die roll:
> >
> > $$\Omega_2=\{1,2,3,4,5,6\}.$$
> >
> > Then
> >
> > $$\Omega=\Omega_1\times\Omega_2.$$
> >
> > Some outcomes are:
> >
> > $$(H,1),(H,2),(H,3),\dots,(T,4),(T,5),(T,6).$$
> >
> > Hence there are
> >
> > $$|\Omega|=2\times6=12$$
> >
> > possible combined outcomes.
> >
> > **Key idea:** The product space records the outcome of **both experiments simultaneously**.
>
> > [!abstract]- Product $\sigma$-Field
> >
> > We also need to specify which subsets of $\Omega$ are measurable events.
> >
> > The product $\sigma$-field is
> >
> > $$\boxed{
> > \mathcal F=\sigma(\mathcal F_1\times\mathcal F_2)
> > }$$
> >
> > meaning the **smallest $\sigma$-field containing the measurable rectangles**
> >
> > $$A_1\times A_2,
> > \qquad A_1\in\mathcal F_1,\ A_2\in\mathcal F_2.$$
> >
> > More precisely, the notation $\mathcal F_1\times\mathcal F_2$ refers to the collection of measurable rectangles
> >
> > $$\{A_1\times A_2:A_1\in\mathcal F_1,\ A_2\in\mathcal F_2\}.$$
> >
> > We then take the smallest $\sigma$-field containing these rectangles.
>
> > [!important]- Product Probability
> >
> > For measurable rectangles
> >
> > $$A_1\times A_2,$$
> >
> > we define the probability by
> >
> > $$\boxed{
> > P(A_1\times A_2)=P_1(A_1)P_2(A_2)
> > }.$$
> >
> > This product rule reflects the idea that the two experiments are being combined independently.
> >
> > For example, if
> >
> > $$P_1(A_1)=0.4$$
> >
> > and
> >
> > $$P_2(A_2)=0.5,$$
> >
> > then
> >
> > $$P(A_1\times A_2)=0.4\times0.5=0.2.$$
>
> > [!abstract]- Why Is the Product Rule Natural?
> >
> > The event
> >
> > $$A_1\times A_2$$
> >
> > means:
> >
> > **experiment 1 produces an outcome in $A_1$ AND experiment 2 produces an outcome in $A_2$.**
> >
> > For independent experiments,
> >
> > $$P(\text{both occur})
> > =
> > P(\text{first occurs})P(\text{second occurs}).$$
> >
> > Therefore,
> >
> > $$P(A_1\times A_2)=P_1(A_1)P_2(A_2).$$
>
> > [!abstract]- Extension to the Full $\sigma$-Field
> >
> > Initially, we define $P$ only on measurable rectangles:
> >
> > $$A_1\times A_2.$$
> >
> > It turns out that this is enough.
> >
> > There exists a **unique extension** of this probability measure from the rectangles to the entire product $\sigma$-field $\mathcal F$.
> >
> > Therefore, once we specify
> >
> > $$P(A_1\times A_2)=P_1(A_1)P_2(A_2),$$
> >
> > the probability measure $P$ on the whole product space is uniquely determined.
>
> > [!important]- Product Space in the Discrete Case
> >
> > If both $\Omega_1$ and $\Omega_2$ are discrete, then every subset is measurable.
> >
> > Therefore,
> >
> > $$\mathcal F_1=2^{\Omega_1}$$
> >
> > and
> >
> > $$\mathcal F_2=2^{\Omega_2}.$$
> >
> > In this case, the product $\sigma$-field is simply
> >
> > $$\boxed{
> > \mathcal F=2^\Omega
> > }$$
> >
> > where
> >
> > $$\Omega=\Omega_1\times\Omega_2.$$
> >
> > Thus, for discrete spaces, there is no major technical difficulty with the $\sigma$-field.
>
> > [!example]- Discrete Example
> >
> > Suppose:
> >
> > $$\Omega_1=\{H,T\}$$
> >
> > and
> >
> > $$\Omega_2=\{1,2,3,4,5,6\}.$$
> >
> > If the coin and die are fair, then
> >
> > $$P_1(\{H\})=\frac12$$
> >
> > and
> >
> > $$P_2(\{4\})=\frac16.$$
> >
> > The product-space event
> >
> > $$\{H\}\times\{4\}=\{(H,4)\}$$
> >
> > has probability
> >
> > $$P((H,4))
> > =P_1(H)P_2(4)
> > =\frac12\cdot\frac16
> > =\frac1{12}.$$
>
> > [!tip]- Connection to Independence
> >
> > The product-space construction naturally represents **independent experiments**.
> >
> > If
> >
> > $$A_1\in\mathcal F_1$$
> >
> > and
> >
> > $$A_2\in\mathcal F_2,$$
> >
> > then
> >
> > $$P(A_1\times A_2)
> > =
> > P_1(A_1)P_2(A_2).$$
> >
> > This has exactly the same mathematical structure as the independence rule:
> >
> > $$P(A\cap B)=P(A)P(B).$$
> >
> > The product space therefore gives a formal mathematical framework for putting **independent experiments together**.
>
> > [!important]- Big Picture
> >
> > We start with two separate probability spaces:
> >
> > $$\boxed{
> > (\Omega_1,\mathcal F_1,P_1)
> > \qquad
> > (\Omega_2,\mathcal F_2,P_2)
> > }$$
> >
> > and construct one combined probability space:
> >
> > $$\boxed{
> > (\Omega_1\times\Omega_2,\mathcal F_1\otimes\mathcal F_2,P)
> > }$$
> >
> > with
> >
> > $$\boxed{
> > P(A_1\times A_2)=P_1(A_1)P_2(A_2).
> > }$$
> >
> > **Mental model:**
> >
> > $$\boxed{
> > \text{Product space = combine separate experiments into one experiment}
> > }$$
> >
> > The idea will become especially useful later when dealing with **random vectors, independent random variables, joint distributions, and repeated experiments**.




