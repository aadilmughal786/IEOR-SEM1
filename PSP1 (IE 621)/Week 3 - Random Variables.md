
> [!important]- Why Do We Need Random Variables?
>
> > [!abstract]- The Problem Before Random Variables
> >
> > Suppose we roll **two dice**.
> >
> > The sample space is
> >
> > $$\Omega=\{(1,1),(1,2),\ldots,(6,6)\}.$$
> >
> > Each outcome describes exactly what happened:
> >
> > $$(1,1),\ (3,5),\ (6,2),\ldots$$
> >
> > Now suppose we ask:
> >
> > **"What is the sum of the two dice?"**
> >
> > The answer is not an outcome such as $(1,1)$ or $(3,5)$.
> >
> > Instead, the answer is a **number**:
> >
> > $$2,3,4,\ldots,12.$$
> >
> > Therefore, we need a systematic way to take an outcome $\omega\in\Omega$ and attach a numerical quantity to it.
> >
> > This is exactly what a **random variable** does.
>
> > [!important]- Basic Idea
> >
> > A random variable is a function
> >
> > $$\boxed{X:\Omega\rightarrow\mathbb R}$$
> >
> > It takes an outcome $\omega$ and assigns a numerical value $X(\omega)$.
> >
> > $$\boxed{
> > \text{Outcome }\omega
> > \xrightarrow{\quad X\quad}
> > \text{Number }X(\omega)
> > }$$
> >
> > **Important:** A random variable is fundamentally a **function**.
> >
> > It is not itself a random number.
> >
> > The value $X(\omega)$ is the numerical value produced when the outcome $\omega$ occurs.
>
> > [!example]- Example: Sum of Two Dice
> >
> > Let $X$ represent the **sum of the two dice**.
> >
> > Then $X$ maps every outcome in $\Omega$ to its corresponding sum:
> >
> > $$X(1,1)=2$$
> >
> > $$X(2,5)=7$$
> >
> > $$X(6,6)=12.$$
> >
> > For example:
> >
> > $$\begin{aligned}
> > (1,1)&\xrightarrow{X}2\\
> > (2,5)&\xrightarrow{X}7\\
> > (4,3)&\xrightarrow{X}7\\
> > (6,6)&\xrightarrow{X}12
> > \end{aligned}$$
> >
> > Notice that different outcomes can produce the **same value**:
> >
> > $$X(2,5)=X(4,3)=7.$$
> >
> > Therefore, the random variable does not necessarily uniquely identify the original outcome.
>
> > [!abstract]- What Does the Random Variable Actually Do?
> >
> > Before introducing $X$, we work with the detailed outcomes:
> >
> > $$(1,1),(1,2),(1,3),\ldots,(6,6).$$
> >
> > But perhaps we do not care about the individual dice values.
> >
> > We may only care about their **sum**.
> >
> > The random variable compresses the detailed outcome into the numerical quantity of interest:
> >
> > $$\boxed{
> > (d_1,d_2)\longmapsto d_1+d_2
> > }$$
> >
> > Thus, instead of studying all $36$ outcomes directly, we can study the possible values
> >
> > $$\{2,3,\ldots,12\}.$$
>
> > [!important]- Core Purpose
> >
> > The randomness is in the **outcome $\omega$**, not in the function $X$ itself.
> >
> > **Probability** gives us a framework for describing:
> >
> > $$\boxed{\text{What can happen?}}$$
> >
> > A **random variable** allows us to describe:
> >
> > $$\boxed{\text{What numerical quantity do we want to study about what happened?}}$$
> >
> > Therefore:
> >
> > $$\boxed{
> > \text{Random variable = numerical measurement of a random outcome}
> > }$$
>
> > [!abstract]- The Bridge from Probability to Numerical Analysis
> >
> > Probability starts with an abstract sample space:
> >
> > $$\Omega=\{\text{possible outcomes}\}.$$
> >
> > But mathematics, statistics, and applications usually deal with **numbers**:
> >
> > - sum of dice
> > - number of heads
> > - waiting time
> > - temperature
> > - lifetime of a machine
> > - profit or loss
> > - height of a randomly selected person
> >
> > A random variable provides the bridge:
> >
> > $$\boxed{
> > \text{Abstract outcome}
> > \longrightarrow
> > \text{Numerical quantity}
> > }$$
> >
> > Once we have a numerical quantity $X$, we can ask questions such as:
> >
> > $$P(X\leq x),\qquad P(X=x),\qquad E[X],\qquad \operatorname{Var}(X).$$
> >
> > These are the quantities that allow probability theory to connect with statistics and applications.
>
> > [!tip]- Important Terminology
> >
> > If $\omega\in\Omega$ is the outcome that actually occurs, then:
> >
> > $$X:\Omega\to\mathbb R$$
> >
> > is the random variable, while
> >
> > $$X(\omega)\in\mathbb R$$
> >
> > is the **realized value** of the random variable.
> >
> > For example, if the dice outcome is
> >
> > $$\omega=(2,5),$$
> >
> > then
> >
> > $$X(\omega)=X(2,5)=7.$$
> >
> > So:
> >
> > $$\boxed{
> > X=\text{function},\qquad X(\omega)=\text{number}
> > }$$
>
> > [!important]- One Subtle Point
> >
> > Although we call it a **random variable**, mathematically it is a function:
> >
> > $$X:\Omega\to\mathbb R.$$
> >
> > The function itself is completely specified once we define it.
> >
> > The value becomes uncertain only because the input $\omega$ is uncertain.
> >
> > In other words:
> >
> > $$\boxed{
> > \text{Randomness of }X
> > \text{ comes from randomness of }\omega.
> > }$$
>
> > [!abstract]- What Comes Next?
> >
> > Simply being a function $X:\Omega\to\mathbb R$ is not quite enough in a general probability space.
> >
> > We need $X$ to interact properly with the $\sigma$-field $\mathcal F$ so that statements such as
> >
> > $$\{X\leq x\}$$
> >
> > are valid events whose probabilities can be calculated.
> >
> > This leads to the formal definition:
> >
> > $$\boxed{
> > X\text{ is a random variable if it is }\mathcal F\text{-measurable}.
> > }$$
> >
> > Equivalently, for every $x\in\mathbb R$,
> >
> > $$\boxed{
> > \{\omega\in\Omega:X(\omega)\leq x\}\in\mathcal F.
> > }$$
> >
> > So the intuitive idea is:
> >
> > $$\boxed{
> > \text{Random variable = function that converts outcomes into numbers}
> > }$$
> >
> > while the formal theory additionally requires:
> >
> > $$\boxed{
> > \text{Random variable = measurable function }X:\Omega\to\mathbb R.
> > }$$

> [!important]- Random Variable
>A function $X:\Omega\rightarrow\mathbb{R}$ is called a **random variable** if, for every $x\in\mathbb{R}$,
>
> $$\{X\leq x\}=\{\omega\in\Omega:X(\omega)\leq x\}\in\mathcal{F}.$$
>
> This condition ensures that we can assign a **probability** to events involving the values taken by $X$.
>
>---
>
> > [!abstract]- F-Measurability
> >
> > The condition
> >
> > $$\{X\leq x\}\in\mathcal{F}\qquad\forall x\in\mathbb{R}$$
> >
> > is called **$\mathcal{F}$-measurability**.
> >
> > Therefore,
> >
> > $$\boxed{\text{Random variables are simply $\mathcal{F}$-measurable functions on }\Omega.}$$
>
> > [!example]- Discrete Sample Space
> >
> > If $\Omega$ is discrete and
> >
> > $$\mathcal{F}=2^\Omega,$$
> >
> > then every subset of $\Omega$ belongs to $\mathcal{F}$.
> >
> > Therefore, for any function $X:\Omega\rightarrow\mathbb{R}$,
> >
> > $$\{X\leq x\}\subseteq\Omega\implies\{X\leq x\}\in\mathcal{F}.$$
> >
> > Hence, **measurability is automatic**, and **every function $X$ on $\Omega$ is a random variable**.
>
> > [!tip]- Notation
> >
> > We usually use **capital letters** for random variables:
> >
> > $$X,\;Y,\;Z$$
> >
> > and **lowercase letters** for constants or ordinary variables:
> >
> > $$x,\;y,\;z.$$
>
> > [!warning]- Important
> >
> > A random variable is **not a variable** and is **not a numerical value**.
> >
> > It is a **function** that maps outcomes to numerical values:
> >
> > $$X:\Omega\rightarrow\mathbb{R}$$
> >
> > For a particular outcome $\omega$, the value $X(\omega)$ is a **number**.
> >
> > $$\boxed{X=\text{function},\qquad X(\omega)=\text{numerical value}}$$

> [!important]- CDF
>Let $X$ be a random variable on $(\Omega,\mathcal{F},P)$.
>
> We want to describe the probability that $X$ takes values in a particular region of $\mathbb{R}$.
>
> The **cumulative distribution function (CDF)** of $X$ is the function
>
> $$F_X:\mathbb{R}\rightarrow[0,1]$$
>
> defined by
>
> $$F_X(x)=P(X\leq x)=P(\{\omega\in\Omega:X(\omega)\leq x\}),\qquad x\in\mathbb{R}.$$
>
> > [!abstract]- Why Is This Probability Well-Defined?
> >
> > Since $X$ is $\mathcal{F}$-measurable,
> >
> > $$\{\omega\in\Omega:X(\omega)\leq x\}\in\mathcal{F}.$$
> >
> > Therefore, this set is an **event** to which $P$ can assign a probability.
> >
> > In other words,
> >
> > $$X\text{ is measurable}\quad\Rightarrow\quad\{X\leq x\}\in\mathcal{F}\quad\Rightarrow\quad P(X\leq x)\text{ makes sense}.$$
>
> > [!tip]- Notation
> >
> > If the random variable $X$ is clear from the context, we may simply write
> >
> > $$F_X(x)=F(x).$$
>
> > [!example]- Coin Tossing
> >
> > Consider two coin tosses:
> >
> > $$\Omega=\{HH,HT,TH,TT\}.$$
> >
> > Let $X$ be the random variable that counts the **number of Heads**.
> >
> > Therefore,
> >
> > $$X(HH)=2,\qquad X(HT)=1,\qquad X(TH)=1,\qquad X(TT)=0.$$
> >
> > The possible values of $X$ are
> >
> > $$\{0,1,2\}.$$
> >
> > The CDF is
> >
> > $$F_X(x)=P(X\leq x).$$
> >
> > Hence,
> >
> > $$F_X(x)=
> > \begin{cases}
> > 0, & x<0,\\
> > \frac14, & 0\leq x<1,\\
> > \frac34, & 1\leq x<2,\\
> > 1, & x\geq2.
> > \end{cases}$$
>
> > [!abstract]- How to Read the CDF
> >
> > The CDF tells us the **accumulated probability up to $x$**:
> >
> > $$F_X(x)=P(X\leq x).$$
> >
> > For example,
> >
> > $$F_X(1)=P(X\leq1)=\frac34.$$
> >
> > This means there is a $\frac34$ probability that the number of Heads is **at most 1**.

> [!important]- Distribution, Law, and Push-Forward Probability
>
> **The main idea**
>
> Let $(\Omega,\mathcal{F},P)$ be a probability space and let
>
> $$X:\Omega\rightarrow\mathbb{R}$$
>
> be a random variable.
>
> Instead of studying probabilities on the original sample space $\Omega$, we can **transfer the probability to $\mathbb{R}$ through $X$**.
>
> > [!abstract]- Push-Forward Probability
> >
> > Recall the Borel $\sigma$-field $\mathcal{B}(\mathbb{R})$ on $\mathbb{R}$.
> >
> > The random variable $X$ induces a probability measure $P_X$ on $(\mathbb{R},\mathcal{B}(\mathbb{R}))$:
> >
> > $$P_X(B)=P(\{\omega\in\Omega:X(\omega)\in B\}),\qquad B\in\mathcal{B}(\mathbb{R}).$$
> >
> > This is called the **push-forward of $P$ under $X$**.
> >
> > It is also called the **distribution** or **law** of the random variable $X$.
>
> > [!warning]- Why Does This Make Sense?
> >
> > To calculate
> >
> > $$P_X(B)=P(\{\omega\in\Omega:X(\omega)\in B\}),$$
> >
> > the set
> >
> > $$\{\omega\in\Omega:X(\omega)\in B\}$$
> >
> > must belong to $\mathcal{F}$.
> >
> > The $\mathcal{F}$-measurability of $X$ guarantees that
> >
> > $$\{X\in B\}\in\mathcal{F}\qquad\forall B\in\mathcal{B}(\mathbb{R}).$$
> >
> > Therefore, its probability is well-defined.
> >
> > The proof of this fact is beyond the scope of this course.
>
> > [!tip]- What We Usually Use
> >
> > Although $P_X$ contains the complete distributional information about $X$, we will mostly work with the **CDF**:
> >
> > $$F_X(x)=P(X\leq x).$$
>
> > [!abstract]- A New Probability Space
> >
> > Once we have $P_X$, we can construct a new probability space:
> >
> > $$(\mathbb{R},\mathcal{B}(\mathbb{R}),P_X).$$
> >
> > This probability space describes the behavior of $X$ directly in terms of its numerical values.
> >
> > We can therefore move from
> >
> > $$(\Omega,\mathcal{F},P)$$
> >
> > to
> >
> > $$(\mathbb{R},\mathcal{B}(\mathbb{R}),P_X).$$
>
> > [!example]- Canonical Probability Space
> >
> > On $(\mathbb{R},\mathcal{B}(\mathbb{R}),P_X)$, consider the **identity random variable**
> >
> > $$I(x)=x.$$
> >
> > The law of $I$ under $P_X$ is exactly $P_X$.
> >
> > Therefore,
> >
> > $$(\mathbb{R},\mathcal{B}(\mathbb{R}),P_X)$$
> >
> > is called the **canonical probability space of $X$**.
>
> > [!important]- Why Is This Useful?
> >
> > Once we have $(\mathbb{R},\mathcal{B}(\mathbb{R}),P_X)$, we can **forget about the original experiment** and the underlying probability space $(\Omega,\mathcal{F},P)$.
> >
> > We can study $X$ entirely through its distribution $P_X$.
> >
> > $$\boxed{
> > (\Omega,\mathcal{F},P)
> > \xrightarrow{\;X\;}
> > (\mathbb{R},\mathcal{B}(\mathbb{R}),P_X)
> > }$$
> >
> > The new probability space contains all the information needed to study the **distributional behavior of $X$**.
>
> > [!note]- Connection to the CDF
> >
> > The CDF is simply one way of describing $P_X$:
> >
> > $$F_X(x)=P(X\leq x)=P_X((-\infty,x]).$$
> >
> > So,
> >
> > $$\boxed{\text{Distribution }P_X\quad\longrightarrow\quad\text{CDF }F_X}$$
> >
> > The distribution $P_X$ is the more general object, while the CDF $F_X$ is a convenient way to describe it.

---

> [!important]- Properties of the CDF
>
> Let $F$ be the CDF of a random variable $X$:
>
> $$F(x)=P(X\leq x).$$
>
> The CDF has three fundamental properties:
>
> > [!abstract]- Limits at $\pm\infty$
> >
> > $$\lim_{x\to-\infty}F(x)=0$$
> >
> > $$\lim_{x\to\infty}F(x)=1$$
> >
> > Intuitively, as $x$ moves towards $-\infty$, the event $\{X\leq x\}$ becomes impossible, while as $x$ moves towards $\infty$, it eventually contains essentially all possible values of $X$.
> >
> > **Proof for $x\to-\infty$:**
> >
> > Define
> >
> > $$A_n=\{X\leq-n\}.$$
> >
> > Then
> >
> > $$A_1\supseteq A_2\supseteq A_3\supseteq\cdots$$
> >
> > and
> >
> > $$\bigcap_{n\geq1}A_n=\varnothing.$$
> >
> > By continuity of probability,
> >
> > $$\lim_{n\to\infty}P(A_n)=P(\varnothing)=0.$$
> >
> > Since
> >
> > $$P(A_n)=P(X\leq-n)=F(-n),$$
> >
> > we get
> >
> > $$F(-n)\rightarrow0.$$
> >
> > Therefore,
> >
> > $$\boxed{\lim_{x\to-\infty}F(x)=0.}$$
> >
> > Similarly,
> >
> > $$\boxed{\lim_{x\to\infty}F(x)=1.}$$
> >
> > Note that $F(-\infty)$ and $F(\infty)$ are **not actually values of the function**, since $F$ is defined on $\mathbb{R}$. They are sometimes used as shorthand for the corresponding limits.
>
> > [!abstract]- Nondecreasing
> >
> > If $x<y$, then
> >
> > $$\{X\leq x\}\subseteq\{X\leq y\}.$$
> >
> > Therefore,
> >
> > $$F(x)=P(X\leq x)\leq P(X\leq y)=F(y).$$
> >
> > Hence,
> >
> > $$\boxed{x<y\implies F(x)\leq F(y).}$$
> >
> > So a CDF can **never decrease** as $x$ increases.
>
> > [!abstract]- Right Continuity
> >
> > For every $x\in\mathbb{R}$,
> >
> > $$\boxed{\lim_{h\downarrow0}F(x+h)=F(x).}$$
> >
> > To see why, consider the sequence of events
> >
> > $$A_n=\left\{X\leq x+\frac1n\right\}.$$
> >
> > These events decrease:
> >
> > $$A_1\supseteq A_2\supseteq A_3\supseteq\cdots$$
> >
> > and
> >
> > $$\bigcap_{n\geq1}A_n=\{X\leq x\}.$$
> >
> > Therefore, by continuity of probability,
> >
> > $$\lim_{n\to\infty}P(A_n)=P\left(\bigcap_{n\geq1}A_n\right).$$
> >
> > Since
> >
> > $$P(A_n)=F\left(x+\frac1n\right)$$
> >
> > and
> >
> > $$P\left(\bigcap_{n\geq1}A_n\right)=P(X\leq x)=F(x),$$
> >
> > we obtain
> >
> > $$\lim_{n\to\infty}F\left(x+\frac1n\right)=F(x).$$
> >
> > Hence $F$ is **right continuous**.
>
> > [!warning]- CDF Is Not Generally Left Continuous
> >
> > A CDF is **not necessarily left continuous**.
> >
> > In general,
> >
> > $$\lim_{h\uparrow0}F(x+h)\neq F(x).$$
> >
> > For a discrete random variable, the CDF has jumps. At a jump point $x$,
> >
> > $$F(x)-\lim_{t\uparrow x}F(t)=P(X=x).$$
> >
> > So the value at $x$ includes the probability mass at $x$ itself.
>
> > [!tip]- Three Properties to Remember
> >
> > $$\boxed{\lim_{x\to-\infty}F(x)=0}$$
> >
> > $$\boxed{\lim_{x\to\infty}F(x)=1}$$
> >
> > $$\boxed{F\text{ is nondecreasing}}$$
> >
> > $$\boxed{F\text{ is right continuous}}$$
> >
> > These properties are fundamental characteristics of every CDF.

> [!important]- Some Important Random Variables
>
> > [!example]- Constant Random Variable
> >
> > Let $c\in\mathbb{R}$.
> >
> > Define $X:\Omega\rightarrow\mathbb{R}$ by
> >
> > $$X(\omega)=c,\qquad\forall\omega\in\Omega.$$
> >
> > Thus, $X$ always takes the same value $c$.
> >
> > Its CDF is
> >
> > $$F(x)=
> > \begin{cases}
> > 0, & x<c,\\
> > 1, & x\geq c.
> > \end{cases}$$
> >
> > In other words, the entire probability mass is concentrated at $c$.
>
> > [!example]- Indicator Random Variable
> >
> > Let $A\in\mathcal{F}$ be an event.
> >
> > Define the **indicator random variable** $\mathbf{1}_A:\Omega\rightarrow\mathbb{R}$ by
> >
> > $$\mathbf{1}_A(\omega)=
> > \begin{cases}
> > 1, & \omega\in A,\\
> > 0, & \omega\notin A.
> > \end{cases}$$
> >
> > Thus, the indicator converts an event into a numerical value:
> >
> > $$\boxed{\mathbf{1}_A=
> > \begin{cases}
> > 1,&A\text{ occurs},\\
> > 0,&A\text{ does not occur}.
> > \end{cases}}$$
> >
> > Let
> >
> > $$p=P(A).$$
> >
> > Since $\mathbf{1}_A$ can only take the values $0$ and $1$,
> >
> > $$P(\mathbf{1}_A=1)=p$$
> >
> > and
> >
> > $$P(\mathbf{1}_A=0)=1-p.$$
> >
> > Therefore, its CDF is
> >
> > $$F(x)=
> > \begin{cases}
> > 0, & x<0,\\
> > 1-p, & 0\leq x<1,\\
> > 1, & x\geq1.
> > \end{cases}$$
> >
> > > [!abstract]- Bernoulli Distribution
> > >
> > > The **push-forward distribution** of $\mathbf{1}_A$ is called the **Bernoulli distribution with parameter $p$**, denoted by
> > >
> > > $$\operatorname{Ber}(p).$$
> > >
> > > It has probability mass function
> > >
> > > $$P(X=x)=
> > > \begin{cases}
> > > 1-p, & x=0,\\
> > > p, & x=1.
> > > \end{cases}$$
> >
> >> [!tip]- Key Connection
> >>
> > >An indicator random variable is essentially a way to turn a **yes/no event** into a **0/1 numerical quantity**:
> >>
> > >$$A\text{ occurs}\longrightarrow1$$
> >>
> > >$$A\text{ does not occur}\longrightarrow0$$
> >>
> > >This makes indicators extremely useful for expressing probabilities and expectations mathematically.

> [!important]- Discrete and Continuous Random Variables
>
> Recall that a random variable $X$ defined on $(\Omega,\mathcal{F},P)$ induces a probability $P_X$ on $(\mathbb{R},\mathcal{B}(\mathbb{R}))$.
>
> Therefore, to study the properties of $X$, we can focus on
>
> $$(\mathbb{R},\mathcal{B}(\mathbb{R}),P_X).$$
>
> > [!example]- Discrete Random Variable
> >
> > Often, the set of possible values of $X$ is a **discrete subset** of $\mathbb{R}$.
> >
> > A random variable $X$ is called **discrete** if it takes values only in a discrete subset
> >
> > $$\{x_1,x_2,\ldots\}\subseteq\mathbb{R}.$$
> >
> > For a discrete random variable, we can directly talk about the probability that $X$ takes a particular value:
> >
> > $$P(X=x)=P(\{\omega\in\Omega:X(\omega)=x\}).$$
> >
> > The function
> >
> > $$f(x)=P(X=x)$$
> >
> > is called the **probability mass function (pmf)** of $X$.
>
> > [!example]- Continuous Random Variable
> >
> > A random variable $X$ is called **continuous** if its CDF can be written as
> >
> > $$F(x)=\int_{-\infty}^{x}f(y)\,dy,\qquad x\in\mathbb{R},$$
> >
> > for some integrable function $f:\mathbb{R}\rightarrow[0,1]$.
> >
> > This function $f$ is called the **probability density function (pdf)** of $X$.
> >
> > In particular, if $X$ is continuous, then its CDF $F_X$ is continuous. In fact, it is **absolutely continuous**.
>
> > [!example]- Example: Uniform Distribution
> >
> > Consider the **stick-breaking experiment**:
> >
> > $$\Omega=[0,1],\qquad\mathcal{F}=\mathcal{B}([0,1]),\qquad P=\lambda,$$
> >
> > where $\lambda$ is the length function (Lebesgue measure).
> >
> > Let $X$ represent the **point at which the stick breaks**.
> >
> > Since the outcome itself is the breaking point,
> >
> > $$X(\omega)=\omega,\qquad\omega\in[0,1].$$
> >
> > Its CDF is
> >
> > $$F_X(x)=
> > \begin{cases}
> > 0, & x<0,\\
> > x, & 0\leq x<1,\\
> > 1, & x\geq1.
> > \end{cases}$$
> >
> > The distribution of $X$ is called the **uniform distribution on $[0,1]$**:
> >
> > $$X\sim\operatorname{Unif}([0,1]).$$
> >
> > In this case, the law of $X$ is the same as $P$.
>
> > [!example]- Example: Function of a Random Variable
> >
> > Consider another random variable
> >
> > $$Y=X^2.$$
> >
> > Since a measurable function of a random variable is also a random variable, $Y$ is a random variable.
> >
> > We can find its CDF using the CDF of $X$:
> >
> > $$F_Y(y)=P(Y\leq y)=P(X^2\leq y).$$
> >
> > If $y<0$, then $X^2\geq0$, so
> >
> > $$F_Y(y)=0.$$
> >
> > If $y\geq0$, since $X\in[0,1]$,
> >
> > $$P(X^2\leq y)=P(X\leq\sqrt{y}).$$
> >
> > Therefore,
> >
> > $$F_Y(y)=
> > \begin{cases}
> > 0, & y<0,\\
> > \sqrt{y}, & 0\leq y<1,\\
> > 1, & y\geq1.
> > \end{cases}$$
> >
> > This illustrates an important idea:
> >
> > $$\boxed{\text{CDF of a function of }X\text{ can often be found using the CDF of }X.}$$
>
> > [!warning]- Neither Discrete Nor Continuous
> >
> > A random variable does not have to be either discrete or continuous. There are random variables that are **neither**.
> >
> > Consider a coin toss together with a stick-breaking experiment:
> >
> > $$\Omega=\{H,T\}\times[0,1].$$
> >
> > Define $X$ as follows:
> >
> > $$X(\omega)=
> > \begin{cases}
> > 0, & \omega_1=H,\\
> > \omega_2, & \omega_1=T,
> > \end{cases}$$
> >
> > where $\omega=(\omega_1,\omega_2)$.
> >
> > In words:
> >
> > - If the coin lands **Heads**, $X=0$.
> > - If the coin lands **Tails**, $X$ is the breaking point.
> >
> > Its CDF is
> >
> > $$F_X(x)=
> > \begin{cases}
> > 0, & x<0,\\
> > \frac12(1+x), & 0\leq x<1,\\
> > 1, & x\geq1.
> > \end{cases}$$
> >
> > This distribution has both:
> >
> > $$P(X=0)=\frac12$$
> >
> > and a continuous component on $(0,1)$.
> >
> > Therefore, $X$ is **neither discrete nor continuous**.
>
> > [!tip]- Key Distinction
> >
> > **Discrete:** Probability is concentrated on individual points.
> >
> > $$P(X=x_i)>0$$
> >
> > **Continuous:** Probability is described by a density and individual points have probability zero.
> >
> > $$P(X=x)=0$$
> >
> > **Neither:** The distribution can contain both discrete point masses and a continuous component.

---

> [!important]- Random Vectors
>
> If $X$ and $Y$ are random variables, their individual CDFs $F_X$ and $F_Y$ give information about each variable separately.
>
> Sometimes, however, we want to study the random variables **together**.
>
> > [!abstract]- Definition
> >
> > Let $X_1,\ldots,X_n$ be $n$ random variables defined on a probability space $(\Omega,\mathcal{F},P)$.
> >
> > The $\mathbb{R}^n$-valued $\mathcal{F}$-measurable function
> >
> > $$X=(X_1,\ldots,X_n)$$
> >
> > is called a **random vector**.
> >
> > In other words, a random vector simply groups several random variables together.
>
> > [!example]- Comparing Two Random Variables
> >
> > Instead of studying
> >
> > $$F_X(x)=P(X\leq x)$$
> >
> > and
> >
> > $$F_Y(y)=P(Y\leq y)$$
> >
> > separately, we may want to know the probability that **both conditions hold simultaneously**:
> >
> > $$P(X\leq x,\;Y\leq y).$$
> >
> > This leads to the **joint distribution function**.
>
> > [!abstract]- Componentwise Order
> >
> > For $\mathbf{x},\mathbf{y}\in\mathbb{R}^n$, we write
> >
> > $$\mathbf{x}\leq\mathbf{y}$$
> >
> > when
> >
> > $$x_1\leq y_1,\quad x_2\leq y_2,\quad\ldots,\quad x_n\leq y_n.$$
> >
> > Thus, the inequality between vectors is interpreted **component by component**.
>
> > [!important]- Joint Distribution Function
> >
> > Given a random vector
> >
> > $$X=(X_1,\ldots,X_n),$$
> >
> > its **joint distribution function** is
> >
> > $$F_X:\mathbb{R}^n\rightarrow[0,1]$$
> >
> > defined by
> >
> > $$F_X(x_1,\ldots,x_n)
> > =P(X\leq x)
> > =P(X_1\leq x_1,\ldots,X_n\leq x_n).$$
> >
> > Equivalently,
> >
> > $$F_X(x)=P(\{\omega\in\Omega:X(\omega)\leq x\}).$$
> >
> > Since $X$ is $\mathcal{F}$-measurable,
> >
> > $$\{X\leq x\}\in\mathcal{F},$$
> >
> > so this probability is well-defined.
>
> > [!tip]- Marginal Distribution Functions
> >
> > Each individual random variable $X_i$ has its own CDF:
> >
> > $$F_{X_i}(x)=P(X_i\leq x).$$
> >
> > These individual CDFs are called the **marginal distribution functions**.
> >
> > The distinction is:
> >
> > $$\boxed{\text{Joint CDF}\rightarrow\text{variables studied together}}$$
> >
> > $$\boxed{\text{Marginal CDF}\rightarrow\text{variables studied individually}}$$

> [!important]- Properties of Joint Distribution Functions
>
> Suppose $(X,Y)$ is a random vector and $F_{X,Y}$ is its joint CDF:
>
> $$F_{X,Y}(x,y)=P(X\leq x,\;Y\leq y).$$
>
> > [!abstract]- Limits
> >
> > The joint CDF satisfies
> >
> > $$\lim_{x,y\to-\infty}F_{X,Y}(x,y)=0$$
> >
> > and
> >
> > $$\lim_{x,y\to\infty}F_{X,Y}(x,y)=1.$$
> >
> > Intuitively, when both $x$ and $y$ go towards $-\infty$, the event $\{X\leq x,Y\leq y\}$ becomes impossible. When both go towards $\infty$, the event eventually covers the whole sample space.
>
> > [!abstract]- Nondecreasing
> >
> > If
> >
> > $$(x_1,y_1)\leq(x_2,y_2),$$
> >
> > meaning
> >
> > $$x_1\leq x_2,\qquad y_1\leq y_2,$$
> >
> > then
> >
> > $$F_{X,Y}(x_1,y_1)\leq F_{X,Y}(x_2,y_2).$$
> >
> > This follows because
> >
> > $$\{X\leq x_1,Y\leq y_1\}\subseteq\{X\leq x_2,Y\leq y_2\}.$$
>
> > [!abstract]- Continuity From Above
> >
> > For any $x,y\in\mathbb{R}$,
> >
> > $$\lim_{h_1,h_2\downarrow0}F_{X,Y}(x+h_1,y+h_2)=F_{X,Y}(x,y).$$
> >
> > This is the two-dimensional analogue of the **right continuity** of a single CDF.
> >
> > The proof follows from the same continuity-of-probability argument used for ordinary CDFs.
>
> > [!tip]- Higher Dimensions
> >
> > The same properties hold for the joint CDF of an $n$-dimensional random vector
> >
> > $$X=(X_1,\ldots,X_n).$$
>
> > [!important]- Obtaining Marginal Distributions
> >
> > The joint distribution contains enough information to recover the individual, or **marginal**, distributions.
> >
> > For $X$:
> >
> > $$F_X(x)=P(X\leq x).$$
> >
> > Since the event $\{Y\leq y\}$ eventually covers the entire sample space as $y\to\infty$,
> >
> > $$F_X(x)
> > =\lim_{y\to\infty}P(X\leq x,Y\leq y).$$
> >
> > Therefore,
> >
> > $$\boxed{F_X(x)=\lim_{y\to\infty}F_{X,Y}(x,y).}$$
> >
> > Similarly,
> >
> > $$\boxed{F_Y(y)=\lim_{x\to\infty}F_{X,Y}(x,y).}$$
> >
> > Thus, we can obtain the **marginal distributions from the joint distribution**.
> >
> > This process is called **marginalization**.
>
> > [!abstract]- Key Relationship
> >
> > $$\boxed{
> > \text{Joint distribution}
> > \xrightarrow{\text{marginalization}}
> > \text{Marginal distributions}
> > }$$
> >
> > The joint CDF describes $X$ and $Y$ **together**, while the marginal CDFs describe them **individually**.

> [!important]- Jointly Discrete and Continuous Random Variables
>
> > [!example]- Jointly Discrete Random Variables
> >
> > A random vector $(X,Y)$ is called **jointly discrete** if it takes values in some countable subset of $\mathbb{R}^2$.
> >
> > In this case, the **joint probability mass function (joint pmf)** is defined by
> >
> > $$f_{X,Y}(x,y)=P(X=x,Y=y).$$
> >
> > It gives the probability that the random vector takes the particular value $(x,y)$.
>
> > [!example]- Jointly Continuous Random Variables
> >
> > A random vector $(X,Y)$ is called **jointly continuous** if there exists an integrable function $f:\mathbb{R}^2\rightarrow[0,\infty)$ such that
> >
> > $$F_{X,Y}(x,y)=\int_{-\infty}^{x}\int_{-\infty}^{y}f(u,v)\,dv\,du.$$
> >
> > The function $f$ is called the **joint probability density function (joint pdf)** of $(X,Y)$.
> >
> > The same definitions extend naturally to an $n$-dimensional random vector.
>
> > [!tip]- Marginalization
> >
> > We can obtain the marginal distributions from the joint distribution.
> >
> > For a jointly discrete random vector,
> >
> > $$f_X(x)=\sum_y f_{X,Y}(x,y).$$
> >
> > Similarly,
> >
> > $$f_Y(y)=\sum_x f_{X,Y}(x,y).$$
> >
> > For a jointly continuous random vector,
> >
> > $$f_X(x)=\int_{-\infty}^{\infty}f_{X,Y}(x,y)\,dy$$
> >
> > and
> >
> > $$f_Y(y)=\int_{-\infty}^{\infty}f_{X,Y}(x,y)\,dx.$$
>
> > [!example]- Dartboard Example
> >
> > A dart is thrown at a circular dartboard of radius $\rho$, and every point on the dartboard is equally likely.
> >
> > The sample space is
> >
> > $$\Omega=\{(x,y):x^2+y^2\leq\rho^2\}.$$
> >
> > The probability of a region $A$ is proportional to its area:
> >
> > $$P(A)=\frac{\operatorname{Area}(A)}{\pi\rho^2}.$$
> >
> > Let $R$ denote the distance from the center to the point where the dart lands:
> >
> > $$R(x,y)=\sqrt{x^2+y^2}.$$
> >
> > For $0\leq r\leq\rho$,
> >
> > $$F_R(r)=P(R\leq r).$$
> >
> > The event $\{R\leq r\}$ corresponds to a circle of radius $r$, whose area is $\pi r^2$. Therefore,
> >
> > $$F_R(r)=\frac{\pi r^2}{\pi\rho^2}=\frac{r^2}{\rho^2}.$$
> >
> > Hence,
> >
> > $$F_R(r)=
> > \begin{cases}
> > 0, & r<0,\\
> > \frac{r^2}{\rho^2}, & 0\leq r\leq\rho,\\
> > 1, & r\geq\rho.
> > \end{cases}$$
> >
> > Since
> >
> > $$F_R(r)=\int_{-\infty}^{r}f_R(u)\,du,$$
> >
> > the density is
> >
> > $$f_R(r)=
> > \begin{cases}
> > \frac{2r}{\rho^2}, & 0\leq r\leq\rho,\\
> > 0, & \text{otherwise}.
> > \end{cases}$$
> >
> > Therefore, $R$ is a **continuous random variable**.
>
> > [!example]- Dartboard Example: Radius and Angle
> >
> > Now consider another random variable $\Theta$ representing the angle from the vertical axis, measured clockwise.
> >
> > We now study the random vector
> >
> > $$(R,\Theta).$$
> >
> > The event
> >
> > $$\{R\leq r,\Theta\leq\theta\}$$
> >
> > corresponds to a sector with radius $r$ and angle $\theta$.
> >
> > The area of this sector is
> >
> > $$\frac12r^2\theta.$$
> >
> > Therefore,
> >
> > $$F_{R,\Theta}(r,\theta)
> > =P(R\leq r,\Theta\leq\theta)
> > =\frac{\frac12r^2\theta}{\pi\rho^2}
> > =\frac{r^2\theta}{2\pi\rho^2}.$$
> >
> > For $0\leq r\leq\rho$ and $0\leq\theta\leq2\pi$,
> >
> > $$F_{R,\Theta}(r,\theta)
> > =\int_0^r\int_0^\theta f_{R,\Theta}(u,v)\,dv\,du.$$
> >
> > Therefore, the joint density is
> >
> > $$f_{R,\Theta}(r,\theta)=
> > \begin{cases}
> > \frac{r}{\pi\rho^2}, & 0\leq r\leq\rho,\;0\leq\theta\leq2\pi,\\
> > 0, & \text{otherwise}.
> > \end{cases}$$
> >
> > Thus, $(R,\Theta)$ is a **jointly continuous random vector**.
>
> > [!important]- Key Idea
> >
> > For one random variable:
> >
> > $$X\longrightarrow f_X(x)$$
> >
> > For two random variables considered together:
> >
> > $$(X,Y)\longrightarrow f_{X,Y}(x,y).$$
> >
> > The **joint distribution** describes how the variables behave together, while **marginalization** gives the distribution of each variable individually.
>
> > $$\boxed{\text{Joint distribution}\xrightarrow{\text{marginalization}}\text{Marginal distributions}}$$











