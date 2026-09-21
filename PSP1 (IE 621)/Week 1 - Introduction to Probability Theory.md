
> [!important]- Random Experiments, Outcomes, and Sample Spaces
>
> > [!abstract]- Context: What Is Probability Theory?
> >
> > **Probability theory** is a mathematical framework for studying experiments and situations involving **randomness**.
> >
> > The basic structure is:
> >
> > $$\boxed{
> > \text{Random Experiment}
> > \rightarrow
> > \text{Outcomes}
> > \rightarrow
> > \text{Sample Space}
> > \rightarrow
> > \text{Events}
> > }$$
> >
> > We first describe what can happen, and then use probability to quantify how likely different events are.
>
> > [!important]- Random Experiment
> >
> > A **random experiment** is a repeatable activity or process:
> >
> > - whose possible outcomes are known or can be specified in advance
> > - but whose exact outcome cannot be predicted with certainty before the experiment is performed.
> >
> > **Examples:**
> >
> > - Tossing a coin
> > - Rolling a die
> > - Drawing a card
> > - Measuring the lifetime of a component
> >
> > The important feature is **uncertainty about the realized outcome**.
>
> > [!abstract]- Outcome
> >
> > An **outcome** is a single possible result of a random experiment.
> >
> > We usually denote an outcome by
> >
> > $$\omega.$$
> >
> > An outcome belongs to the sample space:
> >
> > $$\boxed{\omega\in\Omega}.$$
> >
> > For example, when rolling a die:
> >
> > $$\Omega=\{1,2,3,4,5,6\}.$$
> >
> > If the die actually shows $4$, then the realized outcome is
> >
> > $$\omega=4.$$
>
> > [!important]- Sample Space
> >
> > The **sample space** $\Omega$ is the set of **all possible outcomes** of a random experiment.
> >
> > $$\boxed{
> > \Omega=\{\omega:\omega\text{ is a possible outcome}\}
> > }$$
> >
> > Every outcome that can occur must belong to $\Omega$.
> >
> > **Example:**
> >
> > For a single coin toss:
> >
> > $$\Omega=\{H,T\}.$$
> >
> > For two coin tosses:
> >
> > $$\Omega=\{HH,HT,TH,TT\}.$$
>
> > [!abstract]- Types of Sample Spaces
> >
> > Sample spaces can be classified according to the number of possible outcomes.
>
> > [!abstract]- Finite Sample Space
> >
> > A sample space is **finite** if it contains finitely many outcomes:
> >
> > $$\boxed{|\Omega|<\infty}.$$
> >
> > **Single coin toss:**
> >
> > $$\Omega=\{H,T\}.$$
> >
> > **Double coin toss:**
> >
> > $$\Omega=\{HH,HT,TH,TT\}.$$
> >
> > In the double-toss example,
> >
> > $$|\Omega|=4.$$
>
> > [!abstract]- Countably Infinite Sample Space
> >
> > A sample space is **countably infinite** if its outcomes can be put into one-to-one correspondence with the natural numbers.
> >
> > For example:
> >
> > $$\Omega=\{0,1,2,3,\ldots\}=\mathbb N_0.$$
> >
> > Suppose $\Omega$ represents the number of visitors to a coffee shop on a particular day.
> >
> > The number could be $0,1,2,\ldots$, so the sample space is countably infinite.
> >
> > $$\boxed{|\Omega|=|\mathbb N_0|}.$$
>
> > [!abstract]- Uncountable Sample Space
> >
> > A sample space is **uncountable** when its outcomes cannot be put into one-to-one correspondence with the natural numbers.
> >
> > For example:
> >
> > **Breaking a unit-length stick at a point:**
> >
> > $$\Omega=[0,1].$$
> >
> > **A positive-valued quantity such as a future stock price:**
> >
> > $$\Omega=(0,\infty).$$
> >
> > These sets have the same cardinality as $\mathbb R$:
> >
> > $$\boxed{|\Omega|=|\mathbb R|}.$$
> >
> > The key distinction is:
> >
> > $$\boxed{
> > \text{Finite}\quad\rightarrow\quad\text{Countably infinite}\quad\rightarrow\quad\text{Uncountable}
> > }$$
>
> > [!important]- Events
> >
> > An **event** is a subset of the sample space:
> >
> > $$\boxed{E\subseteq\Omega}.$$
> >
> > An event occurs when the realized outcome belongs to that event:
> >
> > $$\boxed{\omega\in E.}$$
> >
> > So:
> >
> > $$\text{Outcome}=\text{one possible result}$$
> >
> > $$\text{Event}=\text{collection of possible outcomes}$$
> >
> > **Example:** For a die roll,
> >
> > $$\Omega=\{1,2,3,4,5,6\}.$$
> >
> > The event
> >
> > $$A=\{2,4,6\}$$
> >
> > represents "the die shows an even number."
>
> > [!abstract]- Certain and Impossible Events
> >
> > **Certain event:**
> >
> > The entire sample space $\Omega$ is the event that always occurs:
> >
> > $$\boxed{E=\Omega}.$$
> >
> > Since every possible outcome belongs to $\Omega$,
> >
> > $$\omega\in\Omega$$
> >
> > is always true.
> >
> > **Impossible event:**
> >
> > The empty set represents an event that can never occur:
> >
> > $$\boxed{E=\emptyset}.$$
> >
> > No outcome belongs to $\emptyset$.
>
> > [!important]- Fundamental Set Operations on Events
> >
> > Events are sets, so we can use standard **set operations** to construct new events from existing events.
>
> > [!abstract]- Complement
> >
> > The complement of $A$ is the event that **$A$ does not occur**.
> >
> > $$\boxed{
> > A^c=\Omega\setminus A
> > }$$
> >
> > Equivalently,
> >
> > $$A^c=\{\omega\in\Omega:\omega\notin A\}.$$
> >
> > **Example:** If
> >
> > $$A=\{2,4,6\}$$
> >
> > for a die roll, then
> >
> > $$A^c=\{1,3,5\}.$$
>
> > [!abstract]- Union
> >
> > The union $A\cup B$ is the event that **$A$ or $B$ occurs, or both**.
> >
> > $$\boxed{
> > A\cup B=
> > \{\omega\in\Omega:\omega\in A\text{ or }\omega\in B\}
> > }$$
> >
> > The word **"or"** in set theory is usually inclusive:
> >
> > $$\text{A or B or both}.$$
>
> > [!abstract]- Intersection
> >
> > The intersection $A\cap B$ is the event that **both $A$ and $B$ occur**.
> >
> > $$\boxed{
> > A\cap B=
> > \{\omega\in\Omega:\omega\in A\text{ and }\omega\in B\}
> > }$$
> >
> > Therefore, an outcome must belong to **both** sets.
>
> > [!abstract]- Set Difference
> >
> > The set difference $A\setminus B$ is the event that **$A$ occurs but $B$ does not**.
> >
> > $$\boxed{
> > A\setminus B=
> > \{\omega\in\Omega:\omega\in A,\ \omega\notin B\}
> > }$$
> >
> > It can also be written as
> >
> > $$\boxed{A\setminus B=A\cap B^c.}$$
>
> > [!abstract]- Symmetric Difference
> >
> > The symmetric difference $A\Delta B$ is the event that **exactly one** of $A$ and $B$ occurs.
> >
> > $$\boxed{
> > A\Delta B=(A\setminus B)\cup(B\setminus A)
> > }$$
> >
> > Equivalently,
> >
> > $$A\Delta B=(A\cup B)\setminus(A\cap B).$$
> >
> > So:
> >
> > $$\boxed{\text{A or B, but not both}}.$$
>
> > [!warning]- Disjoint / Mutually Exclusive Events
> >
> > Two events $A$ and $B$ are **disjoint** or **mutually exclusive** if they cannot occur together.
> >
> > Mathematically:
> >
> > $$\boxed{A\cap B=\emptyset}.$$
> >
> > Therefore,
> >
> > $$P(A\cap B)=0.$$
> >
> > **Example:** In one die roll:
> >
> > $$A=\{1,2\}$$
> >
> > $$B=\{5,6\}.$$
> >
> > Then
> >
> > $$A\cap B=\emptyset.$$
> >
> > They cannot occur simultaneously in a single die roll.
>
> > [!abstract]- Event Inclusion
> >
> > We say that $A$ is contained in $B$ if
> >
> > $$\boxed{A\subseteq B}.$$
> >
> > This means every outcome that belongs to $A$ also belongs to $B$:
> >
> > $$\omega\in A\implies\omega\in B.$$
> >
> > In probability language:
> >
> > $$\boxed{
> > \text{If }A\text{ occurs, then }B\text{ necessarily occurs.}
> > }$$
> >
> > **Example:**
> >
> > For a die roll, let
> >
> > $$A=\{2\}$$
> >
> > and
> >
> > $$B=\{2,4,6\}.$$
> >
> > Then
> >
> > $$A\subseteq B.$$
> >
> > If the outcome is $2$, then it is necessarily even.
>
> > [!important]- The Big Picture
> >
> > Probability starts with a random experiment:
> >
> > $$\boxed{\text{Random Experiment}}$$
> >
> > which produces an outcome:
> >
> > $$\boxed{\omega\in\Omega}.$$
> >
> > The set of all possible outcomes is the sample space:
> >
> > $$\boxed{\Omega=\{\text{all possible outcomes}\}}.$$
> >
> > Events are subsets of the sample space:
> >
> > $$\boxed{E\subseteq\Omega}.$$
> >
> > Set operations allow us to construct new events:
> >
> > $$A^c,\quad A\cup B,\quad A\cap B,\quad A\setminus B,\quad A\Delta B.$$
> >
> > This gives the basic language needed before introducing the probability measure:
> >
> > $$\boxed{(\Omega,\mathcal F,P)}.$$
> >
> > where $\Omega$ describes **what can happen**, $\mathcal F$ describes **which events we can assign probabilities to**, and $P$ describes **how likely those events are**.

> [!important]- Discrete Probability Spaces $(\Omega,p)$
>
> > [!abstract]- Context: From Outcomes to Probabilities
> >
> > A sample space tells us **what can happen**:
> >
> > $$\Omega=\{\text{all possible outcomes}\}.$$
> >
> > But we also need a way to describe **how likely each outcome is**.
> >
> > In a discrete setting, we do this by assigning a probability to every individual outcome.
> >
> > This gives us a **discrete probability space**.
> >
> > $$\boxed{(\Omega,p)}$$
>
> > [!abstract]- Discrete Sample Space
> >
> > A sample space $\Omega$ is **discrete** if it is either:
> >
> > **Finite:**
> >
> > $$|\Omega|<\infty$$
> >
> > or
> >
> > **Countably infinite:**
> >
> > $$|\Omega|=|\mathbb N_0|.$$
> >
> > **Examples:**
> >
> > Coin toss:
> >
> > $$\Omega=\{H,T\}$$
> >
> > Number of customers:
> >
> > $$\Omega=\{0,1,2,\ldots\}.$$
> >
> > The important point is that the outcomes can be **listed**.
>
> > [!important]- Probability Mass Function
> >
> > In a discrete probability space, we assign a probability to each individual outcome using a function
> >
> > $$\boxed{p:\Omega\rightarrow[0,1].}$$
> >
> > For every outcome $\omega\in\Omega$,
> >
> > $$p(\omega)$$
> >
> > represents the probability assigned to that outcome.
> >
> > It is often called the **probability mass function (PMF)**.
> >
> > For example, for a fair coin:
> >
> > $$p(H)=\frac12,\qquad p(T)=\frac12.$$
>
> > [!important]- Normalization Axiom
> >
> > The probabilities assigned to **all possible outcomes must add up to $1$**:
> >
> > $$\boxed{
> > \sum_{\omega\in\Omega}p(\omega)=1.
> > }$$
> >
> > Why?
> >
> > Because exactly one outcome from $\Omega$ must occur.
> >
> > The total probability of all possible outcomes must therefore be $1$.
> >
> > Also, since $p$ maps into $[0,1]$:
> >
> > $$\boxed{0\leq p(\omega)\leq1.}$$
>
> > [!abstract]- Formal Definition
> >
> > A **discrete probability space** can be represented by the ordered pair
> >
> > $$\boxed{(\Omega,p)}$$
> >
> > where:
> >
> > $$\Omega=\text{discrete sample space}$$
> >
> > and
> >
> > $$p:\Omega\to[0,1]$$
> >
> > satisfies
> >
> > $$\sum_{\omega\in\Omega}p(\omega)=1.$$
> >
> > In the discrete setting, this is enough to determine the probability of every event.
>
> > [!important]- Probability of an Event
> >
> > An event is a subset of the sample space:
> >
> > $$E\subseteq\Omega.$$
> >
> > To find the probability of $E$, add the probabilities of all outcomes belonging to $E$:
> >
> > $$\boxed{
> > P(E)=\sum_{\omega\in E}p(\omega).
> > }$$
> >
> > Therefore:
> >
> > $$\boxed{
> > \text{Probability of event}
> > =
> > \text{sum of probabilities of its outcomes}
> > }$$
>
> > [!example]- Simple Example
> >
> > Consider a die:
> >
> > $$\Omega=\{1,2,3,4,5,6\}.$$
> >
> > Suppose it is fair:
> >
> > $$p(\omega)=\frac16
> > \qquad\text{for every }\omega\in\Omega.$$
> >
> > Let
> >
> > $$E=\{2,4,6\}$$
> >
> > be the event that an even number is rolled.
> >
> > Then:
> >
> > $$P(E)
> > =p(2)+p(4)+p(6)$$
> >
> > $$=\frac16+\frac16+\frac16$$
> >
> > $$=\frac36=\frac12.$$
>
> > [!abstract]- Basic Properties of Event Probability
> >
> > Since $P(E)$ is obtained by summing non-negative probabilities:
> >
> > $$\boxed{0\leq P(E)\leq1.}$$
> >
> > For the entire sample space:
> >
> > $$P(\Omega)
> > =\sum_{\omega\in\Omega}p(\omega)
> > =1.$$
> >
> > Therefore:
> >
> > $$\boxed{P(\Omega)=1.}$$
> >
> > For the empty event:
> >
> > $$P(\emptyset)=\sum_{\omega\in\emptyset}p(\omega)=0.$$
> >
> > Hence:
> >
> > $$\boxed{P(\emptyset)=0.}$$
>
> > [!important]- Equally Likely Outcomes
> >
> > Sometimes every outcome in a **finite** sample space has the same probability.
> >
> > If all outcomes are equally likely, then:
> >
> > $$p(\omega)=\frac1{|\Omega|}
> > \qquad\text{for every }\omega\in\Omega.$$
> >
> > This is the classical **Laplace** model of probability.
> >
> > The normalization condition explains the formula:
> >
> > $$\sum_{\omega\in\Omega}p(\omega)
> > =|\Omega|\cdot p(\omega)=1,$$
> >
> > so
> >
> > $$p(\omega)=\frac1{|\Omega|}.$$
>
> > [!important]- Uniform Probability Formula
> >
> > If all outcomes in a finite sample space are equally likely, then for an event $E\subseteq\Omega$:
> >
> > $$P(E)=\sum_{\omega\in E}\frac1{|\Omega|}.$$
> >
> > Since there are $|E|$ outcomes in $E$:
> >
> > $$\boxed{
> > P(E)=\frac{|E|}{|\Omega|}
> > }.$$
> >
> > In words:
> >
> > $$\boxed{
> > P(E)=
> > \frac{\text{number of favorable outcomes}}
> > {\text{total number of possible outcomes}}
> > }.$$
>
> > [!example]- Example: Two Dice
> >
> > Roll two fair dice.
> >
> > The sample space contains
> >
> > $$|\Omega|=6\times6=36$$
> >
> > equally likely outcomes.
> >
> > Let
> >
> > $$E=\{\text{sum is }7\}.$$
> >
> > The outcomes giving a sum of $7$ are:
> >
> > $$(1,6),(2,5),(3,4),(4,3),(5,2),(6,1).$$
> >
> > Therefore:
> >
> > $$|E|=6.$$
> >
> > Hence:
> >
> > $$P(E)=\frac{|E|}{|\Omega|}
> > =\frac6{36}
> > =\frac16.$$
>
> > [!abstract]- General vs Uniform Probability
> >
> > **General discrete probability:**
> >
> > Different outcomes can have different probabilities:
> >
> > $$p(\omega_1)\neq p(\omega_2).$$
> >
> > We calculate:
> >
> > $$P(E)=\sum_{\omega\in E}p(\omega).$$
> >
> > **Uniform probability:**
> >
> > Every outcome has the same probability:
> >
> > $$p(\omega)=\frac1{|\Omega|}.$$
> >
> > Therefore:
> >
> > $$P(E)=\frac{|E|}{|\Omega|}.$$
> >
> > So the familiar "favorable outcomes / total outcomes" formula is **not the general definition of probability**. It is a special case that works when the finite outcomes are equally likely.
>
> > [!important]- Big Picture
> >
> > The construction can be viewed as:
> >
> > $$\boxed{
> > \Omega
> > \xrightarrow{\quad p\quad}
> > \text{probability of each outcome}
> > }$$
> >
> > Then for an event $E\subseteq\Omega$:
> >
> > $$\boxed{
> > P(E)=\sum_{\omega\in E}p(\omega).
> > }$$
> >
> > And when all finite outcomes are equally likely:
> >
> > $$\boxed{
> > P(E)=\frac{|E|}{|\Omega|}.
> > }$$
> >
> > **Mental model:**
> >
> > $$\boxed{
> > \text{Sample space = what can happen}
> > }$$
> >
> > $$\boxed{
> > p = \text{how much probability each outcome gets}
> > }$$
> >
> > $$\boxed{
> > P(E)=\text{total probability assigned to outcomes in }E
> > }$$

---

> [!important]- Countable Additivity
>
> > [!abstract]- Context: Why Do We Need Countable Additivity?
> >
> > Probability should behave consistently when we break an event into smaller pieces.
> >
> > For a finite collection of **disjoint events**, we already expect:
> >
> > $$P(A_1\cup A_2)=P(A_1)+P(A_2)$$
> >
> > and more generally,
> >
> > $$P\left(\bigcup_{i=1}^nA_i\right)
> > =\sum_{i=1}^nP(A_i).$$
> >
> > But probability theory also needs to handle **infinitely many events**.
> >
> > Countable additivity extends this idea from finite collections to **countably infinite collections**.
>
> > [!important]- Definition: Countable Additivity
> >
> > Let
> >
> > $$A_1,A_2,A_3,\ldots\in\mathcal F$$
> >
> > be a sequence of pairwise disjoint events:
> >
> > $$A_i\cap A_j=\emptyset,
> > \qquad i\neq j.$$
> >
> > Then a probability measure $P$ satisfies **countable additivity** if
> >
> > $$\boxed{
> > P\left(\bigcup_{i=1}^{\infty}A_i\right)
> > =
> > \sum_{i=1}^{\infty}P(A_i).
> > }$$
> >
> > Using disjoint-union notation:
> >
> > $$\boxed{
> > P\left(\bigsqcup_{i\geq1}A_i\right)
> > =
> > \sum_{i=1}^{\infty}P(A_i).
> > }$$
> >
> > **Core idea:**
> >
> > $$\boxed{
> > \text{Probability of disjoint pieces}
> > =
> > \text{sum of probabilities of the pieces}
> > }$$
>
> > [!example]- Simple Example
> >
> > Suppose a fair die is rolled and define:
> >
> > $$A_1=\{1\},\qquad A_2=\{2\},\qquad A_3=\{3\}.$$
> >
> > These events are pairwise disjoint.
> >
> > Therefore:
> >
> > $$P(A_1\cup A_2\cup A_3)
> > =P(A_1)+P(A_2)+P(A_3)$$
> >
> > $$=\frac16+\frac16+\frac16
> > =\frac12.$$
> >
> > Countable additivity is the same principle extended to an infinite sequence of disjoint events.
>
> > [!abstract]- Why "Countable"?
> >
> > **Countable** means that the collection can be indexed by
> >
> > $$1,2,3,\ldots$$
> >
> > So countable additivity applies to:
> >
> > $$A_1,A_2,A_3,\ldots$$
> >
> > It does **not** say that we can simply add probabilities over an arbitrary uncountable collection of disjoint events.
> >
> > This distinction becomes important when we study continuous probability spaces.
>
> > [!important]- Finite Additivity Follows
> >
> > Countable additivity automatically gives **finite additivity**.
> >
> > Suppose $A_1,\ldots,A_n$ are pairwise disjoint.
> >
> > We can define
> >
> > $$A_{n+1}=A_{n+2}=\cdots=\emptyset.$$
> >
> > Since
> >
> > $$P(\emptyset)=0,$$
> >
> > countable additivity gives
> >
> > $$P\left(\bigcup_{i=1}^\infty A_i\right)
> > =\sum_{i=1}^\infty P(A_i),$$
> >
> > which reduces to
> >
> > $$\boxed{
> > P\left(\bigcup_{i=1}^nA_i\right)
> > =
> > \sum_{i=1}^nP(A_i).
> > }$$
> >
> > Therefore:
> >
> > $$\boxed{
> > \text{Countable additivity}\Rightarrow\text{finite additivity}.
> > }$$
>
> > [!important]- Countable Subadditivity
> >
> > What if the events are **not disjoint**?
> >
> > We cannot simply add their probabilities because overlapping parts may be counted multiple times.
> >
> > Nevertheless, probability satisfies the inequality
> >
> > $$\boxed{
> > P\left(\bigcup_{i=1}^{\infty}A_i\right)
> > \leq
> > \sum_{i=1}^{\infty}P(A_i).
> > }$$
> >
> > This is called **countable subadditivity** or **Boole's inequality**.
> >
> > It applies to **any** sequence of events, whether they overlap or not.
>
> > [!abstract]- Why Is It an Inequality?
> >
> > Suppose $A$ and $B$ overlap.
> >
> > Then
> >
> > $$P(A)+P(B)$$
> >
> > counts the overlapping region twice.
> >
> > But
> >
> > $$P(A\cup B)$$
> >
> > counts it only once.
> >
> > Therefore:
> >
> > $$P(A\cup B)\leq P(A)+P(B).$$
> >
> > The same idea extends to countably many events.
> >
> > **Disjoint:**
> >
> > $$P\left(\bigcup_iA_i\right)=\sum_iP(A_i).$$
> >
> > **Possibly overlapping:**
> >
> > $$P\left(\bigcup_iA_i\right)\leq\sum_iP(A_i).$$
>
> > [!important]- Why Does Measure Theory Become Necessary?
> >
> > So far, discrete probability is relatively easy because we can assign probabilities to individual outcomes and sum them.
> >
> > But what happens when the sample space is **uncountable**?
> >
> > Consider a continuous experiment such as choosing a point uniformly from
> >
> > $$\Omega=[0,1].$$
> >
> > We would naturally like probability to correspond to **length**:
> >
> > $$\boxed{
> > P([a,b])=b-a
> > }$$
> >
> > for
> >
> > $$0\leq a\leq b\leq1.$$
>
> > [!abstract]- The Problem with Individual Points
> >
> > If probability corresponds to interval length, then a single point should have zero length:
> >
> > $$\boxed{
> > P(\{\omega\})=0
> > \qquad\text{for every }\omega\in[0,1].
> > }$$
> >
> > This may initially seem strange because the entire interval has probability $1$:
> >
> > $$P([0,1])=1.$$
> >
> > Every individual point has probability $0$, yet the entire interval has probability $1$.
> >
> > This is perfectly possible because **countable additivity applies only to countable unions**.
> >
> > The interval $[0,1]$ is an **uncountable union** of its individual points:
> >
> > $$[0,1]=\bigcup_{\omega\in[0,1]}\{\omega\}.$$
> >
> > We cannot use countable additivity to conclude that the probability of this uncountable union is
> >
> > $$\sum_{\omega\in[0,1]}P(\{\omega\}).$$
> >
> > That would be an invalid application of countable additivity.
>
> > [!warning]- The Full Power Set Problem
> >
> > One might try to define probability on **every subset** of $[0,1]$:
> >
> > $$P:2^{[0,1]}\rightarrow[0,1].$$
> >
> > However, there is no probability measure on the full power set $2^{[0,1]}$ that simultaneously:
> >
> > - assigns intervals their usual lengths, and
> > - satisfies countable additivity.
> >
> > In other words, we cannot consistently assign probabilities to **all possible subsets** of an uncountable space while retaining the desired properties.
> >
> > This is one of the reasons measure theory is needed.
>
> > [!important]- Measure-Theoretic Solution: $\sigma$-Fields
> >
> > Instead of requiring $P$ to be defined on every subset of $\Omega$, we restrict its domain to a carefully chosen collection of subsets:
> >
> > $$\boxed{\mathcal F\subseteq2^\Omega.}$$
> >
> > This collection $\mathcal F$ is called a **$\sigma$-field** (or $\sigma$-algebra).
> >
> > The sets in $\mathcal F$ are called **measurable sets**.
> >
> > We then define probability as
> >
> > $$\boxed{
> > P:\mathcal F\rightarrow[0,1].
> > }$$
> >
> > The probability space becomes
> >
> > $$\boxed{(\Omega,\mathcal F,P).}$$
> >
> > The $\sigma$-field gives us a mathematically consistent collection of events on which probability can be defined.
>
> > [!abstract]- Why $\sigma$-Fields Matter
> >
> > A $\sigma$-field is designed to be closed under the operations needed for probability theory:
> >
> > - complements
> > - countable unions
> > - consequently, countable intersections
> >
> > This allows us to perform probability calculations involving limits and countably many events while maintaining mathematical consistency.
> >
> > Thus, in continuous probability:
> >
> > $$\boxed{
> > \text{Sample space}
> > \rightarrow
> > \text{measurable events}
> > \rightarrow
> > \text{probability measure}
> > }$$
>
> > [!important]- Big Picture
> >
> > The development can be viewed as:
> >
> > $$\boxed{
> > \text{Finite additivity}
> > \longrightarrow
> > \text{Countable additivity}
> > \longrightarrow
> > \text{Measure theory}
> > }$$
> >
> > Countable additivity gives the fundamental rule:
> >
> > $$\boxed{
> > P\left(\bigsqcup_{i=1}^{\infty}A_i\right)
> > =
> > \sum_{i=1}^{\infty}P(A_i).
> > }$$
> >
> > For arbitrary events:
> >
> > $$\boxed{
> > P\left(\bigcup_{i=1}^{\infty}A_i\right)
> > \leq
> > \sum_{i=1}^{\infty}P(A_i).
> > }$$
> >
> > And for continuous spaces, we work with
> >
> > $$\boxed{(\Omega,\mathcal F,P)}$$
> >
> > rather than trying to assign probabilities to every subset of $\Omega$.
>
> > [!tip]- Mental Model
> >
> > **Countable additivity:**
> >
> > $$\boxed{\text{Disjoint pieces → add their probabilities}}$$
> >
> > **Countable subadditivity:**
> >
> > $$\boxed{\text{Overlapping pieces → sum is an upper bound}}$$
> >
> > **Continuous spaces:**
> >
> > $$\boxed{\text{Not every subset needs to be measurable}}$$
> >
> > **Measure theory:**
> >
> > $$\boxed{\text{Provides the rigorous framework for probability on continuous spaces.}}$$

> [!important]- $\sigma$-Fields ($\sigma$-Algebras)
>
> > [!abstract]- Context: Why Do We Need a $\sigma$-Field?
> >
> > In probability, we start with a sample space $\Omega$ containing all possible outcomes.
> >
> > $$\Omega=\{\text{all possible outcomes}\}.$$
> >
> > We then want to assign probabilities to events, which are subsets of $\Omega$.
> >
> > For a finite or discrete sample space, we can often assign probabilities to every subset:
> >
> > $$\mathcal F=2^\Omega.$$
> >
> > But for general, especially **uncountable**, sample spaces, assigning probabilities consistently to every subset is not always possible.
> >
> > Therefore, we select a collection of subsets on which probability can be consistently defined.
> >
> > This collection is called a **$\sigma$-field**.
> >
> > $$\boxed{
> > \mathcal F=\text{collection of measurable events}
> > }$$
> >
> > The resulting probability space is
> >
> > $$\boxed{(\Omega,\mathcal F,P).}$$
>
> > [!important]- Formal Definition
> >
> > A collection
> >
> > $$\mathcal F\subseteq2^\Omega$$
> >
> > is called a **$\sigma$-field** (or $\sigma$-algebra) if it satisfies the required closure properties.
> >
> > The three conditions are:
> >
> > $$\boxed{\emptyset\in\mathcal F,\qquad \Omega\in\mathcal F}$$
> >
> > $$\boxed{A\in\mathcal F\implies A^c\in\mathcal F}$$
> >
> > $$\boxed{
> > A_1,A_2,\ldots\in\mathcal F
> > \implies
> > \bigcup_{i=1}^{\infty}A_i\in\mathcal F
> > }$$
> >
> > These conditions ensure that $\mathcal F$ is sufficiently stable for probability theory.
>
> > [!abstract]- Boundary Inclusion
> >
> > A $\sigma$-field must contain both the empty set and the entire sample space:
> >
> > $$\boxed{\emptyset\in\mathcal F,\qquad\Omega\in\mathcal F.}$$
> >
> > This makes sense because:
> >
> > - $\Omega$ is the **certain event**
> > - $\emptyset$ is the **impossible event**
> >
> > Their probabilities are:
> >
> > $$P(\Omega)=1,\qquad P(\emptyset)=0.$$
>
> > [!abstract]- Closure Under Complements
> >
> > If an event is measurable, then its complement must also be measurable:
> >
> > $$\boxed{
> > A\in\mathcal F\implies A^c\in\mathcal F.
> > }$$
> >
> > This is necessary because if we can assign a probability to $A$, we should also be able to assign a probability to the event **"A does not occur."**
> >
> > For example, if
> >
> > $$A=\{\text{die shows an even number}\},$$
> >
> > then
> >
> > $$A^c=\{\text{die shows an odd number}\}.$$
> >
> > Both should be measurable events.
>
> > [!abstract]- Closure Under Countable Unions
> >
> > If
> >
> > $$A_1,A_2,A_3,\ldots\in\mathcal F,$$
> >
> > then their countable union must also belong to $\mathcal F$:
> >
> > $$\boxed{
> > \bigcup_{i=1}^{\infty}A_i\in\mathcal F.
> > }$$
> >
> > This is particularly important because probability measures satisfy **countable additivity**.
> >
> > We therefore need the collection of measurable events to remain closed when we combine countably many events.
>
> > [!abstract]- Other Closure Properties
> >
> > The three axioms imply several useful properties.
> >
> > **Countable intersections:**
> >
> > $$A_i\in\mathcal F\ \forall i
> > \implies
> > \bigcap_{i=1}^{\infty}A_i\in\mathcal F.$$
> >
> > This follows from De Morgan's law:
> >
> > $$\bigcap_{i=1}^{\infty}A_i
> > =
> > \left(\bigcup_{i=1}^{\infty}A_i^c\right)^c.$$
> >
> > **Finite unions and intersections** are therefore also in $\mathcal F$.
> >
> > **Set differences** are measurable:
> >
> > $$A,B\in\mathcal F
> > \implies
> > A\setminus B\in\mathcal F,$$
> >
> > because
> >
> > $$A\setminus B=A\cap B^c.$$
>
> > [!important]- Trivial $\sigma$-Field
> >
> > The smallest possible $\sigma$-field on $\Omega$ is
> >
> > $$\boxed{
> > \mathcal F_{\text{trivial}}=\{\emptyset,\Omega\}.
> > }$$
> >
> > It contains only two events:
> >
> > - the impossible event
> > - the certain event
> >
> > It satisfies all three $\sigma$-field properties.
> >
> > This is the **minimum amount of information** a $\sigma$-field can contain.
>
> > [!important]- $\sigma$-Field Generated by a Single Event
> >
> > Given any set
> >
> > $$A\subseteq\Omega,$$
> >
> > the smallest $\sigma$-field containing $A$ is
> >
> > $$\boxed{
> > \mathcal F_A=\{\emptyset,\Omega,A,A^c\}.
> > }$$
> >
> > Why are these four sets needed?
> >
> > If $A$ must be measurable, then:
> >
> > $$A\in\mathcal F.$$
> >
> > Closure under complements requires:
> >
> > $$A^c\in\mathcal F.$$
> >
> > Boundary inclusion requires:
> >
> > $$\emptyset,\Omega\in\mathcal F.$$
> >
> > Thus these four sets form the smallest $\sigma$-field containing $A$.
>
> > [!important]- Power Set $\sigma$-Field
> >
> > The **power set** of $\Omega$ is
> >
> > $$2^\Omega=\{A:A\subseteq\Omega\}.$$
> >
> > It contains **every possible subset** of $\Omega$.
> >
> > Therefore,
> >
> > $$\boxed{\mathcal F=2^\Omega}$$
> >
> > is the **largest possible $\sigma$-field** on $\Omega$.
> >
> > For discrete sample spaces, this is commonly used:
> >
> > $$\boxed{
> > \mathcal F_{\text{discrete}}=2^\Omega.
> > }$$
> >
> > In that case, every subset of $\Omega$ is a measurable event.
>
> > [!abstract]- Borel $\sigma$-Field
> >
> > For continuous spaces such as
> >
> > $$\Omega=[0,1],$$
> >
> > using the entire power set $2^{[0,1]}$ is too large for the probability theory we want to construct.
> >
> > Instead, we use the **Borel $\sigma$-field**:
> >
> > $$\boxed{\mathcal B([0,1])}.$$
> >
> > It is the $\sigma$-field generated by the open subsets of $[0,1]$.
> >
> > In particular, it contains sets such as:
> >
> > $$[a,b],\qquad(a,b),\qquad[a,b),\qquad(a,b]$$
> >
> > and sets obtained from these through countable unions, countable intersections, and complements.
> >
> > We have
> >
> > $$\boxed{
> > \mathcal B([0,1])\subsetneq2^{[0,1]}.
> > }$$
> >
> > Thus, not every subset of $[0,1]$ is necessarily Borel measurable.
>
> > [!tip]- Why the Word "$\sigma$"?
> >
> > The "$\sigma$" refers to the fact that the collection is closed under **countable** operations, especially countable unions:
> >
> > $$A_1,A_2,\ldots\in\mathcal F
> > \implies
> > \bigcup_{i=1}^{\infty}A_i\in\mathcal F.$$
> >
> > This connects directly to **countable additivity** of probability.
>
> > [!important]- Relationship Between $\Omega$, $\mathcal F$, and $P$
> >
> > These three objects have different roles:
> >
> > $$\boxed{\Omega=\text{possible outcomes}}$$
> >
> > $$\boxed{\mathcal F=\text{events to which probability can be assigned}}$$
> >
> > $$\boxed{P=\text{probability assigned to those events}}$$
> >
> > Together:
> >
> > $$\boxed{(\Omega,\mathcal F,P)}$$
> >
> > is a **probability space**.
> >
> > The important distinction is:
> >
> > $$\mathcal F\subseteq2^\Omega.$$
> >
> > Not every subset of $\Omega$ must belong to $\mathcal F$.
>
> > [!important]- Big Picture
> >
> > The development of probability can now be viewed as:
> >
> > $$\boxed{
> > \Omega
> > \longrightarrow
> > \mathcal F
> > \longrightarrow
> > P
> > }$$
> >
> > **Sample space $\Omega$:**
> >
> > What can happen?
> >
> > **$\sigma$-field $\mathcal F$:**
> >
> > Which subsets count as measurable events?
> >
> > **Probability measure $P$:**
> >
> > How likely are those measurable events?
> >
> > Therefore:
> >
> > $$\boxed{
> > (\Omega,\mathcal F,P)
> > =
> > \text{sample space + measurable events + probabilities}
> > }$$
>
> > [!abstract]- Mental Model
> >
> > Think of $2^\Omega$ as **all possible subsets** of $\Omega$.
> >
> > A $\sigma$-field $\mathcal F$ selects a mathematically well-behaved collection:
> >
> > $$\boxed{
> > \mathcal F\subseteq2^\Omega.
> > }$$
> >
> > Probability is then defined only on $\mathcal F$:
> >
> > $$\boxed{
> > P:\mathcal F\rightarrow[0,1].
> > }$$
> >
> > So a $\sigma$-field is essentially the **allowed universe of measurable events** on which probability theory operates.

> [!important]- General Probability Space $(\Omega,\mathcal F,P)$
>
> > [!abstract]- Context: From Discrete to General Probability
> >
> > In a discrete probability space, we could often assign probabilities directly to individual outcomes.
> >
> > But probability theory must also handle **continuous and more complicated random experiments**.
> >
> > To create one framework that works for both discrete and continuous settings, we use the triple
> >
> > $$\boxed{(\Omega,\mathcal F,P)}.$$
> >
> > This is called a **probability space**.
> >
> > The three components answer three different questions:
> >
> > $$\boxed{\Omega=\text{What can happen?}}$$
> >
> > $$\boxed{\mathcal F=\text{Which events can we measure?}}$$
> >
> > $$\boxed{P=\text{How likely are those events?}}$$
>
> > [!important]- The Three Components
> >
> > **Sample space $\Omega$**
> >
> > $$\boxed{\Omega=\{\text{all possible outcomes}\}}$$
> >
> > It describes every possible outcome of the random experiment.
> >
> > **$\sigma$-field $\mathcal F$**
> >
> > $$\boxed{\mathcal F\subseteq2^\Omega}$$
> >
> > It specifies which subsets of $\Omega$ are considered **measurable events**.
> >
> > **Probability measure $P$**
> >
> > $$\boxed{P:\mathcal F\rightarrow[0,1]}$$
> >
> > It assigns a probability to every measurable event.
> >
> > Together:
> >
> > $$\boxed{(\Omega,\mathcal F,P)}$$
>
> > [!abstract]- Sample Space $\Omega$
> >
> > The sample space contains all possible outcomes:
> >
> > $$\boxed{
> > \Omega=\{\omega:\omega\text{ is a possible outcome}\}.
> > }$$
> >
> > It can be:
> >
> > - finite
> > - countably infinite
> > - uncountable
> >
> > **Example:**
> >
> > For a die:
> >
> > $$\Omega=\{1,2,3,4,5,6\}.$$
> >
> > For choosing a point uniformly from a unit interval:
> >
> > $$\Omega=[0,1].$$
>
> > [!abstract]- $\sigma$-Field $\mathcal F$
> >
> > The $\sigma$-field is a collection of subsets of $\Omega$:
> >
> > $$\boxed{\mathcal F\subseteq2^\Omega}$$
> >
> > whose members are the **measurable events**.
> >
> > It must satisfy:
> >
> > $$\emptyset,\Omega\in\mathcal F,$$
> >
> > $$A\in\mathcal F\implies A^c\in\mathcal F,$$
> >
> > and
> >
> > $$A_1,A_2,\ldots\in\mathcal F
> > \implies
> > \bigcup_{i=1}^{\infty}A_i\in\mathcal F.$$
> >
> > The $\sigma$-field is important because it tells us **where probability is allowed to be defined**.
>
> > [!abstract]- Probability Measure $P$
> >
> > The probability measure is a function
> >
> > $$\boxed{P:\mathcal F\rightarrow[0,1].}$$
> >
> > Thus, for every measurable event $A\in\mathcal F$,
> >
> > $$P(A)$$
> >
> > is a number between $0$ and $1$ representing the probability of $A$.
> >
> > Importantly, $P$ is defined on $\mathcal F$, not necessarily on every subset of $\Omega$.
>
> > [!important]- Kolmogorov's Axioms
> >
> > A probability measure $P$ must satisfy the fundamental axioms introduced by **Kolmogorov**.
>
> > [!abstract]- Non-Negativity
> >
> > Every event has non-negative probability:
> >
> > $$\boxed{
> > P(A)\geq0,\qquad A\in\mathcal F.
> > }$$
> >
> > Probability can never be negative.
>
> > [!abstract]- Normalization
> >
> > The entire sample space has probability $1$:
> >
> > $$\boxed{P(\Omega)=1.}$$
> >
> > Since the empty event is impossible:
> >
> > $$\boxed{P(\emptyset)=0.}$$
> >
> > Therefore:
> >
> > $$\boxed{
> > P(\emptyset)=0,\qquad P(\Omega)=1.
> > }$$
>
> > [!important]- Countable Additivity
> >
> > If
> >
> > $$A_1,A_2,\ldots\in\mathcal F$$
> >
> > are pairwise disjoint:
> >
> > $$A_i\cap A_j=\emptyset,\qquad i\neq j,$$
> >
> > then
> >
> > $$\boxed{
> > P\left(\bigcup_{i=1}^{\infty}A_i\right)
> > =
> > \sum_{i=1}^{\infty}P(A_i).
> > }$$
> >
> > This says that the probability of a countable collection of mutually exclusive events is the sum of their individual probabilities.
>
> > [!abstract]- Some Important Consequences
> >
> > The Kolmogorov axioms imply useful properties such as:
> >
> > $$0\leq P(A)\leq1,$$
> >
> > $$P(A^c)=1-P(A),$$
> >
> > and for any events $A,B$:
> >
> > $$P(A\cup B)
> > =P(A)+P(B)-P(A\cap B).$$
> >
> > If $A$ and $B$ are disjoint:
> >
> > $$P(A\cup B)=P(A)+P(B).$$
>
> > [!important]- Continuous Probability: The Unit Interval
> >
> > Consider a random experiment where a point is selected uniformly from
> >
> > $$[0,1].$$
> >
> > The natural sample space is
> >
> > $$\Omega=[0,1].$$
> >
> > We use the Borel $\sigma$-field:
> >
> > $$\mathcal F=\mathcal B([0,1]).$$
> >
> > We want probability to correspond to **length**.
> >
> > Therefore, for an interval $[a,b]$:
> >
> > $$\boxed{
> > P([a,b])=b-a.
> > }$$
> >
> > For example:
> >
> > $$P([0.2,0.7])=0.7-0.2=0.5.$$
>
> > [!abstract]- Lebesgue Measure $\lambda$
> >
> > The measure that assigns the usual length to intervals is the **Lebesgue measure**, denoted by
> >
> > $$\lambda.$$
> >
> > On the unit interval:
> >
> > $$\boxed{
> > \lambda([a,b])=b-a
> > }$$
> >
> > for
> >
> > $$0\leq a\leq b\leq1.$$
> >
> > Since
> >
> > $$\lambda([0,1])=1,$$
> >
> > it is already normalized and can serve as a probability measure on $[0,1]$.
>
> > [!important]- Formal Continuous Probability Space
> >
> > The uniform probability space on the unit interval is therefore
> >
> > $$\boxed{
> > ([0,1],\mathcal B([0,1]),\lambda).
> > }$$
> >
> > Here:
> >
> > $$[0,1]\quad\rightarrow\quad\text{sample space}$$
> >
> > $$\mathcal B([0,1])\quad\rightarrow\quad\text{measurable events}$$
> >
> > $$\lambda\quad\rightarrow\quad\text{probability measure}.$$
>
> > [!abstract]- Discrete vs Continuous
> >
> > **Discrete example:**
> >
> > $$\Omega=\{1,2,3,4,5,6\},$$
> >
> > $$\mathcal F=2^\Omega,$$
> >
> > $$P(\{i\})=\frac16.$$
> >
> > **Continuous example:**
> >
> > $$\Omega=[0,1],$$
> >
> > $$\mathcal F=\mathcal B([0,1]),$$
> >
> > $$P([a,b])=b-a.$$
> >
> > The underlying framework is the same:
> >
> > $$\boxed{(\Omega,\mathcal F,P)}.$$
> >
> > Only the particular choices of $\Omega$, $\mathcal F$, and $P$ change.
>
> > [!important]- The Complete Probability Framework
> >
> > We can now see how the concepts introduced so far fit together:
> >
> > $$\boxed{
> > \text{Random experiment}
> > \rightarrow
> > \Omega
> > \rightarrow
> > \mathcal F
> > \rightarrow
> > P
> > }$$
> >
> > **Random experiment:** produces uncertainty.
> >
> > **Sample space $\Omega$:** lists all possible outcomes.
> >
> > **$\sigma$-field $\mathcal F$:** identifies the measurable events.
> >
> > **Probability measure $P$:** assigns probabilities to those events.
> >
> > Thus:
> >
> > $$\boxed{
> > (\Omega,\mathcal F,P)
> > =
> > \text{the mathematical model of a random experiment}.
> > }$$
>
> > [!tip]- Mental Model
> >
> > Think of the three components as three layers:
> >
> > $$\boxed{
> > \Omega=\text{possibilities}
> > }$$
> >
> > $$\boxed{
> > \mathcal F=\text{measurable questions about those possibilities}
> > }$$
> >
> > $$\boxed{
> > P=\text{answers in terms of probabilities}
> > }$$
> >
> > Once $(\Omega,\mathcal F,P)$ is defined, we have a complete mathematical framework in which we can study **events, conditional probability, independence, random variables, distributions, and expectations**.

---

> [!important]- Elementary Properties of Probability Measures
>
> > [!abstract]- Context
> >
> > Let
> >
> > $$(\Omega,\mathcal F,P)$$
> >
> > be a probability space, and let
> >
> > $$A,B\in\mathcal F$$
> >
> > be events.
> >
> > From the three basic properties of a probability measure — **non-negativity, normalization, and countable additivity** — we can derive several important rules that are used throughout probability theory.
> >
> > The most fundamental ones are:
> >
> > $$\boxed{
> > \text{Complement Rule}
> > \quad
> > \text{Monotonicity}
> > \quad
> > \text{Inclusion-Exclusion}
> > }$$
>
> > [!important]- Property 1: Complement Rule
> >
> > **Statement**
> >
> > $$\boxed{
> > P(A^c)=1-P(A)
> > }$$
> >
> > This follows from the fact that $A$ and $A^c$ divide the entire sample space into two disjoint parts.
>
> > [!abstract]- Proof
> >
> > We know:
> >
> > $$A\cap A^c=\emptyset$$
> >
> > and
> >
> > $$A\cup A^c=\Omega.$$
> >
> > Since $A$ and $A^c$ are disjoint, additivity gives:
> >
> > $$P(A\cup A^c)=P(A)+P(A^c).$$
> >
> > But
> >
> > $$A\cup A^c=\Omega$$
> >
> > and
> >
> > $$P(\Omega)=1.$$
> >
> > Therefore:
> >
> > $$1=P(A)+P(A^c).$$
> >
> > Hence:
> >
> > $$\boxed{P(A^c)=1-P(A).}$$
>
> > [!tip]- Intuition
> >
> > The events $A$ and $A^c$ together cover **everything**, with no overlap.
> >
> > $$\boxed{
> > \text{Probability of }A
> > +
> > \text{Probability of not }A
> > =1
> > }$$
> >
> > So if
> >
> > $$P(A)=0.7,$$
> >
> > then
> >
> > $$P(A^c)=0.3.$$
>
> > [!important]- Property 2: Monotonicity
> >
> > **Statement**
> >
> > If
> >
> > $$A\subseteq B,$$
> >
> > then
> >
> > $$\boxed{P(A)\leq P(B).}$$
> >
> > More precisely:
> >
> > $$\boxed{
> > P(B)=P(A)+P(B\setminus A)\geq P(A).
> > }$$
> >
> > In words:
> >
> > **A larger event cannot have smaller probability than an event contained inside it.**
>
> > [!abstract]- Proof
> >
> > If
> >
> > $$A\subseteq B,$$
> >
> > then $B$ consists of two disjoint pieces:
> >
> > $$\boxed{
> > B=A\sqcup(B\setminus A).
> > }$$
> >
> > Therefore, by additivity:
> >
> > $$P(B)=P(A)+P(B\setminus A).$$
> >
> > Since probability is non-negative:
> >
> > $$P(B\setminus A)\geq0.$$
> >
> > Hence:
> >
> > $$P(B)\geq P(A).$$
> >
> > Therefore:
> >
> > $$\boxed{A\subseteq B\implies P(A)\leq P(B).}$$
>
> > [!example]- Monotonicity Example
> >
> > Consider a fair die:
> >
> > $$A=\{2\}$$
> >
> > $$B=\{2,4,6\}.$$
> >
> > Clearly:
> >
> > $$A\subseteq B.$$
> >
> > Their probabilities are:
> >
> > $$P(A)=\frac16$$
> >
> > and
> >
> > $$P(B)=\frac36=\frac12.$$
> >
> > Therefore:
> >
> > $$P(A)\leq P(B).$$
> >
> > This illustrates the idea that adding possible outcomes cannot decrease probability.
>
> > [!important]- Property 3: Two-Set Inclusion-Exclusion
> >
> > **Statement**
> >
> > For any two events $A$ and $B$:
> >
> > $$\boxed{
> > P(A\cup B)
> > =
> > P(A)+P(B)-P(A\cap B).
> > }$$
> >
> > The subtraction is necessary because the intersection $A\cap B$ is counted **twice** when we add $P(A)$ and $P(B)$.
>
> > [!abstract]- Why Do We Subtract the Intersection?
> >
> > Think of the union as three disjoint pieces:
> >
> > $$A\cup B
> > =
> > (A\setminus B)
> > \sqcup
> > (A\cap B)
> > \sqcup
> > (B\setminus A).$$
> >
> > Therefore:
> >
> > $$P(A\cup B)
> > =
> > P(A\setminus B)
> > +P(A\cap B)
> > +P(B\setminus A).$$
> >
> > But when we calculate
> >
> > $$P(A)+P(B),$$
> >
> > the intersection appears twice:
> >
> > $$P(A)=P(A\setminus B)+P(A\cap B)$$
> >
> > $$P(B)=P(B\setminus A)+P(A\cap B).$$
> >
> > Hence:
> >
> > $$P(A)+P(B)
> > =
> > P(A\cup B)+P(A\cap B).$$
> >
> > Rearranging:
> >
> > $$\boxed{
> > P(A\cup B)
> > =
> > P(A)+P(B)-P(A\cap B).
> > }$$
>
> > [!abstract]- Alternative Proof
> >
> > Since
> >
> > $$A\subseteq A\cup B,$$
> >
> > monotonicity decomposition gives:
> >
> > $$P(A\cup B)
> > =
> > P(A)+P((A\cup B)\setminus A).$$
> >
> > Now observe that
> >
> > $$B=(A\cap B)\sqcup((A\cup B)\setminus A).$$
> >
> > Therefore:
> >
> > $$P(B)
> > =
> > P(A\cap B)+P((A\cup B)\setminus A).$$
> >
> > Hence:
> >
> > $$P((A\cup B)\setminus A)
> > =
> > P(B)-P(A\cap B).$$
> >
> > Substituting:
> >
> > $$P(A\cup B)
> > =
> > P(A)+P(B)-P(A\cap B).$$
>
> > [!example]- Inclusion-Exclusion Example
> >
> > Roll a fair die.
> >
> > Let
> >
> > $$A=\{2,4,6\}$$
> >
> > be the event "even number."
> >
> > Let
> >
> > $$B=\{4,5,6\}$$
> >
> > be the event "number greater than $3$."
> >
> > Then:
> >
> > $$P(A)=\frac36=\frac12$$
> >
> > $$P(B)=\frac36=\frac12$$
> >
> > and
> >
> > $$A\cap B=\{4,6\},$$
> >
> > so
> >
> > $$P(A\cap B)=\frac26=\frac13.$$
> >
> > Therefore:
> >
> > $$P(A\cup B)
> > =
> > \frac12+\frac12-\frac13
> > =\frac23.$$
>
> > [!warning]- When Can We Simply Add Probabilities?
> >
> > If $A$ and $B$ are **disjoint**:
> >
> > $$A\cap B=\emptyset,$$
> >
> > so
> >
> > $$P(A\cap B)=0.$$
> >
> > Inclusion-exclusion becomes:
> >
> > $$\boxed{
> > P(A\cup B)=P(A)+P(B).
> > }$$
> >
> > Therefore, simple addition works for disjoint events.
> >
> > For overlapping events, we must subtract the intersection.
>
> > [!important]- Relationship Between the Three Properties
> >
> > These properties all come from the fundamental axioms of probability.
> >
> > **Complement:**
> >
> > $$\boxed{P(A^c)=1-P(A)}$$
> >
> > **Monotonicity:**
> >
> > $$\boxed{A\subseteq B\implies P(A)\leq P(B)}$$
> >
> > **Inclusion-Exclusion:**
> >
> > $$\boxed{
> > P(A\cup B)=P(A)+P(B)-P(A\cap B)
> > }$$
> >
> > They are not additional axioms; they are **consequences of the probability axioms**.
>
> > [!tip]- Mental Model
> >
> > **Complement:**
> >
> > $$\boxed{\text{Everything}=\text{A}+\text{not A}}$$
> >
> > **Monotonicity:**
> >
> > $$\boxed{\text{Bigger event}\Rightarrow\text{at least as much probability}}$$
> >
> > **Inclusion-Exclusion:**
> >
> > $$\boxed{
> > \text{A or B}
> > =
> > \text{A}+\text{B}-\text{overlap}
> > }$$
> >
> > These three rules will repeatedly appear in calculations involving **events, conditional probability, independence, and random variables**.

> [!important]- Frequentist Approach to Probability
>
> > [!abstract]- Context: What Does Probability Mean?
> >
> > There are different philosophical interpretations of probability.
> >
> > The **frequentist approach** interprets probability in terms of the **long-run relative frequency** with which an outcome or event occurs when the same random experiment is repeated many times under identical conditions.
> >
> > The central idea is:
> >
> > $$\boxed{
> > \text{Probability}
> > \approx
> > \text{long-run relative frequency}
> > }$$
> >
> > For example, if a fair coin is tossed repeatedly, we expect the fraction of tosses that result in Heads to approach $\frac12$ as the number of tosses becomes very large.
>
> > [!important]- Relative Frequency
> >
> > Suppose an experiment is performed $N$ times.
> >
> > Let $N(\omega)$ denote the number of times outcome $\omega$ occurs.
> >
> > The **relative frequency** of $\omega$ is
> >
> > $$\boxed{
> > \frac{N(\omega)}{N}.
> > }$$
> >
> > Here:
> >
> > $$N=\text{total number of trials}$$
> >
> > $$N(\omega)=\text{number of trials producing }\omega.$$
> >
> > Since $N(\omega)\leq N$,
> >
> > $$0\leq\frac{N(\omega)}N\leq1.$$
>
> > [!abstract]- Frequentist Interpretation
> >
> > Under the frequentist interpretation, as the number of repetitions becomes very large, the relative frequency is expected to stabilize around a particular value.
> >
> > This motivates the notation
> >
> > $$\boxed{
> > p(\omega)
> > :=
> > \lim_{N\to\infty}\frac{N(\omega)}N
> > }$$
> >
> > whenever this limit exists in the relevant probabilistic sense.
> >
> > Thus:
> >
> > $$\boxed{
> > \text{Probability of an outcome}
> > =
> > \text{its long-run relative frequency}
> > }$$
>
> > [!warning]- Important Mathematical Nuance
> >
> > The formula
> >
> > $$p(\omega)=\lim_{N\to\infty}\frac{N(\omega)}N$$
> >
> > is best understood as the **intuition behind the frequentist interpretation**, rather than as the foundational definition used in modern probability theory.
> >
> > In rigorous probability theory, probability is usually introduced through the axioms of a probability measure:
> >
> > $$P:\mathcal F\to[0,1].$$
> >
> > The connection between probabilities and observed long-run frequencies is established by results such as the **Law of Large Numbers**.
>
> > [!example]- Fair Coin Toss
> >
> > Suppose a fair coin is tossed repeatedly.
> >
> > Let
> >
> > $$N(H)=\text{number of Heads in }N\text{ tosses}.$$
> >
> > The observed relative frequency of Heads is
> >
> > $$\frac{N(H)}N.$$
> >
> > As the number of tosses becomes very large, we expect
> >
> > $$\frac{N(H)}N\to\frac12.$$
> >
> > Therefore, the frequentist interpretation is consistent with
> >
> > $$\boxed{p(H)=\frac12}.$$
> >
> > Similarly:
> >
> > $$\boxed{p(T)=\frac12}.$$
>
> > [!example]- Fair Die Roll
> >
> > Consider
> >
> > $$\Omega=\{1,2,3,4,5,6\}.$$
> >
> > For a fair die, each face should occur approximately $\frac16$ of the time in a large number of trials.
> >
> > Thus:
> >
> > $$\frac{N(i)}N\to\frac16,
> > \qquad i=1,\ldots,6.$$
> >
> > This corresponds to
> >
> > $$\boxed{
> > p(i)=\frac16
> > \qquad\text{for all }i\in\Omega.
> > }$$
>
> > [!example]- First Heads in Repeated Coin Tosses
> >
> > Consider repeatedly tossing a fair coin until the first Head appears.
> >
> > Define the random variable $N$ as:
> >
> > $$N=\text{number of tosses required to obtain the first Head}.$$
> >
> > The possible values are
> >
> > $$N\in\{1,2,3,\ldots\}.$$
> >
> > For the first Head to occur on toss $n$, the sequence must be
> >
> > $$\underbrace{TT\cdots T}_{n-1\text{ tails}}H.$$
> >
> > Therefore:
> >
> > $$P(N=n)
> > =
> > \left(\frac12\right)^{n-1}\left(\frac12\right)
> > =\frac1{2^n}.$$
> >
> > Hence:
> >
> > $$\boxed{
> > P(N=n)=\frac1{2^n},
> > \qquad n=1,2,3,\ldots
> > }$$
> >
> > In a frequentist interpretation, if we repeat the **entire experiment** many times, the fraction of experiments in which the first Head occurs on toss $n$ approaches $\frac1{2^n}$.
>
> > [!abstract]- Example of Long-Run Frequency
> >
> > Suppose we repeat the first-head experiment $100{,}000$ times.
> >
> > For $n=3$, the probability is
> >
> > $$P(N=3)=\frac18.$$
> >
> > Therefore, we expect approximately
> >
> > $$100{,}000\times\frac18=12{,}500$$
> >
> > experiments to have their first Head on the third toss.
> >
> > The observed proportion should become closer to $\frac18$ as the number of repetitions becomes very large.
>
> > [!abstract]- What Is the Core Idea?
> >
> > The frequentist approach connects three ideas:
> >
> > $$\boxed{
> > \text{Repeated experiment}
> > \rightarrow
> > \text{observed frequency}
> > \rightarrow
> > \text{probability}
> > }$$
> >
> > For an event $A$, if it occurs $N(A)$ times in $N$ repetitions, then its relative frequency is
> >
> > $$\frac{N(A)}N.$$
> >
> > The frequentist interpretation associates the probability $P(A)$ with the long-run behavior of this relative frequency:
> >
> > $$\boxed{
> > \frac{N(A)}N\longrightarrow P(A).
> > }$$
>
> > [!important]- Connection to the Law of Large Numbers
> >
> > The rigorous mathematical result behind the long-run frequency intuition is the **Law of Large Numbers**.
> >
> > Roughly, if we repeatedly perform the same random experiment under suitable assumptions, then the empirical frequency of an event approaches its probability:
> >
> > $$\boxed{
> > \frac{N(A)}N\to P(A)
> > }$$
> >
> > as $N\to\infty$.
> >
> > Thus, the Law of Large Numbers explains why probability can be interpreted through long-run frequencies.
>
> > [!warning]- Probability Is Not the Same as Observed Frequency
> >
> > For a finite number of trials,
> >
> > $$\frac{N(A)}N$$
> >
> > does **not** have to equal $P(A)$.
> >
> > For example, in $10$ coin tosses, we might observe:
> >
> > $$N(H)=7.$$
> >
> > Then:
> >
> > $$\frac{N(H)}{10}=0.7,$$
> >
> > even though
> >
> > $$P(H)=0.5.$$
> >
> > Random fluctuations are expected.
> >
> > The important statement concerns the behavior as the number of repetitions becomes very large.
>
> > [!important]- Big Picture
> >
> > The frequentist viewpoint says:
> >
> > $$\boxed{
> > P(A)\text{ describes the long-run frequency with which }A\text{ occurs.}
> > }$$
> >
> > This gives an intuitive connection between the abstract probability measure $P$ and actual repeated experiments.
> >
> > **However, in modern probability theory:**
> >
> > $$\boxed{
> > \text{Probability is mathematically defined by axioms;}
> > }$$
> >
> > while
> >
> > $$\boxed{
> > \text{long-run frequency is a way to interpret and estimate it.}
> > }$$
>
> > [!tip]- Mental Model
> >
> > **One experiment:**
> >
> > $$\text{Outcome is uncertain}$$
> >
> > **Many repetitions:**
> >
> > $$\text{Relative frequency fluctuates}$$
> >
> > **Very many repetitions:**
> >
> > $$\text{Relative frequency stabilizes around }P(A)$$
> >
> > So:
> >
> > $$\boxed{
> > \text{Probability}
> > \xleftarrow{\text{long-run interpretation}}
> > \text{Relative frequency}
> > }$$

> [!important]- De Morgan's Laws
>
> > [!abstract]- Context
> >
> > **De Morgan's Laws** describe how the complement operation interacts with **union** and **intersection**.
> >
> > They are fundamental set identities used to manipulate and simplify complements of combined events.
> >
> > The key idea is:
> >
> > $$\boxed{\text{Complement changes }\cup\text{ into }\cap\text{ and }\cap\text{ into }\cup.}$$
>
> > [!important]- Two-Set Form
> >
> > **Complement of a union:**
> >
> > $$\boxed{
> > (A\cup B)^c=A^c\cap B^c
> > }$$
> >
> > Meaning:
> >
> > > "Neither $A$ nor $B$ occurs."
> >
> > is equivalent to
> >
> > > "$A$ does not occur **and** $B$ does not occur."
> >
> > **Complement of an intersection:**
> >
> > $$\boxed{
> > (A\cap B)^c=A^c\cup B^c
> > }$$
> >
> > Meaning:
> >
> > > "It is not true that both $A$ and $B$ occur."
> >
> > is equivalent to
> >
> > > "At least one of $A$ or $B$ does not occur."
>
> > [!example]- Example
> >
> > Suppose:
> >
> > $A=$ "It rains"
> >
> > $B=$ "It is cold"
> >
> > Then
> >
> > $$A\cup B=$$
> > "It rains **or** it is cold."
> >
> > Therefore:
> >
> > $$(A\cup B)^c=A^c\cap B^c.$$
> >
> > This means:
> >
> > "It does not rain **and** it is not cold."
> >
> > Similarly:
> >
> > $$(A\cap B)^c=A^c\cup B^c.$$
> >
> > This means:
> >
> > "It is not the case that both rain and cold occur"
> >
> > or equivalently:
> >
> > "It does not rain **or** it is not cold."
>
> > [!abstract]- General Countable Form
> >
> > For a countable collection of events $A_1,A_2,\ldots$:
> >
> > **Complement of a countable union:**
> >
> > $$\boxed{
> > \left(\bigcup_{i=1}^{\infty}A_i\right)^c
> > =
> > \bigcap_{i=1}^{\infty}A_i^c
> > }$$
> >
> > In words:
> >
> > "None of the events $A_i$ occurs."
> >
> > **Complement of a countable intersection:**
> >
> > $$\boxed{
> > \left(\bigcap_{i=1}^{\infty}A_i\right)^c
> > =
> > \bigcup_{i=1}^{\infty}A_i^c
> > }$$
> >
> > In words:
> >
> > "It is not true that all of the events $A_i$ occur"
> >
> > means
> >
> > "At least one of the events $A_i$ does not occur."
>
> > [!tip]- Easy Way to Remember
> >
> > When taking a complement:
> >
> > $$\boxed{
> > \cup\longleftrightarrow\cap
> > }$$
> >
> > while every individual event is complemented:
> >
> > $$A\to A^c,\qquad B\to B^c.$$
> >
> > So:
> >
> > $$\boxed{
> > (A\cup B)^c=A^c\cap B^c
> > }$$
> >
> > $$\boxed{
> > (A\cap B)^c=A^c\cup B^c
> > }$$
>
> > [!important]- Connection to Probability
> >
> > De Morgan's Laws are particularly useful when calculating probabilities of complements.
> >
> > For example:
> >
> > $$P((A\cup B)^c)
> > =
> > P(A^c\cap B^c).$$
> >
> > Also:
> >
> > $$P((A\cap B)^c)
> > =
> > P(A^c\cup B^c).$$
> >
> > This is often useful when an event is easier to describe through its complement.
>
> > [!abstract]- Big Picture
> >
> > $$\boxed{
> > \text{Complement}
> > \quad+\quad
> > \text{Union/Intersection}
> > \quad\Rightarrow\quad
> > \text{De Morgan's Laws}
> > }$$
> >
> > The essential rule is:
> >
> > $$\boxed{
> > \text{Complement flips AND }\leftrightarrow\text{ OR}
> > }$$
> >
> > In set notation:
> >
> > $$\boxed{
> > \cup\leftrightarrow\cap
> > }$$

---

> [!important]- Inclusion-Exclusion Principle
>
> > [!abstract]- Context: Why Do We Need It?
> >
> > The **Inclusion-Exclusion Principle** is used to calculate the probability of a **union of events**, even when the events are **not disjoint**.
> >
> > The main problem is **overcounting**.
> >
> > If we simply add $P(A)+P(B)$, outcomes belonging to both $A$ and $B$ are counted twice.
> >
> > Therefore, we subtract the overlap.
> >
> > $$\boxed{
> > \text{Union probability}
> > =
> > \text{sum of individual probabilities}
> > -
> > \text{overlap}
> > }$$
>
> > [!important]- Two-Event Case
> >
> > For two arbitrary events $A$ and $B$:
> >
> > $$\boxed{
> > P(A\cup B)
> > =
> > P(A)+P(B)-P(A\cap B)
> > }$$
> >
> > Here:
> >
> > - $P(A)+P(B)$ counts everything in $A$ and everything in $B$.
> > - $A\cap B$ is counted **twice**.
> > - Subtracting $P(A\cap B)$ corrects this double counting.
>
> > [!example]- Why Subtract the Intersection?
> >
> > Think of the sample space as three regions:
> >
> > $$A\setminus B,\qquad A\cap B,\qquad B\setminus A.$$
> >
> > Then:
> >
> > $$P(A)=P(A\setminus B)+P(A\cap B)$$
> >
> > $$P(B)=P(B\setminus A)+P(A\cap B).$$
> >
> > Adding them gives:
> >
> > $$P(A)+P(B)
> > =
> > P(A\setminus B)+P(B\setminus A)+2P(A\cap B).$$
> >
> > But $A\cup B$ should contain the intersection only once.
> >
> > Therefore:
> >
> > $$P(A\cup B)
> > =
> > P(A)+P(B)-P(A\cap B).$$
>
> > [!tip]- Special Case: Disjoint Events
> >
> > If $A$ and $B$ are disjoint:
> >
> > $$A\cap B=\emptyset.$$
> >
> > Therefore:
> >
> > $$P(A\cap B)=0,$$
> >
> > and inclusion-exclusion becomes:
> >
> > $$\boxed{
> > P(A\cup B)=P(A)+P(B).
> > }$$
> >
> > So **addition of probabilities is valid directly only when the events are disjoint**.
>
> > [!important]- Three-Event Case
> >
> > For three arbitrary events $A,B,C$:
> >
> > $$\boxed{
> > \begin{aligned}
> > P(A\cup B\cup C)
> > ={}&
> > P(A)+P(B)+P(C)\\
> > &-P(A\cap B)-P(A\cap C)-P(B\cap C)\\
> > &+P(A\cap B\cap C).
> > \end{aligned}
> > }$$
> >
> > The pattern is:
> >
> > $$\boxed{
> > \text{Add singles}
> > \;-\;
> > \text{subtract pairs}
> > \;+\;
> > \text{add triple intersection}
> > }$$
>
> > [!abstract]- Why Does the Three-Event Formula Alternate?
> >
> > Start by adding:
> >
> > $$P(A)+P(B)+P(C).$$
> >
> > Pairwise overlaps are counted twice, so subtract:
> >
> > $$P(A\cap B)+P(A\cap C)+P(B\cap C).$$
> >
> > However, the region
> >
> > $$A\cap B\cap C$$
> >
> > was initially counted **3 times**.
> >
> > The three pairwise subtractions remove it 3 times, leaving it counted $0$ times.
> >
> > Therefore, we add it back once:
> >
> > $$+P(A\cap B\cap C).$$
> >
> > Final count: exactly **once**.
>
> > [!example]- Numerical Example
> >
> > Suppose:
> >
> > $$P(A)=0.5,\qquad P(B)=0.4,$$
> >
> > and
> >
> > $$P(A\cap B)=0.2.$$
> >
> > Then:
> >
> > $$P(A\cup B)
> > =0.5+0.4-0.2
> > =0.7.$$
> >
> > Without subtracting the intersection, we would incorrectly obtain $0.9$.
>
> > [!important]- General Pattern
> >
> > For $n$ events, inclusion-exclusion follows the alternating pattern:
> >
> > $$\boxed{
> > \text{1-way intersections}
> > -
> > \text{2-way intersections}
> > +
> > \text{3-way intersections}
> > -
> > \cdots
> > }$$
> >
> > In general:
> >
> > $$\boxed{
> > P\left(\bigcup_{i=1}^n A_i\right)
> > =
> > \sum_iP(A_i)
> > -
> > \sum_{i<j}P(A_i\cap A_j)
> > +
> > \sum_{i<j<k}P(A_i\cap A_j\cap A_k)
> > -\cdots
> > +(-1)^{n+1}P(A_1\cap\cdots\cap A_n)
> > }$$
>
> > [!tip]- Easy Way to Remember
> >
> > $$\boxed{
> > +\text{ singles}
> > \rightarrow
> > -\text{ pairs}
> > \rightarrow
> > +\text{ triples}
> > \rightarrow
> > -\text{ quadruples}
> > \rightarrow\cdots
> > }$$
> >
> > The signs **alternate** because each higher-order intersection corrects the overcounting introduced by the previous terms.
>
> > [!important]- Big Picture
> >
> > $$\boxed{
> > \text{Inclusion-Exclusion}
> > =
> > \text{count everything}
> > -
> > \text{correct overcounting}
> > }$$
> >
> > For two events:
> >
> > $$P(A\cup B)=P(A)+P(B)-P(A\cap B).$$
> >
> > For three events:
> >
> > $$P(A\cup B\cup C)
> > =
> > \text{singles}
> > -
> > \text{pairs}
> > +
> > \text{triple}.$$
> >
> > **Core idea:** intersections measure the overlap that must be corrected when probabilities of overlapping events are added.

> [!important]- Non-Measurable Sets: Why $\mathcal F\neq2^\Omega$
>
> > [!abstract]- Context: Why Can't Every Subset Be an Event?
> >
> > In a discrete probability space, we often take
> >
> > $$\mathcal F=2^\Omega,$$
> >
> > meaning **every subset of $\Omega$ is measurable**.
> >
> > For continuous spaces such as
> >
> > $$\Omega=[0,1],$$
> >
> > this is no longer possible if we want probability to behave like ordinary length.
> >
> > The power set
> >
> > $$2^{[0,1]}$$
> >
> > contains extremely pathological subsets for which a consistent notion of length/probability cannot be defined while preserving the usual desirable properties.
> >
> > Therefore, we restrict the collection of valid events:
> >
> > $$\boxed{
> > \mathcal F\subsetneq2^\Omega
> > }$$
> >
> > and only assign probabilities to sets in $\mathcal F$.
>
> > [!important]- The Three Desirable Properties
> >
> > Suppose we want a probability measure on $[0,1]$ that behaves like ordinary length.
> >
> > We would naturally want:
> >
> > **Length matching**
> >
> > Intervals should have their usual lengths:
> >
> > $$P([a,b])=b-a.$$
> >
> > For example:
> >
> > $$P([0,0.5])=0.5.$$
> >
> > **Translation invariance**
> >
> > Moving a set without changing its shape should not change its measure:
> >
> > $$P(A+x)=P(A).$$
> >
> > **Countable additivity**
> >
> > For pairwise disjoint measurable sets:
> >
> > $$P\left(\bigcup_{i=1}^{\infty}A_i\right)
> > =
> > \sum_{i=1}^{\infty}P(A_i).$$
> >
> > These properties work perfectly for ordinary measurable sets.
> >
> > The problem appears when we insist that they apply to **every subset** of $[0,1]$.
>
> > [!abstract]- Vitali Set: The Problematic Set
> >
> > A **Vitali set** $V\subseteq[0,1]$ is constructed by selecting exactly one representative from each equivalence class under
> >
> > $$x\sim y
> > \iff x-y\in\mathbb Q.$$
> >
> > In other words, two numbers are considered equivalent if their difference is rational.
> >
> > Using the Axiom of Choice, we can select one representative from every equivalence class.
> >
> > The resulting set $V$ is a **non-measurable set**.
>
> > [!abstract]- Why Translated Copies Cause a Contradiction
> >
> > Consider rational translations of $V$:
> >
> > $$V+q=\{v+q:v\in V\},
> > \qquad q\in\mathbb Q.$$
> >
> > The important properties are:
> >
> > - Appropriate rational translates are pairwise disjoint.
> > - Countably many rational translates cover $[0,1]$.
> > - All translates have the same measure if translation invariance holds.
> >
> > In fact, the relevant translated copies can be considered inside a bounded interval such as $[-1,2]$.
> >
> > This creates the contradiction.
>
> > [!warning]- Case 1: Suppose $P(V)=0$
> >
> > Every rational translate would also have measure $0$:
> >
> > $$P(V+q)=0.$$
> >
> > Since there are countably many such translates, countable additivity would give
> >
> > $$P\left(\bigcup_{q\in\mathbb Q}(V+q)\right)
> > =
> > \sum_{q\in\mathbb Q}0
> > =0.
> > $$
> >
> > But these translates cover $[0,1]$, so this would imply
> >
> > $$P([0,1])=0,$$
> >
> > contradicting
> >
> > $$P([0,1])=1.$$
>
> > [!warning]- Case 2: Suppose $P(V)>0$
> >
> > Translation invariance gives
> >
> > $$P(V+q)=P(V)>0.$$
> >
> > There are countably infinitely many pairwise disjoint translates.
> >
> > Therefore:
> >
> > $$P\left(\bigcup_{q\in\mathbb Q}(V+q)\right)
> > =
> > \sum_{q\in\mathbb Q}P(V)
> > =\infty.
> > $$
> >
> > But all these translates lie inside a bounded interval such as $[-1,2]$, whose finite length is $3$.
> >
> > Hence its probability cannot be infinite.
> >
> > Contradiction again.
>
> > [!important]- Conclusion
> >
> > Therefore, $V$ cannot be assigned a probability while simultaneously preserving the desired properties of length, translation invariance, and countable additivity.
> >
> > Hence:
> >
> > $$\boxed{
> > \text{Not every subset of }[0,1]\text{ can be measurable.}
> > }$$
> >
> > In particular:
> >
> > $$\boxed{
> > \mathcal F\neq2^{[0,1]}.
> > }$$
>
> > [!abstract]- Resolution: Measure Theory
> >
> > Instead of trying to assign probabilities to **all** subsets, measure theory restricts attention to a well-behaved collection of sets called a **$\sigma$-field**.
> >
> > For $[0,1]$, an important choice is the **Borel $\sigma$-field**:
> >
> > $$\mathcal B([0,1]).$$
> >
> > It contains the usual sets we need, such as:
> >
> > - intervals
> > - open and closed sets
> > - points
> > - countable unions and intersections of Borel sets
> > - complements of Borel sets
> >
> > but it does **not** contain every subset of $[0,1]$.
> >
> > Thus:
> >
> > $$\boxed{
> > \mathcal B([0,1])\subsetneq2^{[0,1]}.
> > }$$
>
> > [!tip]- Why This Is Not a Problem
> >
> > We do not need every mathematical subset to be an event.
> >
> > We only need a collection of sets that is:
> >
> > $$\boxed{\text{rich enough for probability theory and closed under the required operations.}}$$
> >
> > That is exactly what a $\sigma$-field provides.
> >
> > So the probability-space structure becomes:
> >
> > $$\boxed{
> > (\Omega,\mathcal F,P)
> > }$$
> >
> > where:
> >
> > $$\Omega=\text{all possible outcomes}$$
> >
> > $$\mathcal F=\text{measurable events}$$
> >
> > $$P=\text{probability measure on those events}.$$
>
> > [!important]- Big Picture
> >
> > In a finite/countable discrete space, we can often use
> >
> > $$\boxed{\mathcal F=2^\Omega.}$$
> >
> > In continuous spaces, this is generally too large.
> >
> > Therefore:
> >
> > $$\boxed{
> > \text{All subsets}
> > \;\supsetneq\;
> > \text{measurable subsets}
> > \;\xrightarrow{\;P\;}\;
> > [0,1].
> > }$$
> >
> > The existence of non-measurable sets is one of the reasons **measure theory needs the concept of a $\sigma$-field**.

> [!important]- The Birthday Problem
>
> > [!abstract]- Problem Statement
> >
> > Suppose $n$ people are chosen randomly.
> >
> > Assume:
> >
> > - There are $d=365$ possible birthdays.
> > - Each day is equally likely.
> > - Birthdays of different people are independent.
> >
> > Let
> >
> > $$E=\{\text{at least two people have the same birthday}\}.$$
> >
> > We want:
> >
> > $$\boxed{P(E)}.$$
>
> > [!tip]- Key Strategy: Use the Complement
> >
> > Directly counting all assignments where at least two birthdays match is complicated.
> >
> > Instead, consider the complement:
> >
> > $$E^c=\{\text{all }n\text{ people have distinct birthdays}\}.$$
> >
> > Since
> >
> > $$E^c=\text{``no collision''},$$
> >
> > we have
> >
> > $$\boxed{
> > P(E)=1-P(E^c).
> > }$$
> >
> > This is a common probability strategy:
> >
> > $$\boxed{
> > P(\text{at least one})=
> > 1-P(\text{none}).
> > }$$
>
> > [!important]- Sample Space
> >
> > Each of the $n$ people can have one of $d=365$ birthdays.
> >
> > Therefore, the total number of possible birthday assignments is
> >
> > $$\boxed{
> > |\Omega|=d^n=365^n.
> > }$$
> >
> > Each assignment is equally likely under the assumptions.
>
> > [!abstract]- Counting the Complement
> >
> > We need all $n$ birthdays to be distinct.
> >
> > **Person 1:**
> >
> > There are $d$ choices.
> >
> > **Person 2:**
> >
> > One day is already occupied, so there are $d-1$ choices.
> >
> > **Person 3:**
> >
> > Two days are occupied, so there are $d-2$ choices.
> >
> > Continuing:
> >
> > $$d(d-1)(d-2)\cdots(d-n+1).$$
> >
> > Thus:
> >
> > $$\boxed{
> > |E^c|
> > =
> > d(d-1)\cdots(d-n+1)
> > =
> > \frac{d!}{(d-n)!}
> > }$$
> >
> > This formula is valid for $n\le d$.
>
> > [!important]- Probability of No Shared Birthday
> >
> > Therefore:
> >
> > $$P(E^c)
> > =
> > \frac{|E^c|}{|\Omega|}.$$
> >
> > Hence:
> >
> > $$\boxed{
> > P(E^c)
> > =
> > \frac{d(d-1)\cdots(d-n+1)}{d^n}
> > }$$
> >
> > Dividing each factor by $d$:
> >
> > $$\boxed{
> > P(E^c)
> > =
> > \prod_{k=0}^{n-1}
> > \left(1-\frac{k}{d}\right)
> > }$$
> >
> > For $d=365$:
> >
> > $$\boxed{
> > P(E^c)
> > =
> > \prod_{k=0}^{n-1}
> > \left(1-\frac{k}{365}\right).
> > }$$
>
> > [!important]- Probability of at Least One Shared Birthday
> >
> > Taking the complement:
> >
> > $$\boxed{
> > P(E)
> > =
> > 1-
> > \prod_{k=0}^{n-1}
> > \left(1-\frac{k}{365}\right)
> > }$$
> >
> > Equivalently:
> >
> > $$\boxed{
> > P(E)
> > =
> > 1-
> > \frac{365\cdot364\cdots(365-n+1)}
> > {365^n}.
> > }$$
>
> > [!example]- Why 23 People Is Surprisingly Enough
> >
> > For $n=23$:
> >
> > $$P(E)
> > =
> > 1-
> > \prod_{k=0}^{22}
> > \left(1-\frac{k}{365}\right)
> > \approx0.5073.
> > $$
> >
> > Therefore:
> >
> > $$\boxed{
> > P(E)\approx50.73\%.
> > }$$
> >
> > So with only **23 people**, the probability that at least two share a birthday is already greater than $50\%$.
> >
> > The surprising part is that we are not comparing one particular person with everyone else. There are many possible **pairs** of people that could produce a collision.
>
> > [!example]- For 57 People
> >
> > For $n=57$:
> >
> > $$P(E)\approx0.9901.$$
> >
> > Thus:
> >
> > $$\boxed{
> > P(E)\approx99.0\%.
> > }$$
> >
> > So with 57 people, a shared birthday is extremely likely under the model assumptions.
>
> > [!abstract]- Balls-in-Bins Interpretation
> >
> > The Birthday Problem is an instance of the **balls-in-bins model**.
> >
> > Correspondence:
> >
> > $$\boxed{
> > \begin{array}{c|c}
> > \text{Birthday Problem} & \text{Balls-in-Bins}\\
> > \hline
> > \text{Person} & \text{Ball}\\
> > \text{Birthday} & \text{Bin}\\
> > 365\text{ days} & 365\text{ bins}\\
> > \text{Same birthday} & \text{Same bin}\\
> > \text{Shared birthday} & \text{Collision}
> > \end{array}
> > }$$
> >
> > Each ball is placed independently and uniformly into one of the $d$ bins.
> >
> > The event
> >
> > $$E=\{\text{at least two people share a birthday}\}$$
> >
> > becomes
> >
> > $$E=\{\text{at least one bin contains }\ge2\text{ balls}\}.$$
>
> > [!important]- Collision Threshold
> >
> > The important question is not:
> >
> > > "How many people are needed to fill 365 days?"
> >
> > Instead, it is:
> >
> > > "How many random assignments are needed before a collision becomes likely?"
> >
> > Because **every pair of people** can potentially collide, the probability of a collision rises much faster than intuition based only on $n/365$ might suggest.
> >
> > The approximate threshold for a $50\%$ collision probability is
> >
> > $$\boxed{
> > n\approx\sqrt{2d\ln2}.
> > }$$
> >
> > For $d=365$:
> >
> > $$n\approx\sqrt{2(365)\ln2}\approx22.5,$$
> >
> > which explains why the exact threshold occurs at about **23 people**.
>
> > [!tip]- General Balls-in-Bins Formula
> >
> > For $n$ balls and $d$ equally likely bins:
> >
> > $$\boxed{
> > P(\text{no collision})
> > =
> > \prod_{k=0}^{n-1}
> > \left(1-\frac{k}{d}\right)
> > }$$
> >
> > Therefore:
> >
> > $$\boxed{
> > P(\text{at least one collision})
> > =
> > 1-
> > \prod_{k=0}^{n-1}
> > \left(1-\frac{k}{d}\right).
> > }$$
> >
> > The Birthday Problem is simply the special case
> >
> > $$d=365.$$
>
> > [!important]- Big Picture
> >
> > $$\boxed{
> > \text{Birthday Problem}
> > \longleftrightarrow
> > \text{Balls-in-Bins Collision Problem}
> > }$$
> >
> > The main technique is:
> >
> > $$\boxed{
> > \text{At least one collision}
> > \xrightarrow{\text{complement}}
> > \text{no collision}
> > \xrightarrow{\text{count}}
> > \text{product formula}
> > }$$
> >
> > The key formula to remember is:
> >
> > $$\boxed{
> > P(\text{shared birthday})
> > =
> > 1-
> > \prod_{k=0}^{n-1}
> > \left(1-\frac{k}{365}\right).
> > }$$













