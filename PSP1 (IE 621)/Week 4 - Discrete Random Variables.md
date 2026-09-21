
> [!important]- Discrete Random Variables
>
> > [!abstract]- Context: What Is a Discrete Random Variable?
> >
> > A **discrete random variable** is a random variable whose possible values form a **discrete subset of $\mathbb R$**.
> >
> > For example:
> >
> > $$X\in\{0,1,2,\ldots\}$$
> >
> > or
> >
> > $$X\in\{x_1,x_2,x_3,\ldots\}.$$
> >
> > Instead of studying the entire probability space $(\Omega,\mathcal F,P)$, we can often study $X$ directly through its **probability mass function (pmf)**.
>
> > [!important]- Probability Mass Function (PMF)
> >
> > For a discrete random variable $X$, its probability mass function is
> >
> > $$\boxed{
> > f_X(x)=P(X=x)
> > }$$
> >
> > It assigns a probability to each possible value of $X$.
> >
> > The pmf satisfies:
> >
> > $$\boxed{f_X(x)\geq0}$$
> >
> > and
> >
> > $$\boxed{
> > \sum_x f_X(x)=1.
> > }$$
> >
> > If $X$ can take values $x_1,x_2,\ldots$, then:
> >
> > $$\boxed{
> > \sum_i f_X(x_i)=1.
> > }$$
> >
> > If the random variable $X$ is clear from context, we may simply write $f(x)$ instead of $f_X(x)$.
>
> > [!abstract]- Probability of a Set of Values
> >
> > Suppose $A$ is a subset of the possible values of $X$:
> >
> > $$A\subseteq\{x_1,x_2,\ldots\}.$$
> >
> > The event
> >
> > $$\{X\in A\}$$
> >
> > means that the value taken by $X$ belongs to $A$.
> >
> > Since the events $\{X=x\}$ are mutually disjoint:
> >
> > $$\{X\in A\}
> > =
> > \bigcup_{x\in A}\{X=x\},$$
> >
> > countable additivity gives:
> >
> > $$\boxed{
> > P(X\in A)
> > =
> > \sum_{x\in A}f_X(x).
> > }$$
> >
> > This is one of the most important formulas for a discrete random variable.
>
> > [!important]- CDF From the PMF
> >
> > The cumulative distribution function is
> >
> > $$F_X(x)=P(X\leq x).$$
> >
> > Since $X$ is discrete, we add the probabilities of all possible values not exceeding $x$:
> >
> > $$\boxed{
> > F_X(x)
> > =
> > \sum_{i:x_i\leq x}f_X(x_i).
> > }$$
> >
> > Therefore:
> >
> > $$\boxed{
> > \text{PMF}\quad\xrightarrow{\text{cumulative sum}}\quad\text{CDF}
> > }$$
> >
> > The PMF tells us the probability at each individual point, while the CDF accumulates those probabilities up to $x$.
>
> > [!example]- Bernoulli Random Variable
> >
> > A **Bernoulli random variable** represents a single yes/no or success/failure experiment.
> >
> > Let
> >
> > $$X=
> > \begin{cases}
> > 1,&\text{with probability }p,\\
> > 0,&\text{with probability }1-p.
> > \end{cases}$$
> >
> > Its possible values are:
> >
> > $$X\in\{0,1\}.$$
> >
> > Therefore its pmf is:
> >
> > $$\boxed{
> > f_X(x)=
> > \begin{cases}
> > p,&x=1,\\
> > 1-p,&x=0,\\
> > 0,&\text{otherwise}.
> > \end{cases}
> > }$$
> >
> > Usually, we interpret:
> >
> > $$1=\text{success},\qquad 0=\text{failure}.$$
> >
> > The distribution is denoted:
> >
> > $$\boxed{X\sim\operatorname{Bernoulli}(p).}$$
>
> > [!abstract]- From Bernoulli Trials to Binomial
> >
> > Now perform the same Bernoulli experiment $n$ times independently.
> >
> > Suppose the probability of success in each trial is $p$ and define
> >
> > $$q=1-p.$$
> >
> > Let $X$ be the **number of successes** in the $n$ trials.
> >
> > Then:
> >
> > $$X\in\{0,1,\ldots,n\}.$$
> >
> > This random variable follows a **binomial distribution**.
>
> > [!important]- Deriving the Binomial PMF
> >
> > We want to calculate:
> >
> > $$P(X=k).$$
> >
> > This means exactly $k$ successes and $n-k$ failures occur.
> >
> > For any **particular arrangement** containing $k$ successes and $n-k$ failures:
> >
> > $$P(\text{particular arrangement})
> > =
> > p^kq^{n-k}.$$
> >
> > For example, if $n=4$ and $k=2$, the pattern
> >
> > $$SFSF$$
> >
> > has probability
> >
> > $$pqpq=p^2q^2.$$
> >
> > But there are many different arrangements containing exactly $k$ successes.
>
> > [!important]- Counting the Arrangements
> >
> > The number of ways to choose which $k$ of the $n$ trials are successes is
> >
> > $$\boxed{
> > \binom nk
> > =
> > \frac{n!}{k!(n-k)!}.
> > }$$
> >
> > Every such arrangement has probability
> >
> > $$p^kq^{n-k}.$$
> >
> > Therefore:
> >
> > $$\boxed{
> > P(X=k)
> > =
> > \binom nk p^kq^{n-k}.
> > }$$
>
> > [!important]- Binomial Distribution
> >
> > A random variable $X$ has a **binomial distribution** with parameters $n$ and $p$ if
> >
> > $$\boxed{
> > X\sim\operatorname{Bin}(n,p)
> > }$$
> >
> > with pmf
> >
> > $$\boxed{
> > f_X(k)
> > =
> > \binom nk p^k(1-p)^{n-k},
> > \qquad k=0,1,\ldots,n.
> > }$$
> >
> > Here:
> >
> > $$n=\text{number of independent trials}$$
> >
> > $$p=\text{probability of success in each trial}$$
> >
> > $$k=\text{number of successes}. $$
>
> > [!example]- Simple Binomial Example
> >
> > Suppose a fair coin is tossed $4$ times and $X$ is the number of Heads.
> >
> > Then:
> >
> > $$n=4,\qquad p=\frac12.$$
> >
> > The probability of exactly $2$ Heads is:
> >
> > $$P(X=2)
> > =
> > \binom42
> > \left(\frac12\right)^2
> > \left(\frac12\right)^2.$$
> >
> > Therefore:
> >
> > $$P(X=2)
> > =
> > 6\cdot\frac1{16}
> > =
> > \frac38.$$
> >
> > The factor $\binom42$ counts the six possible arrangements:
> >
> > $$HHTT,\ HTHT,\ HTTH,\ THHT,\ THTH,\ TTHH.$$
>
> > [!tip]- Important Distinction
> >
> > For exactly $k$ successes:
> >
> > $$\boxed{
> > P(X=k)
> > =
> > \underbrace{\binom nk}_{\text{number of arrangements}}
> > \times
> > \underbrace{p^k(1-p)^{n-k}}_{\text{probability of each arrangement}}
> > }$$
> >
> > The binomial coefficient is necessary because $X=k$ does **not** specify the order of the successes.
>
> > [!abstract]- PMF vs CDF
> >
> > For a discrete random variable:
> >
> > **PMF:**
> >
> > $$\boxed{f_X(k)=P(X=k)}$$
> >
> > **CDF:**
> >
> > $$\boxed{F_X(x)=P(X\leq x)}$$
> >
> > and therefore:
> >
> > $$\boxed{
> > F_X(x)=\sum_{k\leq x}f_X(k).
> > }$$
> >
> > So the CDF is obtained by **accumulating the PMF**.
>
> > [!important]- Why the PMF Is Enough
> >
> > Once the pmf $f_X$ is known, we can calculate probabilities of all events involving $X$:
> >
> > $$P(X\in A)=\sum_{x\in A}f_X(x).$$
> >
> > We can also obtain the CDF:
> >
> > $$F_X(x)=\sum_{t\leq x}f_X(t).$$
> >
> > Therefore, we can study the distribution of $X$ without explicitly specifying:
> >
> > $$\Omega,\qquad\mathcal F,\qquad P,\qquad X:\Omega\to\mathbb R.$$
> >
> > The pmf contains all the information needed about the **distribution of the discrete random variable**.
>
> > [!important]- Big Picture
> >
> > $$\boxed{
> > \text{Probability space}
> > \longrightarrow
> > \text{Random variable }X
> > \longrightarrow
> > \text{PMF }f_X
> > \longrightarrow
> > \text{CDF }F_X
> > }$$
> >
> > For discrete $X$:
> >
> > $$\boxed{
> > f_X(x)=P(X=x)
> > }$$
> >
> > $$\boxed{
> > P(X\in A)=\sum_{x\in A}f_X(x)
> > }$$
> >
> > $$\boxed{
> > F_X(x)=\sum_{t\leq x}f_X(t)
> > }$$
> >
> > For $n$ independent Bernoulli trials:
> >
> > $$\boxed{
> > X\sim\operatorname{Bin}(n,p)
> > }$$
> >
> > $$\boxed{
> > P(X=k)=\binom nkp^k(1-p)^{n-k}.
> > }$$

> [!important]- Independence of Random Variables
>
> > [!abstract]- Context: From Independent Events to Independent Random Variables
> >
> > Recall that two events $A$ and $B$ are independent if
> >
> > $$\boxed{
> > P(A\cap B)=P(A)P(B).
> > }$$
> >
> > For random variables $X$ and $Y$, we want a similar idea:
> >
> > $$\boxed{
> > \text{Knowing the value of }X\text{ gives no information about }Y.
> > }$$
> >
> > In other words, observing $X$ should not change the distribution of $Y$, and vice versa.
>
> > [!abstract]- Connecting Random Variables to Events
> >
> > For a discrete random variable $X$, we can write
> >
> > $$X=\sum_{x:f_X(x)>0}x\,1_{\{X=x\}}.$$
> >
> > Similarly:
> >
> > $$Y=\sum_{y:f_Y(y)>0}y\,1_{\{Y=y\}}.$$
> >
> > Define the events
> >
> > $$A_x=\{X=x\}$$
> >
> > and
> >
> > $$B_y=\{Y=y\}.$$
> >
> > Thus, knowing the value of $X$ corresponds to knowing which event $A_x$ occurred.
> >
> > This motivates defining independence of $X$ and $Y$ through independence of all such events.
>
> > [!important]- Definition
> >
> > Two discrete random variables $X$ and $Y$ are **independent** if
> >
> > $$\boxed{
> > \{X=x\}\text{ and }\{Y=y\}
> > \text{ are independent for every }x,y.
> > }$$
> >
> > Therefore:
> >
> > $$\boxed{
> > P(X=x,Y=y)
> > =
> > P(X=x)P(Y=y)
> > }$$
> >
> > for every possible pair $(x,y)$.
>
> > [!abstract]- Joint PMF
> >
> > The **joint probability mass function** of $X$ and $Y$ is
> >
> > $$\boxed{
> > f_{X,Y}(x,y)=P(X=x,Y=y).
> > }$$
> >
> > If $X$ and $Y$ are independent, then
> >
> > $$P(X=x,Y=y)
> > =
> > P(X=x)P(Y=y).$$
> >
> > Therefore:
> >
> > $$\boxed{
> > f_{X,Y}(x,y)=f_X(x)f_Y(y).
> > }$$
>
> > [!important]- Characterization Theorem
> >
> > Two discrete random variables $X$ and $Y$ are independent **if and only if**
> >
> > $$\boxed{
> > f_{X,Y}(x,y)=f_X(x)f_Y(y)
> > \qquad\text{for all }x,y.
> > }$$
> >
> > This gives a very convenient way to check independence.
> >
> > **Factorization of the joint PMF = independence.**
>
> > [!abstract]- Proof: Independence $\Rightarrow$ PMF Factorization
> >
> > Suppose $X$ and $Y$ are independent.
> >
> > By definition, the events $\{X=x\}$ and $\{Y=y\}$ are independent.
> >
> > Therefore:
> >
> > $$P(\{X=x\}\cap\{Y=y\})
> > =
> > P(X=x)P(Y=y).$$
> >
> > But
> >
> > $$\{X=x\}\cap\{Y=y\}
> > =
> > \{X=x,Y=y\}.$$
> >
> > Hence:
> >
> > $$P(X=x,Y=y)
> > =
> > P(X=x)P(Y=y).$$
> >
> > Using the definitions of the pmfs:
> >
> > $$\boxed{
> > f_{X,Y}(x,y)=f_X(x)f_Y(y).
> > }$$
>
> > [!abstract]- Proof: PMF Factorization $\Rightarrow$ Independence
> >
> > Suppose
> >
> > $$f_{X,Y}(x,y)=f_X(x)f_Y(y)$$
> >
> > for every $x,y$.
> >
> > Since
> >
> > $$f_{X,Y}(x,y)=P(X=x,Y=y),$$
> >
> > we obtain:
> >
> > $$P(X=x,Y=y)
> > =
> > P(X=x)P(Y=y).$$
> >
> > Therefore:
> >
> > $$P(\{X=x\}\cap\{Y=y\})
> > =
> > P(X=x)P(Y=y).$$
> >
> > Hence $\{X=x\}$ and $\{Y=y\}$ are independent for every $x,y$.
> >
> > Therefore:
> >
> > $$\boxed{X\text{ and }Y\text{ are independent}.}$$
>
> > [!example]- Binomial Distribution and Independent Bernoulli Trials
> >
> > Suppose
> >
> > $$X_1,X_2,\ldots,X_n
> > \overset{\text{i.i.d.}}{\sim}\operatorname{Ber}(p).$$
> >
> > That means each $X_i$ is a Bernoulli random variable with success probability $p$, and the trials are independent.
> >
> > Define
> >
> > $$S_n=X_1+\cdots+X_n.$$
> >
> > Then $S_n$ counts the number of successes in the $n$ trials.
> >
> > Therefore:
> >
> > $$\boxed{
> > S_n\sim\operatorname{Bin}(n,p).
> > }$$
> >
> > Thus, a binomial random variable can be viewed as the **sum of $n$ independent Bernoulli random variables**.
>
> > [!tip]- Intuition
> >
> > Suppose:
> >
> > $$X=\text{result of today's coin toss}$$
> >
> > $$Y=\text{result of tomorrow's coin toss}.$$
> >
> > If the tosses are independent, knowing that
> >
> > $$X=H$$
> >
> > does not change the probability that
> >
> > $$Y=H.$$
> >
> > In particular:
> >
> > $$P(Y=H\mid X=H)=P(Y=H).$$
> >
> > So:
> >
> > $$\boxed{
> > \text{Independence means knowing one random variable does not provide information about the other.}
> > }$$
>
> > [!important]- Independence vs. Uncorrelated
> >
> > Independence is a strong condition.
> >
> > If $X$ and $Y$ are independent and the relevant expectations exist, then they are uncorrelated:
> >
> > $$\operatorname{Cov}(X,Y)=0.$$
> >
> > However:
> >
> > $$\boxed{
> > \text{Uncorrelated}\not\Rightarrow\text{Independent}
> > }$$
> >
> > So independence contains more information than simply having zero covariance.
>
> > [!abstract]- More Than Two Random Variables
> >
> > The same idea extends to a finite collection:
> >
> > $$X_1,X_2,\ldots,X_n.$$
> >
> > They are mutually independent if the joint probabilities factor appropriately for every finite collection of variables.
> >
> > For example:
> >
> > $$P(X_1=x_1,\ldots,X_n=x_n)
> > =
> > \prod_{i=1}^nP(X_i=x_i).$$
> >
> > **Important:** pairwise independence does not necessarily imply mutual independence.
>
> > [!important]- Big Picture
> >
> > For events:
> >
> > $$\boxed{
> > P(A\cap B)=P(A)P(B)
> > }$$
> >
> > For discrete random variables:
> >
> > $$\boxed{
> > P(X=x,Y=y)
> > =
> > P(X=x)P(Y=y)
> > }$$
> >
> > Equivalently:
> >
> > $$\boxed{
> > f_{X,Y}(x,y)=f_X(x)f_Y(y)
> > }$$
> >
> > Therefore:
> >
> > $$\boxed{
> > \text{Independent random variables}
> > \iff
> > \text{Joint PMF factorizes into marginal PMFs}.
> > }$$

> [!important]- More Examples of Discrete Random Variables
>
> > [!abstract]- Finite vs. Infinite Support
> >
> > Recall that the **support** of a discrete random variable is the set of values that it can take with positive probability.
> >
> > **Finite support:**
> >
> > $$X\sim\operatorname{Ber}(p)
> > \quad\Rightarrow\quad
> > X\in\{0,1\}$$
> >
> > $$X\sim\operatorname{Bin}(n,p)
> > \quad\Rightarrow\quad
> > X\in\{0,1,\ldots,n\}.$$
> >
> > Both have only finitely many possible values.
> >
> > **Infinite support:**
> >
> > Some discrete random variables can take infinitely many values. Two important examples are the **Geometric** and **Poisson** distributions.
>
> > [!important]- Geometric Distribution
> >
> > Consider a biased coin with:
> >
> > $$P(H)=p,\qquad P(T)=1-p=q.$$
> >
> > Toss the coin repeatedly until the first Head occurs.
> >
> > Let
> >
> > $$X=\text{toss number on which the first Head occurs}.$$
> >
> > Then:
> >
> > $$X\in\{1,2,3,\ldots\}.$$
> >
> > For the first Head to occur on toss $k$, we need:
> >
> > $$\underbrace{TT\cdots T}_{k-1\text{ tails}}H.$$
> >
> > By independence:
> >
> > $$P(X=k)
> > =
> > q^{k-1}p.$$
> >
> > Therefore:
> >
> > $$\boxed{
> > f_X(k)=(1-p)^{k-1}p,
> > \qquad k=1,2,3,\ldots
> > }$$
> >
> > This is the **geometric distribution**:
> >
> > $$\boxed{
> > X\sim\operatorname{Geom}(p).
> > }$$
> >
> > Interpretation:
> >
> > $$\boxed{
> > \operatorname{Geom}(p)
> > =
> > \text{number of trials until the first success}
> > }$$
> >
> > where the trials are independent $\operatorname{Ber}(p)$ trials.
>
> > [!abstract]- Why Geometric Has Infinite Support
> >
> > There is no fixed maximum number of tosses before the first Head.
> >
> > The first Head could occur on:
> >
> > $$1,2,3,\ldots$$
> >
> > For example:
> >
> > $$P(X=1)=p$$
> >
> > $$P(X=2)=qp$$
> >
> > $$P(X=3)=q^2p$$
> >
> > $$\vdots$$
> >
> > Hence the support is infinite.
>
> > [!important]- Poisson Distribution
> >
> > The Poisson distribution arises as a limiting form of the binomial distribution.
> >
> > Suppose:
> >
> > $$X_n\sim\operatorname{Bin}(n,p).$$
> >
> > Let $n\to\infty$ while making $p$ small in such a way that
> >
> > $$np\to\lambda.$$
> >
> > Here $\lambda>0$ is kept fixed.
> >
> > Then:
> >
> > $$\boxed{
> > P(X_n=k)
> > \longrightarrow
> > e^{-\lambda}\frac{\lambda^k}{k!}.
> > }$$
> >
> > This limiting distribution is called the **Poisson distribution** with parameter $\lambda$:
> >
> > $$\boxed{
> > X\sim\operatorname{Poi}(\lambda).
> > }$$
>
> > [!abstract]- Poisson PMF
> >
> > The probability mass function is:
> >
> > $$\boxed{
> > f_X(k)
> > =
> > e^{-\lambda}\frac{\lambda^k}{k!},
> > \qquad k=0,1,2,\ldots
> > }$$
> >
> > The support is infinite:
> >
> > $$\{0,1,2,\ldots\}.$$
> >
> > The probabilities sum to $1$ because:
> >
> > $$\sum_{k=0}^{\infty}
> > e^{-\lambda}\frac{\lambda^k}{k!}
> > =
> > e^{-\lambda}
> > \sum_{k=0}^{\infty}\frac{\lambda^k}{k!}.$$
> >
> > Using
> >
> > $$e^\lambda
> > =
> > \sum_{k=0}^{\infty}\frac{\lambda^k}{k!},$$
> >
> > we obtain:
> >
> > $$e^{-\lambda}e^\lambda=1.$$
>
> > [!abstract]- Binomial $\to$ Poisson Intuition
> >
> > The Poisson distribution models a situation with:
> >
> > $$\boxed{
> > \text{many trials/events}
> > +
> > \text{small probability per trial}
> > +
> > \text{fixed average rate}
> > }$$
> >
> > The condition
> >
> > $$np\to\lambda$$
> >
> > means:
> >
> > $$\boxed{
> > \text{number of opportunities}\to\infty,
> > \qquad
> > \text{probability of each opportunity}\to0,
> > }$$
> >
> > while the expected number of successes stays approximately $\lambda$.
>
> > [!important]- A Surprising Independence Example
> >
> > Consider a biased coin:
> >
> > $$P(H)=p,\qquad P(T)=q=1-p.$$
> >
> > First, toss it **once**.
> >
> > Let:
> >
> > $$X=\text{number of Heads},$$
> >
> > $$Y=\text{number of Tails}.$$
> >
> > Since exactly one outcome occurs:
> >
> > $$X+Y=1.$$
> >
> > Therefore $X$ and $Y$ cannot be independent.
>
> > [!example]- One Toss: Not Independent
> >
> > We have:
> >
> > $$P(X=1)=p$$
> >
> > and
> >
> > $$P(Y=1)=q.$$
> >
> > But both cannot equal $1$ simultaneously:
> >
> > $$P(X=1,Y=1)=0.$$
> >
> > If they were independent, we would need:
> >
> > $$P(X=1,Y=1)=P(X=1)P(Y=1)=pq.$$
> >
> > Since $pq>0$ for $0<p<1$:
> >
> > $$\boxed{
> > 0\neq pq.
> > }$$
> >
> > Hence $X$ and $Y$ are **not independent**.
> >
> > In fact, the events $\{X=1\}$ and $\{Y=1\}$ are disjoint.
> >
> > **Disjoint does not mean independent.**
>
> > [!important]- Now Randomize the Number of Tosses
> >
> > Suppose instead that the number of tosses $N$ itself is random:
> >
> > $$\boxed{
> > N\sim\operatorname{Poi}(\lambda).
> > }$$
> >
> > Toss the biased coin $N$ times.
> >
> > Let:
> >
> > $$X=\text{number of Heads},$$
> >
> > $$Y=\text{number of Tails}.$$
> >
> > Clearly:
> >
> > $$X+Y=N.$$
> >
> > At first, it may seem that $X$ and $Y$ should be dependent because their sum is $N$.
> >
> > Surprisingly:
> >
> > $$\boxed{X\text{ and }Y\text{ are independent}.}$$
>
> > [!abstract]- Joint Distribution of $X$ and $Y$
> >
> > Suppose we want:
> >
> > $$P(X=x,Y=y).$$
> >
> > If there are exactly $x$ Heads and $y$ Tails, then the total number of tosses must be:
> >
> > $$N=x+y.$$
> >
> > Therefore:
> >
> > $$P(X=x,Y=y)
> > =
> > P(N=x+y)
> > P(X=x,Y=y\mid N=x+y).$$
> >
> > Since
> >
> > $$N\sim\operatorname{Poi}(\lambda),$$
> >
> > $$P(N=x+y)
> > =
> > e^{-\lambda}
> > \frac{\lambda^{x+y}}{(x+y)!}.$$
> >
> > Given $N=x+y$, exactly $x$ of the $x+y$ tosses must be Heads.
> >
> > There are
> >
> > $$\binom{x+y}{x}$$
> >
> > such arrangements, each having probability $p^xq^y$.
> >
> > Hence:
> >
> > $$P(X=x,Y=y)
> > =
> > e^{-\lambda}
> > \frac{\lambda^{x+y}}{(x+y)!}
> > \binom{x+y}{x}p^xq^y.$$
>
> > [!important]- Simplifying the Joint PMF
> >
> > Using
> >
> > $$\binom{x+y}{x}
> > =
> > \frac{(x+y)!}{x!y!},$$
> >
> > we obtain:
> >
> > $$P(X=x,Y=y)
> > =
> > e^{-\lambda}
> > \frac{\lambda^{x+y}}{x!y!}p^xq^y.$$
> >
> > Rearrange:
> >
> > $$P(X=x,Y=y)
> > =
> > \left(
> > e^{-\lambda p}\frac{(\lambda p)^x}{x!}
> > \right)
> > \left(
> > e^{-\lambda q}\frac{(\lambda q)^y}{y!}
> > \right),$$
> >
> > because
> >
> > $$p+q=1.$$
> >
> > Therefore:
> >
> > $$\boxed{
> > P(X=x,Y=y)
> > =
> > e^{-\lambda p}\frac{(\lambda p)^x}{x!}
> > \;
> > e^{-\lambda q}\frac{(\lambda q)^y}{y!}.
> > }$$
>
> > [!important]- Marginal Distributions
> >
> > From the marginal calculation:
> >
> > $$\boxed{
> > X\sim\operatorname{Poi}(p\lambda)
> > }$$
> >
> > and similarly:
> >
> > $$\boxed{
> > Y\sim\operatorname{Poi}(q\lambda).
> > }$$
> >
> > Therefore:
> >
> > $$P(X=x)
> > =
> > e^{-p\lambda}
> > \frac{(p\lambda)^x}{x!},$$
> >
> > $$P(Y=y)
> > =
> > e^{-q\lambda}
> > \frac{(q\lambda)^y}{y!}.$$
>
> > [!important]- Proving Independence
> >
> > We have:
> >
> > $$P(X=x,Y=y)
> > =
> > e^{-p\lambda}\frac{(p\lambda)^x}{x!}
> > \;
> > e^{-q\lambda}\frac{(q\lambda)^y}{y!}.$$
> >
> > But these are exactly the marginal probabilities:
> >
> > $$P(X=x)
> > =
> > e^{-p\lambda}\frac{(p\lambda)^x}{x!},$$
> >
> > $$P(Y=y)
> > =
> > e^{-q\lambda}\frac{(q\lambda)^y}{y!}.$$
> >
> > Hence:
> >
> > $$\boxed{
> > P(X=x,Y=y)=P(X=x)P(Y=y).
> > }$$
> >
> > Therefore:
> >
> > $$\boxed{
> > X\text{ and }Y\text{ are independent}.
> > }$$
>
> > [!abstract]- Why Is This Surprising?
> >
> > In the one-toss case:
> >
> > $$X+Y=1,$$
> >
> > so $X$ and $Y$ are dependent.
> >
> > In the Poisson-number-of-tosses case:
> >
> > $$X+Y=N,$$
> >
> > yet $X$ and $Y$ become independent because $N$ itself is Poisson.
> >
> > This is an important special property of the Poisson distribution:
> >
> > $$\boxed{
> > N\sim\operatorname{Poi}(\lambda)
> > \text{ and each event is independently classified}
> > }$$
> >
> > leads to independent Poisson counts.
>
> > [!tip]- Poisson Splitting Property
> >
> > The above result is called the **Poisson splitting/thinning property**.
> >
> > If
> >
> > $$N\sim\operatorname{Poi}(\lambda)$$
> >
> > and each of the $N$ events is independently classified as type 1 with probability $p$ and type 2 with probability $q=1-p$, then:
> >
> > $$\boxed{
> > X\sim\operatorname{Poi}(\lambda p),
> > \qquad
> > Y\sim\operatorname{Poi}(\lambda q)
> > }$$
> >
> > and
> >
> > $$\boxed{X\perp Y.}$$
>
> > [!important]- Distribution Summary
> >
> > $$\boxed{
> > \begin{array}{c|c|c}
> > \text{Distribution} & \text{Meaning} & \text{Support}\\
> > \hline
> > \operatorname{Ber}(p)
> > & \text{One success/failure trial}
> > & \{0,1\}\\
> > \operatorname{Bin}(n,p)
> > & \text{Number of successes in }n\text{ trials}
> > & \{0,\ldots,n\}\\
> > \operatorname{Geom}(p)
> > & \text{Trials until first success}
> > & \{1,2,\ldots\}\\
> > \operatorname{Poi}(\lambda)
> > & \text{Count of events at rate }\lambda
> > & \{0,1,2,\ldots\}
> > \end{array}
> > }$$
>
> > [!important]- Big Picture
> >
> > **Geometric:**
> >
> > $$\boxed{
> > P(X=k)=(1-p)^{k-1}p
> > }$$
> >
> > First success in independent Bernoulli trials.
> >
> > **Poisson:**
> >
> > $$\boxed{
> > P(X=k)=e^{-\lambda}\frac{\lambda^k}{k!}
> > }$$
> >
> > Limit of $\operatorname{Bin}(n,p)$ when $n\to\infty$, $p\to0$, and $np\to\lambda$.
> >
> > **Poisson splitting:**
> >
> > $$\boxed{
> > N\sim\operatorname{Poi}(\lambda)
> > \quad\Longrightarrow\quad
> > X\sim\operatorname{Poi}(p\lambda),\
> > Y\sim\operatorname{Poi}(q\lambda),\
> > X\perp Y.
> > }$$

---

> [!important]- Expectation of a Discrete Random Variable
>
> > [!abstract]- Context: Expectation as a Long-Run Average
> >
> > Suppose an experiment is performed $N$ times and produces numerical outcomes
> >
> > $$x_1,x_2,\ldots,x_N.$$
> >
> > Their empirical average is
> >
> > $$\frac1N\sum_{i=1}^N x_i.$$
> >
> > Instead of summing over trials, group together equal outcomes.
> >
> > Let $N(x)$ be the number of times outcome $x$ occurs. Then:
> >
> > $$\boxed{
> > \frac1N\sum_{i=1}^N x_i
> > =
> > \sum_x x\frac{N(x)}N
> > }$$
> >
> > Under the **frequentist interpretation**:
> >
> > $$\frac{N(x)}N\approx P(X=x)=f_X(x).$$
> >
> > Therefore, for a very large number of repetitions:
> >
> > $$\text{average}\approx\sum_xxf_X(x).$$
> >
> > This motivates the definition of expectation.
>
> > [!important]- Definition: Expectation
> >
> > Let $X$ be a discrete random variable with pmf $f_X$.
> >
> > The **expectation**, **mean**, or **expected value** of $X$ is
> >
> > $$\boxed{
> > E[X]
> > =
> > \sum_{x:f_X(x)>0}x f_X(x)
> > }$$
> >
> > provided the sum is **absolutely convergent**.
> >
> > For now, assume the required convergence condition holds.
> >
> > The formula can be interpreted as:
> >
> > $$\boxed{
> > E[X]
> > =
> > \sum
> > (\text{value})
> > \times
> > (\text{probability of that value})
> > }$$
>
> > [!abstract]- Intuition
> >
> > Expectation is a **probability-weighted average**.
> >
> > A value that occurs with high probability contributes more to the average, while a value with low probability contributes less.
> >
> > For example, if
> >
> > $$P(X=1)=0.8,\qquad P(X=5)=0.2,$$
> >
> > then
> >
> > $$E[X]
> > =1(0.8)+5(0.2)
> > =1.8.$$
> >
> > Note that $E[X]$ does not necessarily have to be a value that $X$ can actually take.
>
> > [!important]- Expectation Depends Only on the Distribution
> >
> > The expectation is determined entirely by the pmf:
> >
> > $$E[X]=\sum_xxf_X(x).$$
> >
> > Therefore, $E[X]$ depends only on the **law/distribution of $X$**, not on the particular underlying probability space or the particular representation of $X$.
> >
> > Thus:
> >
> > $$\boxed{
> > E[X]=\text{mean of the distribution of }X.
> > }$$
>
> > [!example]- Indicator Random Variable
> >
> > For an event $A$, define its indicator random variable:
> >
> > $$\mathbf 1_A=
> > \begin{cases}
> > 1,&A\text{ occurs},\\
> > 0,&A^c\text{ occurs}.
> > \end{cases}$$
> >
> > Suppose
> >
> > $$P(A)=p.$$
> >
> > Then:
> >
> > $$P(\mathbf1_A=1)=p$$
> >
> > and
> >
> > $$P(\mathbf1_A=0)=1-p.$$
> >
> > Therefore:
> >
> > $$\begin{aligned}
> > E[\mathbf1_A]
> > &=1\cdot P(A)+0\cdot P(A^c)\\
> > &=P(A).
> > \end{aligned}$$
> >
> > Hence:
> >
> > $$\boxed{
> > E[\mathbf1_A]=P(A).
> > }$$
> >
> > This is an extremely useful identity: **the expectation of an indicator equals the probability of its event.**
>
> > [!abstract]- Expectation of a Function of a Random Variable
> >
> > Suppose
> >
> > $$Y=g(X)$$
> >
> > for some function $g$.
> >
> > We want to calculate $E[Y]$ without first finding the entire pmf of $Y$.
> >
> > The key result is:
> >
> > $$\boxed{
> > E[g(X)]
> > =
> > \sum_{x:f_X(x)>0}g(x)f_X(x)
> > }$$
> >
> > This is sometimes called the **law of the unconscious statistician (LOTUS)** for discrete random variables.
>
> > [!abstract]- Derivation of $E[g(X)]$
> >
> > Since
> >
> > $$Y=g(X),$$
> >
> > by definition:
> >
> > $$E[Y]
> > =
> > \sum_{y:f_Y(y)>0}y f_Y(y).$$
> >
> > For a particular $y$, define
> >
> > $$g^{-1}(y)=\{x:g(x)=y\}.$$
> >
> > Then:
> >
> > $$\begin{aligned}
> > f_Y(y)
> > &=P(Y=y)\\
> > &=P(g(X)=y)\\
> > &=P(X\in g^{-1}(y))\\
> > &=\sum_{x:g(x)=y}f_X(x).
> > \end{aligned}$$
> >
> > The last equality follows from countable additivity.
>
> > [!important]- Completing the Derivation
> >
> > Substitute the expression for $f_Y(y)$ into the expectation:
> >
> > $$E[Y]
> > =
> > \sum_y y
> > \left(
> > \sum_{x:g(x)=y}f_X(x)
> > \right).$$
> >
> > Each $x$ is associated with exactly one value $y=g(x)$.
> >
> > Therefore, we can regroup the terms according to $x$:
> >
> > $$E[Y]
> > =
> > \sum_x g(x)f_X(x).$$
> >
> > Since $Y=g(X)$:
> >
> > $$\boxed{
> > E[g(X)]
> > =
> > \sum_xg(x)f_X(x).
> > }$$
> >
> > The important point is that we **do not need to explicitly calculate $f_Y$**.
>
> > [!example]- Simple Example of $E[g(X)]$
> >
> > Suppose:
> >
> > $$P(X=1)=\frac12,\qquad P(X=2)=\frac12.$$
> >
> > Let
> >
> > $$Y=X^2.$$
> >
> > Then:
> >
> > $$E[Y]=E[X^2].$$
> >
> > Using the function-of-$X$ formula:
> >
> > $$\begin{aligned}
> > E[X^2]
> > &=\sum_xx^2P(X=x)\\
> > &=1^2\left(\frac12\right)
> > +2^2\left(\frac12\right)\\
> > &=\frac12+2\\
> > &=\frac52.
> > \end{aligned}$$
> >
> > We did not need to first find the pmf of $Y$.
>
> > [!warning]- $E[g(X)]$ Is Not Generally $g(E[X])$
> >
> > In general:
> >
> > $$\boxed{
> > E[g(X)]\neq g(E[X]).
> > }$$
> >
> > For example, with $g(x)=x^2$:
> >
> > $$E[X^2]\neq(E[X])^2$$
> >
> > in general.
> >
> > This distinction becomes important later when studying **variance**:
> >
> > $$\operatorname{Var}(X)
> > =E[X^2]-(E[X])^2.
> > $$
>
> > [!important]- Why Absolute Convergence Matters
> >
> > For an infinite-support random variable, the expectation involves an infinite sum:
> >
> > $$E[X]=\sum_xxf_X(x).$$
> >
> > We require this sum to be **absolutely convergent**:
> >
> > $$\boxed{
> > \sum_x|x|f_X(x)<\infty.
> > }$$
> >
> > This guarantees that the expectation is well-defined and does not depend on how the terms are ordered.
> >
> > For finite-support random variables such as $\operatorname{Ber}(p)$ and $\operatorname{Bin}(n,p)$, this issue automatically causes no problem.
>
> > [!tip]- Important Formulas to Remember
> >
> > **Discrete expectation:**
> >
> > $$\boxed{
> > E[X]=\sum_xxf_X(x)
> > }$$
> >
> > **Indicator:**
> >
> > $$\boxed{
> > E[\mathbf1_A]=P(A)
> > }$$
> >
> > **Function of a random variable:**
> >
> > $$\boxed{
> > E[g(X)]
> > =
> > \sum_xg(x)f_X(x)
> > }$$
> >
> > The last formula is especially useful because it allows us to calculate the expectation of $g(X)$ **directly from the distribution of $X$**, without finding the distribution of $g(X)$.
>
> > [!important]- Big Picture
> >
> > The frequentist idea:
> >
> > $$\text{long-run average}
> > \approx
> > \sum_xx\frac{N(x)}N$$
> >
> > and
> >
> > $$\frac{N(x)}N\approx P(X=x).$$
> >
> > This leads naturally to:
> >
> > $$\boxed{
> > E[X]=\sum_xxP(X=x).
> > }$$
> >
> > More generally:
> >
> > $$\boxed{
> > E[g(X)]
> > =
> > \sum_xg(x)P(X=x).
> > }$$
> >
> > So expectation is fundamentally a **probability-weighted average of the values of a random variable**.

> [!important]- Linearity of Expectation
>
> > [!abstract]- Context
> >
> > Expectation behaves like a **linear operator**.
> >
> > This means that constants can be pulled outside the expectation and sums can be separated:
> >
> > $$\boxed{
> > E[aX+bY]
> > =
> > aE[X]+bE[Y].
> > }$$
> >
> > The important point is that **independence of $X$ and $Y$ is not required** for this result.
>
> > [!important]- Proposition
> >
> > If $X$ and $Y$ are discrete random variables and $a,b$ are constants, then
> >
> > $$\boxed{
> > E[aX+bY]
> > =
> > aE[X]+bE[Y].
> > }$$
> >
> > More generally:
> >
> > $$\boxed{
> > E\left[\sum_{i=1}^na_iX_i\right]
> > =
> > \sum_{i=1}^na_iE[X_i].
> > }$$
> >
> > This holds whether or not the random variables are independent.
>
> > [!abstract]- Derivation
> >
> > Recall the function-of-a-random-vector result:
> >
> > $$E[g(X,Y)]
> > =
> > \sum_{x,y}g(x,y)P(X=x,Y=y).$$
> >
> > Let
> >
> > $$A_x=\{X=x\},\qquad B_y=\{Y=y\}.$$
> >
> > Taking
> >
> > $$g(x,y)=ax+by,$$
> >
> > gives:
> >
> > $$E[aX+bY]
> > =
> > \sum_{x,y}(ax+by)P(A_x\cap B_y).$$
>
> > [!abstract]- Using the Partition of the Sample Space
> >
> > For a fixed $x$, the events
> >
> > $$\{B_y:y\text{ is a possible value of }Y\}$$
> >
> > form a countable partition of $\Omega$.
> >
> > Therefore:
> >
> > $$\sum_yP(A_x\cap B_y)=P(A_x).$$
> >
> > Similarly, for a fixed $y$:
> >
> > $$\sum_xP(A_x\cap B_y)=P(B_y).$$
> >
> > These identities allow us to separate the two parts of the expectation.
>
> > [!important]- Separating the Terms
> >
> > Start with:
> >
> > $$E[aX+bY]
> > =
> > \sum_{x,y}(ax+by)P(A_x\cap B_y).$$
> >
> > Split the sum:
> >
> > $$=
> > \sum_{x,y}axP(A_x\cap B_y)
> > +
> > \sum_{x,y}byP(A_x\cap B_y).$$
> >
> > Factor out terms that do not depend on the inner summation:
> >
> > $$=
> > \sum_xax\sum_yP(A_x\cap B_y)
> > +
> > \sum_yby\sum_xP(A_x\cap B_y).$$
> >
> > Using the partition identities:
> >
> > $$=
> > \sum_xaxP(A_x)
> > +
> > \sum_ybyP(B_y).$$
> >
> > Therefore:
> >
> > $$\boxed{
> > E[aX+bY]
> > =
> > aE[X]+bE[Y].
> > }$$
>
> > [!tip]- Why Independence Is Not Needed
> >
> > Notice that nowhere in the proof did we use
> >
> > $$P(A_x\cap B_y)=P(A_x)P(B_y).$$
> >
> > Therefore:
> >
> > $$\boxed{
> > \text{Linearity of expectation does not require independence.}
> > }$$
> >
> > Even if $X$ and $Y$ are strongly dependent:
> >
> > $$E[X+Y]=E[X]+E[Y].$$
>
> > [!example]- Dependent Variables
> >
> > Suppose
> >
> > $$Y=X.$$
> >
> > Then $X$ and $Y$ are obviously dependent.
> >
> > Nevertheless:
> >
> > $$E[X+Y]
> > =
> > E[2X]
> > =
> > 2E[X]
> > =
> > E[X]+E[Y].$$
> >
> > So linearity still works.
>
> > [!important]- What About $E[XY]$?
> >
> > A natural question is whether expectation also separates for products:
> >
> > $$\boxed{
> > E[XY]\stackrel{?}{=}E[X]E[Y].
> > }$$
> >
> > **Not in general.**
> >
> > Unlike linearity, this equality requires an additional condition: **independence**.
>
> > [!important]- Proposition: Product of Independent Variables
> >
> > If $X$ and $Y$ are independent, then
> >
> > $$\boxed{
> > E[XY]=E[X]E[Y].
> > }$$
> >
> > More generally, for suitable independent random variables:
> >
> > $$E\left[\prod_iX_i\right]
> > =
> > \prod_iE[X_i].$$
>
> > [!abstract]- Derivation
> >
> > By the function-of-a-random-vector formula:
> >
> > $$E[XY]
> > =
> > \sum_{x,y}xyP(A_x\cap B_y).$$
> >
> > If $X$ and $Y$ are independent:
> >
> > $$P(A_x\cap B_y)
> > =
> > P(A_x)P(B_y).$$
> >
> > Therefore:
> >
> > $$E[XY]
> > =
> > \sum_{x,y}xyP(A_x)P(B_y).$$
> >
> > Rearrange the double sum:
> >
> > $$E[XY]
> > =
> > \left(\sum_xxP(A_x)\right)
> > \left(\sum_yyP(B_y)\right).$$
> >
> > But:
> >
> > $$\sum_xxP(A_x)=E[X]$$
> >
> > and
> >
> > $$\sum_yyP(B_y)=E[Y].$$
> >
> > Hence:
> >
> > $$\boxed{
> > E[XY]=E[X]E[Y].
> > }$$
>
> > [!warning]- Important Distinction
> >
> > These two statements are very different:
> >
> > **Always true (under the usual integrability conditions):**
> >
> > $$\boxed{
> > E[X+Y]=E[X]+E[Y].
> > }$$
> >
> > No independence required.
> >
> > **Requires independence:**
> >
> > $$\boxed{
> > E[XY]=E[X]E[Y].
> > }$$
> >
> > In general:
> >
> > $$\boxed{
> > E[XY]\neq E[X]E[Y].
> > }$$
>
> > [!abstract]- Connection to Covariance
> >
> > The difference between these two quantities is captured by covariance:
> >
> > $$\boxed{
> > \operatorname{Cov}(X,Y)
> > =
> > E[XY]-E[X]E[Y].
> > }$$
> >
> > Therefore:
> >
> > $$E[XY]=E[X]E[Y]$$
> >
> > exactly when
> >
> > $$\operatorname{Cov}(X,Y)=0.$$
> >
> > Independence implies this equality, but the reverse implication generally does not hold.
>
> > [!important]- Big Picture
> >
> > **Addition:**
> >
> > $$\boxed{
> > E[aX+bY]=aE[X]+bE[Y]
> > }$$
> >
> > Independence **not required**.
> >
> > **Multiplication:**
> >
> > $$\boxed{
> > X\perp Y
> > \Rightarrow
> > E[XY]=E[X]E[Y]
> > }$$
> >
> > Independence **is sufficient**.
> >
> > The key distinction to remember:
> >
> > $$\boxed{
> > \text{Expectation is always linear, but not generally multiplicative.}
> > }$$

---

> [!important]- Variance and Moments
>
> > [!abstract]- Context: Why Study $E[g(X)]$?
> >
> > Expectation can be applied not only to $X$, but to functions of $X$:
> >
> > $$E[g(X)].$$
> >
> > Some choices of $g$ are particularly important because they describe different properties of the distribution.
> >
> > The most important choices are:
> >
> > $$g(X)=X,\quad X^2,\quad X^3,\ldots$$
> >
> > and
> >
> > $$g(X)=(X-E[X])^2.$$
> >
> > These lead to **moments** and **variance**.
>
> > [!important]- $k$th Moment
> >
> > The **$k$th moment** of a discrete random variable $X$ is defined as
> >
> > $$\boxed{
> > m_k=E[X^k]
> > }$$
> >
> > Therefore:
> >
> > $$\boxed{
> > m_k
> > =
> > \sum_{x:f_X(x)>0}x^k f_X(x)
> > }$$
> >
> > The first few moments are:
> >
> > $$m_1=E[X]$$
> >
> > $$m_2=E[X^2]$$
> >
> > $$m_3=E[X^3]$$
> >
> > $$\vdots$$
> >
> > In particular:
> >
> > $$\boxed{m_1=E[X]}$$
> >
> > is the **mean** of $X$.
>
> > [!abstract]- Why Are Moments Useful?
> >
> > Different moments describe different aspects of a distribution.
> >
> > $$E[X]$$ describes its location/center.
> >
> > $$E[X^2]$$ helps quantify the magnitude of values and is used to calculate variance.
> >
> > Higher moments such as $E[X^3]$ and $E[X^4]$ are used to study properties such as skewness and kurtosis.
>
> > [!important]- Variance
> >
> > The mean of $X$ is
> >
> > $$m_1=E[X].$$
> >
> > To measure how much $X$ varies around its mean, consider the deviation:
> >
> > $$X-E[X].$$
> >
> > We square the deviation so that positive and negative deviations do not cancel:
> >
> > $$\boxed{
> > \operatorname{Var}(X)
> > =
> > E[(X-E[X])^2].
> > }$$
> >
> > This is called the **variance** of $X$.
>
> > [!abstract]- Why Square the Deviation?
> >
> > If we simply used
> >
> > $$E[X-E[X]],$$
> >
> > we would always get zero:
> >
> > $$E[X-E[X]]
> > =
> > E[X]-E[X]
> > =0.$$
> >
> > So the ordinary deviations cancel each other.
> >
> > Squaring gives:
> >
> > $$$(X-E[X])^2\geq0,$$
> >
> > allowing us to measure the magnitude of deviations from the mean.
>
> > [!important]- Variance in Terms of Moments
> >
> > Starting from:
> >
> > $$\operatorname{Var}(X)
> > =
> > E[(X-E[X])^2],$$
> >
> > expand the square:
> >
> > $$\begin{aligned}
> > \operatorname{Var}(X)
> > &=E[X^2-2XE[X]+(E[X])^2].
> > \end{aligned}$$
> >
> > Since $E[X]$ is a constant:
> >
> > $$\begin{aligned}
> > \operatorname{Var}(X)
> > &=E[X^2]-2E[X]E[X]+(E[X])^2\\
> > &=E[X^2]-(E[X])^2.
> > \end{aligned}$$
> >
> > Therefore:
> >
> > $$\boxed{
> > \operatorname{Var}(X)
> > =
> > E[X^2]-(E[X])^2
> > }$$
> >
> > Since
> >
> > $$m_1=E[X],\qquad m_2=E[X^2],$$
> >
> > we can also write:
> >
> > $$\boxed{
> > \operatorname{Var}(X)=m_2-m_1^2.
> > }$$
>
> > [!important]- Non-Negativity of Variance
> >
> > Since
> >
> > $$(X-E[X])^2\geq0$$
> >
> > for every outcome, its expectation must also be nonnegative:
> >
> > $$\boxed{
> > \operatorname{Var}(X)\geq0.
> > }$$
> >
> > Therefore:
> >
> > $$\boxed{
> > E[X^2]\geq(E[X])^2.
> > }$$
> >
> > This is an important inequality that follows directly from the definition of variance.
>
> > [!abstract]- Centered Moments
> >
> > Ordinary moments use powers of $X$:
> >
> > $$E[X^k].$$
> >
> > **Centered moments** instead measure powers of the deviation from the mean.
> >
> > The $k$th centered moment is:
> >
> > $$\boxed{
> > \sigma_k
> > =
> > E[(X-m_1)^k]
> > }$$
> >
> > where
> >
> > $$m_1=E[X].$$
> >
> > For $k=2$:
> >
> > $$\sigma_2
> > =
> > E[(X-E[X])^2]
> > =
> > \operatorname{Var}(X).$$
> >
> > Hence:
> >
> > $$\boxed{
> > \operatorname{Var}(X)=\sigma_2.
> > }$$
>
> > [!important]- Standard Deviation
> >
> > Variance is measured in **squared units**.
> >
> > To return to the original units of $X$, take the positive square root:
> >
> > $$\boxed{
> > \sigma=\sqrt{\operatorname{Var}(X)}
> > }$$
> >
> > This is called the **standard deviation**.
> >
> > Therefore:
> >
> > $$\boxed{
> > \sigma^2=\operatorname{Var}(X)
> > }$$
> >
> > and
> >
> > $$\boxed{
> > \sigma=\sqrt{\operatorname{Var}(X)}.
> > }$$
>
> > [!abstract]- Interpretation of Standard Deviation
> >
> > Variance measures the average **squared** distance from the mean:
> >
> > $$\operatorname{Var}(X)=E[(X-E[X])^2].$$
> >
> > Standard deviation converts this back to the original scale:
> >
> > $$\sigma=\sqrt{E[(X-E[X])^2]}.$$
> >
> > Thus, standard deviation gives a measure of the typical spread of $X$ around its mean.
>
> > [!important]- Example: Binomial Random Variable
> >
> > Let
> >
> > $$X\sim\operatorname{Bin}(n,p).$$
> >
> > Its pmf is:
> >
> > $$P(X=k)=\binom nkp^kq^{n-k},\qquad q=1-p.$$
> >
> > Therefore:
> >
> > $$E[X]
> > =
> > \sum_{k=0}^n
> > k\binom nkp^kq^{n-k}.$$
>
> > [!abstract]- Computing $E[X]$ for Binomial
> >
> > Start with the binomial identity:
> >
> > $$\boxed{
> > \sum_{k=0}^n\binom nkx^k=(1+x)^n.
> > }$$
> >
> > Differentiate both sides:
> >
> > $$\sum_{k=0}^n
> > k\binom nkx^{k-1}
> > =
> > n(1+x)^{n-1}.$$
> >
> > Multiply by $x$:
> >
> > $$\sum_{k=0}^n
> > k\binom nkx^k
> > =
> > nx(1+x)^{n-1}.$$
> >
> > Set
> >
> > $$x=\frac pq.$$
> >
> > Then:
> >
> > $$1+\frac pq
> > =\frac{p+q}{q}
> > =\frac1q.$$
> >
> > Hence:
> >
> > $$\sum_{k=0}^n
> > k\binom nk
> > \left(\frac pq\right)^k
> > =
> > n\frac pq
> > \left(\frac1q\right)^{n-1}.$$
> >
> > Multiplying by $q^n$ gives:
> >
> > $$\sum_{k=0}^n
> > k\binom nkp^kq^{n-k}
> > =np.$$
> >
> > Therefore:
> >
> > $$\boxed{
> > E[X]=np.
> > }$$
>
> > [!important]- Variance of a Binomial Random Variable
> >
> > For
> >
> > $$X\sim\operatorname{Bin}(n,p),$$
> >
> > the variance is:
> >
> > $$\boxed{
> > \operatorname{Var}(X)=npq
> > }$$
> >
> > where
> >
> > $$q=1-p.$$
> >
> > Thus:
> >
> > $$\boxed{
> > E[X]=np,\qquad
> > \operatorname{Var}(X)=np(1-p).
> > }$$
>
> > [!abstract]- Binomial as a Sum of Bernoulli Variables
> >
> > A binomial random variable can be written as:
> >
> > $$\boxed{
> > X=X_1+\cdots+X_n
> > }$$
> >
> > where
> >
> > $$X_i\overset{\text{i.i.d.}}{\sim}\operatorname{Ber}(p).$$
> >
> > Each $X_i$ indicates whether trial $i$ is a success:
> >
> > $$X_i=
> > \begin{cases}
> > 1,&\text{success},\\
> > 0,&\text{failure}.
> > \end{cases}$$
> >
> > Therefore, the total number of successes is their sum.
>
> > [!important]- Expectation of the Binomial via Linearity
> >
> > Since
> >
> > $$X=\sum_{i=1}^nX_i,$$
> >
> > linearity of expectation gives:
> >
> > $$E[X]
> > =
> > E\left[\sum_{i=1}^nX_i\right]
> > =
> > \sum_{i=1}^nE[X_i].$$
> >
> > For each Bernoulli variable:
> >
> > $$E[X_i]=p.$$
> >
> > Therefore:
> >
> > $$E[X]
> > =
> > \sum_{i=1}^np
> > =np.$$
> >
> > Hence:
> >
> > $$\boxed{
> > E[X]=np.
> > }$$
> >
> > This gives a much simpler way to derive the mean than directly summing the binomial pmf.
>
> > [!abstract]- Variance via Independent Bernoulli Trials
> >
> > Since the $X_i$ are independent:
> >
> > $$\operatorname{Var}\left(\sum_{i=1}^nX_i\right)
> > =
> > \sum_{i=1}^n\operatorname{Var}(X_i).$$
> >
> > For a Bernoulli variable:
> >
> > $$\operatorname{Var}(X_i)=p(1-p)=pq.$$
> >
> > Therefore:
> >
> > $$\operatorname{Var}(X)
> > =
> > \sum_{i=1}^npq
> > =npq.$$
> >
> > Thus:
> >
> > $$\boxed{
> > \operatorname{Var}(X)=npq.
> > }$$
>
> > [!tip]- Key Formulas
> >
> > **$k$th moment:**
> >
> > $$\boxed{
> > m_k=E[X^k]
> > }$$
> >
> > **$k$th centered moment:**
> >
> > $$\boxed{
> > \sigma_k=E[(X-E[X])^k]
> > }$$
> >
> > **Variance:**
> >
> > $$\boxed{
> > \operatorname{Var}(X)
> > =E[(X-E[X])^2]
> > =E[X^2]-(E[X])^2
> > }$$
> >
> > **Standard deviation:**
> >
> > $$\boxed{
> > \sigma=\sqrt{\operatorname{Var}(X)}
> > }$$
> >
> > **Binomial:**
> >
> > $$\boxed{
> > X\sim\operatorname{Bin}(n,p)
> > \Rightarrow
> > E[X]=np,\quad
> > \operatorname{Var}(X)=np(1-p).
> > }$$
>
> > [!important]- Big Picture
> >
> > $$\boxed{
> > \text{Moments}
> > \longrightarrow
> > \text{describe the distribution}
> > }$$
> >
> > The first moment gives the center:
> >
> > $$m_1=E[X].$$
> >
> > The second centered moment gives the spread:
> >
> > $$\sigma_2=\operatorname{Var}(X).$$
> >
> > Its square root gives the standard deviation:
> >
> > $$\sigma=\sqrt{\operatorname{Var}(X)}.$$
> >
> > For a binomial random variable:
> >
> > $$\boxed{
> > \text{mean}=np,\qquad
> > \text{variance}=np(1-p).
> > }$$

> [!important]- Properties of Variance
> > [!abstract]- Main Idea
> > We know that expectation is linear:
> >
> > $$E[aX+bY]=aE[X]+bE[Y]$$
> >
> > Variance is **not linear**. Instead, it has specific scaling and addition properties.
>
> > [!important]- Scaling Property
> > For any constant $a$:
> >
> > $$\boxed{\operatorname{Var}(aX)=a^2\operatorname{Var}(X)}$$
> >
> > The square appears because variance measures **squared deviations from the mean**.
>
> > [!abstract]- Derivation
> > Start with:
> >
> > $$\operatorname{Var}(aX)=E[(aX-E[aX])^2]$$
> >
> > By linearity of expectation:
> >
> > $$E[aX]=aE[X]$$
> >
> > Therefore:
> >
> > $$\begin{aligned}
> > \operatorname{Var}(aX)
> > &=E[(aX-aE[X])^2]\\
> > &=E[a^2(X-E[X])^2]\\
> > &=a^2E[(X-E[X])^2]\\
> > &=\boxed{a^2\operatorname{Var}(X)}
> > \end{aligned}$$
>
> > [!tip]- Intuition
> > If we multiply every value of $X$ by $a$, every deviation from the mean is also multiplied by $a$.
> >
> > Since variance squares the deviation, the variance gets multiplied by $a^2$.
> >
> > For example:
> >
> > $$\operatorname{Var}(2X)=4\operatorname{Var}(X)$$
> >
> > $$\operatorname{Var}(-3X)=9\operatorname{Var}(X)$$
>
> > [!important]- Variance of a Sum
> > In general:
> >
> > $$\boxed{
> > \operatorname{Var}(X+Y)
> > =
> > \operatorname{Var}(X)
> > +
> > \operatorname{Var}(Y)
> > +
> > 2\operatorname{Cov}(X,Y)
> > }$$
> >
> > Therefore, if $X$ and $Y$ are **uncorrelated**:
> >
> > $$\operatorname{Cov}(X,Y)=0$$
> >
> > and hence:
> >
> > $$\boxed{
> > \operatorname{Var}(X+Y)
> > =
> > \operatorname{Var}(X)+\operatorname{Var}(Y)
> > }$$
>
> > [!abstract]- Derivation
> > Using:
> >
> > $$\operatorname{Var}(Z)=E[Z^2]-(E[Z])^2$$
> >
> > with $Z=X+Y$:
> >
> > $$\begin{aligned}
> > \operatorname{Var}(X+Y)
> > &=E[(X+Y)^2]-(E[X+Y])^2\\
> > &=E[X^2+2XY+Y^2]-(E[X]+E[Y])^2\\
> > &=E[X^2]+2E[XY]+E[Y^2]\\
> > &\quad-E[X]^2-2E[X]E[Y]-E[Y]^2\\
> > &=\big(E[X^2]-E[X]^2\big)
> > +\big(E[Y^2]-E[Y]^2\big)\\
> > &\quad+2\big(E[XY]-E[X]E[Y]\big)\\
> > &=\operatorname{Var}(X)+\operatorname{Var}(Y)
> > +2\operatorname{Cov}(X,Y)
> > \end{aligned}$$
>
> > [!warning]- Independence vs Uncorrelatedness
> > Independence implies uncorrelatedness:
> >
> > $$X\perp Y
> > \Rightarrow
> > \operatorname{Cov}(X,Y)=0$$
> >
> > Therefore, independence is sufficient for:
> >
> > $$\operatorname{Var}(X+Y)
> > =
> > \operatorname{Var}(X)+\operatorname{Var}(Y)$$
> >
> > But independence is **not necessary**. It is enough that:
> >
> > $$\operatorname{Cov}(X,Y)=0$$
>
> > [!tip]- Compare with Expectation
> > **Expectation:**
> >
> > $$E[X+Y]=E[X]+E[Y]$$
> >
> > No independence or uncorrelatedness is required.
> >
> > **Variance:**
> >
> > $$\operatorname{Var}(X+Y)
> > =\operatorname{Var}(X)+\operatorname{Var}(Y)
> > +2\operatorname{Cov}(X,Y)$$
> >
> > The covariance term matters.
> >
> > Therefore:
> >
> > $$\boxed{\text{Expectation is linear, variance is not.}}$$
>
> > [!important]- Key Formulas
> > $$\boxed{\operatorname{Var}(aX)=a^2\operatorname{Var}(X)}$$
> >
> > $$\boxed{
> > \operatorname{Var}(X+Y)
> > =
> > \operatorname{Var}(X)+\operatorname{Var}(Y)
> > +2\operatorname{Cov}(X,Y)
> > }$$
> >
> > If $X,Y$ are uncorrelated:
> >
> > $$\boxed{
> > \operatorname{Var}(X+Y)
> > =
> > \operatorname{Var}(X)+\operatorname{Var}(Y)
> > }$$

> [!important]- Covariance
> > [!abstract]- Definition
> > Covariance measures how two random variables vary **together**.
> >
> > For random variables $X$ and $Y$:
> >
> > $$\boxed{\operatorname{Cov}(X,Y)=E[(X-E[X])(Y-E[Y])]}$$
> >
> > It measures the direction of their linear relationship.
>
> > [!abstract]- Simplified Formula
> > Expand:
> >
> > $$\begin{aligned}
> > \operatorname{Cov}(X,Y)
> > &=E[(X-E[X])(Y-E[Y])]\\
> > &=E[XY-XE[Y]-E[X]Y+E[X]E[Y]]\\
> > &=E[XY]-E[X]E[Y].
> > \end{aligned}$$
> >
> > Therefore:
> >
> > $$\boxed{\operatorname{Cov}(X,Y)=E[XY]-E[X]E[Y]}$$
>
> > [!tip]- Intuition
> > Think about whether $X$ and $Y$ tend to be **above or below their respective means at the same time**.
> >
> > Define deviations from the mean:
> >
> > $$X-E[X],\qquad Y-E[Y]$$
> >
> > Then:
> >
> > - Both deviations positive $\Rightarrow$ product positive
> > - Both deviations negative $\Rightarrow$ product positive
> > - One positive and one negative $\Rightarrow$ product negative
> >
> > Covariance averages these products.
> >
> > So:
> >
> > $$\boxed{\text{positive covariance}\Rightarrow\text{tend to move together}}$$
> >
> > $$\boxed{\text{negative covariance}\Rightarrow\text{tend to move oppositely}}$$
> >
> > $$\boxed{\text{zero covariance}\Rightarrow\text{no linear relationship detected}}$$
>
> > [!abstract]- Uncorrelated Random Variables
> > $X$ and $Y$ are called **uncorrelated** if:
> >
> > $$\boxed{\operatorname{Cov}(X,Y)=0}$$
> >
> > Equivalently:
> >
> > $$\boxed{E[XY]=E[X]E[Y]}$$
> >
> > **Important:** Uncorrelated does not necessarily mean independent.
>
> > [!important]- Independence Implies Uncorrelatedness
> > If $X$ and $Y$ are independent, then:
> >
> > $$E[XY]=E[X]E[Y]$$
> >
> > Therefore:
> >
> > $$\operatorname{Cov}(X,Y)
> > =E[XY]-E[X]E[Y]
> > =0$$
> >
> > Hence:
> >
> > $$\boxed{X\perp Y\Rightarrow\operatorname{Cov}(X,Y)=0}$$
> >
> > So:
> >
> > $$\boxed{\text{Independent}\Rightarrow\text{Uncorrelated}}$$
>
> > [!warning]- Converse Is False
> > In general:
> >
> > $$\boxed{\operatorname{Cov}(X,Y)=0\not\Rightarrow X\perp Y}$$
> >
> > Zero covariance only tells us that there is **no linear dependence** between $X$ and $Y$.
> >
> > They may still have a nonlinear dependence.
>
> > [!example]- Example: Uncorrelated but Dependent
> > Let $X$ take values $-1$ and $1$ with equal probability, and let:
> >
> > $$Y=X^2$$
> >
> > Then:
> >
> > $$Y=1$$
> >
> > always. Thus, $Y$ is completely determined by $X$, so $X$ and $Y$ are **not independent**.
> >
> > But:
> >
> > $$E[X]=0,\qquad E[Y]=1$$
> >
> > and:
> >
> > $$E[XY]=E[X^3]=0$$
> >
> > Therefore:
> >
> > $$\begin{aligned}
> > \operatorname{Cov}(X,Y)
> > &=E[XY]-E[X]E[Y]\\
> > &=0-(0)(1)\\
> > &=0
> > \end{aligned}$$
> >
> > Thus:
> >
> > $$\boxed{\text{uncorrelated but dependent}}$$
>
> > [!important]- Key Relationship
> > $$\boxed{
> > \text{Independence}
> > \Longrightarrow
> > \text{Uncorrelatedness}
> > }$$
> >
> > but:
> >
> > $$\boxed{
> > \text{Uncorrelatedness}
> > \not\Longrightarrow
> > \text{Independence}
> > }$$
> >
> > **Think:** Independence is much stronger.
> >
> > Independence rules out *all kinds* of dependence, whereas zero covariance rules out only **linear dependence**.






