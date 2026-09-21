
> [!important]- Conditional Distributions and Conditional Expectation
> > [!abstract]- From Conditional Probability to Conditional Distribution
> > Recall that for events $A$ and $B$, with $P(B)>0$:
> >
> > $$\boxed{P(A\mid B)=\frac{P(A\cap B)}{P(B)}}$$
> >
> > For random variables $X$ and $Y$, we can similarly ask:
> >
> > **What is the distribution of $Y$ when we know that $X=x$?**
> >
> > This leads to the concept of a **conditional distribution**.
>
> > [!abstract]- Conditional Distribution Function
> > For random variables $X$ and $Y$, and for $x$ such that $P(X=x)>0$, define the conditional CDF of $Y$ given $X=x$ as:
> >
> > $$\boxed{
> > F_{Y\mid X}(y\mid x)
> > =
> > P(Y\le y\mid X=x)
> > }$$
> >
> > It describes the distribution of $Y$ after we know that $X=x$.
>
> > [!abstract]- Conditional PMF
> > For discrete random variables, the conditional pmf of $Y$ given $X=x$ is:
> >
> > $$\boxed{
> > f_{Y\mid X}(y\mid x)
> > =
> > P(Y=y\mid X=x)
> > }$$
> >
> > Using the definition of conditional probability:
> >
> > $$\begin{aligned}
> > f_{Y\mid X}(y\mid x)
> > &=\frac{P(Y=y,X=x)}{P(X=x)}\\
> > &=\boxed{\frac{f_{X,Y}(x,y)}{f_X(x)}}
> > \end{aligned}$$
> >
> > where $f_X(x)>0$.
>
> > [!tip]- Intuition
> > The joint pmf $f_{X,Y}(x,y)$ tells us the probability of **both** $X=x$ and $Y=y$.
> >
> > The conditional pmf asks:
> >
> > **Among the outcomes where $X=x$, how is the probability distributed among the possible values of $Y$?**
> >
> > Therefore:
> >
> > $$\boxed{
> > \text{Conditional distribution}
> > =
> > \frac{\text{joint distribution}}{\text{distribution of the condition}}
> > }$$
>
> > [!important]- Conditional Distribution and Independence
> > $X$ and $Y$ are independent if and only if knowing $X=x$ does not change the distribution of $Y$.
> >
> > Therefore:
> >
> > $$\boxed{
> > X\perp Y
> > \iff
> > f_{Y\mid X}(y\mid x)=f_Y(y)
> > }$$
> >
> > for every $x$ with $P(X=x)>0$ and every $y$.
> >
> > In words:
> >
> > $$\boxed{
> > \text{Independent}
> > \iff
> > \text{conditioning on }X\text{ does not change the distribution of }Y
> > }$$
>
> > [!abstract]- Conditional Expectation
> > For a fixed $x$, $f_{Y\mid X}(\cdot\mid x)$ is itself a pmf.
> >
> > Therefore, we can calculate its mean.
> >
> > The **conditional expectation of $Y$ given $X=x$** is:
> >
> > $$\boxed{
> > E[Y\mid X=x]
> > =
> > \sum_y y f_{Y\mid X}(y\mid x)
> > }$$
> >
> > It is simply the expected value of $Y$ under the conditional distribution of $Y$ given $X=x$.
>
> > [!tip]- Intuition
> > Ordinary expectation:
> >
> > $$E[Y]$$
> >
> > asks:
> >
> > **What is the average value of $Y$ before knowing anything about $X$?**
> >
> > Conditional expectation:
> >
> > $$E[Y\mid X=x]$$
> >
> > asks:
> >
> > **What is the average value of $Y$ after learning that $X=x$?**
> >
> > Therefore, conditioning can change the expected value.
>
> > [!important]- Conditional Expectation as a Random Variable
> > For each possible value $x$, we obtain a number:
> >
> > $$E[Y\mid X=x]$$
> >
> > Since this number depends on $x$, we can view it as a function of $X$.
> >
> > Thus:
> >
> > $$\boxed{E[Y\mid X]}$$
> >
> > is itself a **random variable**.
> >
> > More precisely:
> >
> > $$E[Y\mid X]
> > =
> > g(X)$$
> >
> > where
> >
> > $$g(x)=E[Y\mid X=x].$$
>
> > [!abstract]- Law of Iterated Expectations
> > The conditional expectation satisfies:
> >
> > $$\boxed{
> > E[E[Y\mid X]]=E[Y]
> > }$$
> >
> > This is called the **law of iterated expectations** or the **tower property**.
> >
> > Intuitively:
> >
> > **First average $Y$ within each value of $X$, then average those conditional averages over $X$.**
> >
> > You recover the original overall average.
>
> > [!abstract]- Derivation
> > Start with the expectation of the random variable $E[Y\mid X]$:
> >
> > $$E[E[Y\mid X]]
> > =
> > \sum_x E[Y\mid X=x]f_X(x)$$
> >
> > Substitute the definition of conditional expectation:
> >
> > $$=
> > \sum_x
> > \left(
> > \sum_y y f_{Y\mid X}(y\mid x)
> > \right)f_X(x)$$
> >
> > Rearrange:
> >
> > $$=
> > \sum_x\sum_y
> > y f_{Y\mid X}(y\mid x)f_X(x)$$
> >
> > Since:
> >
> > $$f_{Y\mid X}(y\mid x)f_X(x)
> > =
> > f_{X,Y}(x,y)$$
> >
> > we get:
> >
> > $$=
> > \sum_x\sum_y
> > y f_{X,Y}(x,y)$$
> >
> > Rearrange the sums:
> >
> > $$=
> > \sum_y y
> > \sum_x f_{X,Y}(x,y)$$
> >
> > Since:
> >
> > $$\sum_x f_{X,Y}(x,y)=f_Y(y)$$
> >
> > therefore:
> >
> > $$\begin{aligned}
> > E[E[Y\mid X]]
> > &=\sum_y y f_Y(y)\\
> > &=E[Y].
> > \end{aligned}$$
> >
> > Hence:
> >
> > $$\boxed{E[E[Y\mid X]]=E[Y]}$$
>
> > [!example]- Example: Poisson Number of Coin Tosses
> > A coin is tossed $N$ times, where:
> >
> > $$N\sim\operatorname{Poi}(\lambda)$$
> >
> > Let $X$ denote the number of heads, with:
> >
> > $$P(\text{Head})=p.$$
> >
> > **Goal:** Compute $E[X]$.
>
> > [!abstract]- Step 1: Condition on $N=n$
> > Given $N=n$, exactly $n$ tosses are performed.
> >
> > Therefore:
> >
> > $$X\mid N=n\sim\operatorname{Bin}(n,p)$$
> >
> > Its conditional pmf is:
> >
> > $$\boxed{
> > f_{X\mid N}(x\mid n)
> > =
> > \binom nx p^x(1-p)^{n-x}
> > }$$
> >
> > for $x=0,1,\ldots,n$.
>
> > [!abstract]- Step 2: Conditional Expectation
> > Since:
> >
> > $$X\mid N=n\sim\operatorname{Bin}(n,p)$$
> >
> > and the mean of a binomial random variable is $np$:
> >
> > $$\boxed{
> > E[X\mid N=n]=np
> > }$$
> >
> > Therefore, as a random variable:
> >
> > $$\boxed{
> > E[X\mid N]=Np
> > }$$
>
> > [!abstract]- Step 3: Apply the Tower Property
> > Using:
> >
> > $$E[X]=E[E[X\mid N]]$$
> >
> > we obtain:
> >
> > $$\begin{aligned}
> > E[X]
> > &=E[Np]\\
> > &=pE[N]\\
> > &=p\lambda.
> > \end{aligned}$$
> >
> > Therefore:
> >
> > $$\boxed{E[X]=\lambda p}$$
>
> > [!tip]- Intuition of the Example
> > The number of tosses $N$ is random.
> >
> > But once we know $N=n$, the problem becomes an ordinary binomial problem:
> >
> > $$E[X\mid N=n]=np.$$
> >
> > Then we average these conditional means over the randomness of $N$:
> >
> > $$E[X]=E[Np]=pE[N]=\lambda p.$$
> >
> > This illustrates the general principle:
> >
> > $$\boxed{
> > \text{Overall average}
> > =
> > \text{average of conditional averages}
> > }$$
>
> > [!important]- Key Formulas
> > Conditional pmf:
> >
> > $$\boxed{
> > f_{Y\mid X}(y\mid x)
> > =
> > \frac{f_{X,Y}(x,y)}{f_X(x)}
> > }$$
> >
> > Conditional expectation:
> >
> > $$\boxed{
> > E[Y\mid X=x]
> > =
> > \sum_y y f_{Y\mid X}(y\mid x)
> > }$$
> >
> > Tower property:
> >
> > $$\boxed{
> > E[E[Y\mid X]]=E[Y]
> > }$$
> >
> > Independence:
> >
> > $$\boxed{
> > X\perp Y
> > \iff
> > f_{Y\mid X}(y\mid x)=f_Y(y)
> > }$$
>
> > [!warning]- Exercise
> > For the Poisson coin-toss model above, compute:
> >
> > $$\boxed{E[N\mid X]}$$
> >
> > This is different from $E[X\mid N]$ because now we are asking:
> >
> > **Given the observed number of heads $X$, what is the expected total number of tosses $N$?**

> [!important]- Sums of Random Variables
> > [!abstract]- Main Idea
> > Suppose $X$ and $Y$ are discrete random variables and define:
> >
> > $$Z=X+Y$$
> >
> > We want to find the pmf of $Z$:
> >
> > $$P(Z=z)=P(X+Y=z).$$
> >
> > The key idea is to consider **all possible pairs $(x,y)$ whose sum is $z$**.
>
> > [!abstract]- Distribution of $X+Y$
> > We have:
> >
> > $$\boxed{
> > P(X+Y=z)
> > =
> > \sum_x f_{X,Y}(x,z-x)
> > }$$
> >
> > Why?
> >
> > The event $\{X+Y=z\}$ can be written as:
> >
> > $$\{X+Y=z\}
> > =
> > \bigcup_{x:f_X(x)>0}
> > \left(\{X=x\}\cap\{Y=z-x\}\right).$$
> >
> > These events are **disjoint** because $X$ cannot simultaneously take two different values.
> >
> > Therefore, by countable additivity:
> >
> > $$\begin{aligned}
> > P(X+Y=z)
> > &=\sum_xP(X=x,Y=z-x)\\
> > &=\sum_xf_{X,Y}(x,z-x).
> > \end{aligned}$$
>
> > [!tip]- Intuition
> > To get a total of $z$, $X$ and $Y$ can take combinations such as:
> >
> > $$X=0,\ Y=z$$
> >
> > $$X=1,\ Y=z-1$$
> >
> > $$X=2,\ Y=z-2$$
> >
> > and so on.
> >
> > We add the probabilities of **all possible combinations that produce the sum $z$**.
>
> > [!important]- Independent Random Variables
> > If $X$ and $Y$ are independent:
> >
> > $$f_{X,Y}(x,y)=f_X(x)f_Y(y).$$
> >
> > Therefore:
> >
> > $$\begin{aligned}
> > P(X+Y=z)
> > &=\sum_xf_{X,Y}(x,z-x)\\
> > &=\sum_xf_X(x)f_Y(z-x).
> > \end{aligned}$$
> >
> > This is called the **convolution** of $f_X$ and $f_Y$.
> >
> > $$\boxed{
> > f_{X+Y}(z)
> > =
> > \sum_xf_X(x)f_Y(z-x)
> > }$$
> >
> > or:
> >
> > $$\boxed{f_{X+Y}=f_X*f_Y}$$
>
> > [!abstract]- Convolution
> > The convolution of two discrete pmfs $f_X$ and $f_Y$ is:
> >
> > $$\boxed{
> > (f_X*f_Y)(z)
> > =
> > \sum_xf_X(x)f_Y(z-x)
> > }$$
> >
> > Thus, when $X$ and $Y$ are independent:
> >
> > $$\boxed{
> > f_{X+Y}=f_X*f_Y
> > }$$
> >
> > **Important:** The convolution formula directly applies in this simple form when $X$ and $Y$ are independent.
>
> > [!example]- Example: Tosses Until the Second Head
> > Keep tossing a biased coin with:
> >
> > $$P(H)=p,\qquad P(T)=1-p.$$
> >
> > Let $Z$ be the toss number at which the **second Head** appears.
> >
> > Define:
> >
> > $$X_1=\text{number of tosses until the first Head}$$
> >
> > $$X_2=\text{number of tosses from the first Head until the second Head}$$
> >
> > Then:
> >
> > $$\boxed{Z=X_1+X_2}$$
> >
> > Each $X_i$ has a geometric distribution:
> >
> > $$X_1,X_2\overset{\text{i.i.d.}}{\sim}\operatorname{Geom}(p)$$
> >
> > with pmf:
> >
> > $$\boxed{
> > f(k)=(1-p)^{k-1}p,\qquad k=1,2,\ldots
> > }$$
>
> > [!abstract]- Finding $P(Z=z)$
> > Since $Z=X_1+X_2$ and $X_1,X_2$ are independent:
> >
> > $$P(Z=z)
> > =
> > \sum_{k=1}^{z-1}
> > P(X_1=k)P(X_2=z-k).$$
> >
> > Substitute the geometric pmf:
> >
> > $$\begin{aligned}
> > P(Z=z)
> > &=\sum_{k=1}^{z-1}
> > p(1-p)^{k-1}
> > \cdot
> > p(1-p)^{z-k-1}\\
> > &=\sum_{k=1}^{z-1}
> > p^2(1-p)^{z-2}.
> > \end{aligned}$$
> >
> > The term is independent of $k$, and there are $z-1$ possible values of $k$.
> >
> > Therefore:
> >
> > $$\boxed{
> > P(Z=z)
> > =(z-1)p^2(1-p)^{z-2},
> > \qquad z\ge2
> > }$$
>
> > [!tip]- Why Are There $z-1$ Terms?
> > To have the second Head on toss $z$, the first Head can occur on any toss:
> >
> > $$1,2,\ldots,z-1.$$
> >
> > For example, if $z=5$:
> >
> > $$X_1=1,\ X_2=4$$
> >
> > $$X_1=2,\ X_2=3$$
> >
> > $$X_1=3,\ X_2=2$$
> >
> > $$X_1=4,\ X_2=1$$
> >
> > So there are:
> >
> > $$z-1$$
> >
> > possible decompositions.
>
> > [!important]- Generalization: $r$-th Head
> > Suppose:
> >
> > $$Z=X_1+\cdots+X_r$$
> >
> > where $X_1,\ldots,X_r$ are independent $\operatorname{Geom}(p)$ random variables.
> >
> > Then $Z$ represents the toss number on which the **$r$-th Head** occurs.
> >
> > Its pmf is:
> >
> > $$\boxed{
> > P(Z=z)
> > =
> > \binom{z-1}{r-1}
> > p^r(1-p)^{z-r},
> > \qquad z\ge r
> > }$$
> >
> > This is the **negative binomial distribution** with parameters $p$ and $r$.
>
> > [!tip]- Why the Binomial Coefficient?
> > For the $r$-th Head to occur on toss $z$:
> >
> > - Toss $z$ must be a Head.
> > - Among the first $z-1$ tosses, exactly $r-1$ must be Heads.
> > - The remaining $z-r$ tosses must be Tails.
> >
> > The number of ways to choose the $r-1$ Heads among the first $z-1$ positions is:
> >
> > $$\binom{z-1}{r-1}.$$
> >
> > Each such sequence has probability:
> >
> > $$p^r(1-p)^{z-r}.$$
> >
> > Hence:
> >
> > $$P(Z=z)
> > =
> > \binom{z-1}{r-1}
> > p^r(1-p)^{z-r}.$$
>
> > [!important]- Key Formulas
> > For arbitrary discrete $X,Y$:
> >
> > $$\boxed{
> > P(X+Y=z)
> > =
> > \sum_xf_{X,Y}(x,z-x)
> > }$$
> >
> > If $X,Y$ are independent:
> >
> > $$\boxed{
> > f_{X+Y}(z)
> > =
> > \sum_xf_X(x)f_Y(z-x)
> > =
> > (f_X*f_Y)(z)
> > }$$
> >
> > For the $r$-th success in Bernoulli trials:
> >
> > $$\boxed{
> > P(Z=z)
> > =
> > \binom{z-1}{r-1}
> > p^r(1-p)^{z-r},
> > \qquad z\ge r
> > }$$

> [!important]- Continuous Random Variables
> > [!abstract]- Definition
> > A random variable $X$ is called a **continuous random variable** if its CDF can be written as:
> >
> > $$\boxed{
> > F_X(x)=\int_{-\infty}^{x}f_X(y)\,dy
> > }$$
> >
> > where $f_X$ is called the **probability density function (pdf)** of $X$.
> >
> > Unlike a discrete random variable, a continuous random variable does not assign positive probability to individual points.
>
> > [!abstract]- PDF from the CDF
> > If $F_X$ is differentiable, then the pdf can be obtained by differentiating the CDF:
> >
> > $$\boxed{
> > f_X(x)=F_X'(x)
> > }$$
> >
> > Therefore:
> >
> > $$\boxed{
> > F_X(x)=\int_{-\infty}^{x}f_X(y)\,dy
> > \quad\Longleftrightarrow\quad
> > f_X(x)=F_X'(x)
> > }$$
>
> > [!tip]- Important Interpretation
> > For continuous random variables, we can study the distribution almost entirely through its pdf $f_X$.
> >
> > The pdf itself is **not a probability** at a point.
> >
> > Instead, probabilities are obtained by integrating the pdf over an interval:
> >
> > $$P(a\le X\le b)=\int_a^b f_X(x)\,dx.$$
> >
> > Think of:
> >
> > $$\boxed{\text{Probability}=\text{area under the pdf}}$$
>
> > [!abstract]- Constructing a Probability Space from a PDF
> > Given a valid density function $f_X$, we can construct a probability measure on:
> >
> > $$(\mathbb R,\mathcal B(\mathbb R))$$
> >
> > by defining:
> >
> > $$\boxed{
> > P_X(A)=\int_Af_X(x)\,dx,
> > \qquad A\in\mathcal B(\mathbb R)
> > }$$
> >
> > Here:
> >
> > - $\mathbb R$ is the sample space.
> > - $\mathcal B(\mathbb R)$ is the Borel $\sigma$-field.
> > - $P_X$ is the probability measure induced by the density.
> >
> > Thus, once we know $f_X$, we can describe the distribution of $X$ without explicitly referring to the original $(\Omega,\mathcal F,P)$.
>
> > [!important]- Basic Properties
> > Let $X$ be a continuous random variable with pdf $f_X$.
> >
> > **Total probability is $1$:**
> >
> > $$\boxed{
> > \int_{-\infty}^{\infty}f_X(x)\,dx=1
> > }$$
> >
> > **Probability over an interval:**
> >
> > For $a\le b$:
> >
> > $$\boxed{
> > P(a\le X\le b)
> > =
> > \int_a^b f_X(x)\,dx
> > }$$
> >
> > **Probability at a single point:**
> >
> > $$\boxed{
> > P(X=x)=0
> > }$$
> >
> > for every $x\in\mathbb R$.
>
> > [!tip]- Why Does the PDF Integrate to 1?
> > Since a CDF satisfies:
> >
> > $$\lim_{x\to\infty}F_X(x)=1$$
> >
> > and:
> >
> > $$F_X(x)=\int_{-\infty}^{x}f_X(y)\,dy,$$
> >
> > taking $x\to\infty$ gives:
> >
> > $$\boxed{
> > \int_{-\infty}^{\infty}f_X(y)\,dy=1
> > }$$
> >
> > Therefore, the **total area under a pdf is always $1$**.
>
> > [!abstract]- Deriving the Interval Probability
> > We have:
> >
> > $$\{X\le b\}
> > =
> > \{X<a\}\cup\{a\le X\le b\}$$
> >
> > and the two events are disjoint.
> >
> > Therefore:
> >
> > $$P(X\le b)
> > =
> > P(X<a)+P(a\le X\le b).$$
> >
> > For a continuous random variable:
> >
> > $$P(X<a)=F_X(a).$$
> >
> > Hence:
> >
> > $$F_X(b)=F_X(a)+P(a\le X\le b).$$
> >
> > Therefore:
> >
> > $$\begin{aligned}
> > P(a\le X\le b)
> > &=F_X(b)-F_X(a)\\
> > &=\int_{-\infty}^{b}f_X(x)\,dx
> > -\int_{-\infty}^{a}f_X(x)\,dx\\
> > &=\boxed{\int_a^bf_X(x)\,dx}.
> > \end{aligned}$$
>
> > [!abstract]- Why $P(X=x)=0$
> > Set $a=b=x$ in the interval formula:
> >
> > $$P(x\le X\le x)
> > =
> > \int_x^xf_X(t)\,dt=0.$$
> >
> > Since:
> >
> > $$\{x\le X\le x\}=\{X=x\},$$
> >
> > we obtain:
> >
> > $$\boxed{P(X=x)=0}$$
> >
> > for every specific value $x$.
> >
> > This does **not** mean that $X$ cannot take the value $x$. It means that the probability assigned to any single point is zero.
>
> > [!example]- Example: Uniform Distribution
> > Consider a stick of length $1$ and let $X$ be the position at which the stick breaks.
> >
> > Then $X$ has a uniform distribution on $[0,1]$:
> >
> > $$X\sim\operatorname{Unif}[0,1].$$
> >
> > Its pdf is:
> >
> > $$f_X(x)=
> > \begin{cases}
> > 1,&0\le x\le1,\\
> > 0,&\text{otherwise}.
> > \end{cases}$$
> >
> > For example:
> >
> > $$P(0.2\le X\le0.5)
> > =\int_{0.2}^{0.5}1\,dx
> > =0.3.$$
> >
> > But:
> >
> > $$P(X=0.5)=0.$$
>
> > [!example]- Example: $Y=X^2$
> > Suppose:
> >
> > $$X\sim\operatorname{Unif}[0,1]$$
> >
> > and define:
> >
> > $$Y=X^2.$$
> >
> > Then the pdf of $Y$ is:
> >
> > $$\boxed{
> > f_Y(y)=\frac{1}{2\sqrt y},
> > \qquad 0<y<1
> > }$$
> >
> > and:
> >
> > $$f_Y(y)=0$$
> >
> > otherwise.
> >
> > Notice that the density is not constant anymore, even though $X$ was uniformly distributed.
>
> > [!tip]- How to Write a PDF
> > Usually, when writing a pdf, we only specify the region where it is nonzero.
> >
> > For example:
> >
> > $$f_Y(y)=\frac{1}{2\sqrt y},
> > \qquad 0<y<1.$$
> >
> > It is understood that:
> >
> > $$f_Y(y)=0$$
> >
> > outside this range.
>
> > [!warning]- PDF Is Not Probability
> > Do **not** interpret:
> >
> > $$f_X(x)=P(X=x).$$
> >
> > This is true for a discrete pmf, but **not** for a continuous pdf.
> >
> > For a continuous random variable:
> >
> > $$\boxed{P(X=x)=0}$$
> >
> > while:
> >
> > $$f_X(x)
> > $$
> >
> > can be positive.
> >
> > The probability comes from an integral:
> >
> > $$\boxed{
> > P(a\le X\le b)=\int_a^bf_X(x)\,dx
> > }$$
>
> > [!important]- Discrete vs Continuous
> > **Discrete:**
> >
> > $$P(X=x)=f_X(x)$$
> >
> > where $f_X$ is a pmf.
> >
> > **Continuous:**
> >
> > $$P(X=x)=0$$
> >
> > and:
> >
> > $$P(a\le X\le b)=\int_a^bf_X(x)\,dx$$
> >
> > where $f_X$ is a pdf.
> >
> > The key difference is:
> >
> > $$\boxed{
> > \text{Discrete: probability is summed}
> > }$$
> >
> > $$\boxed{
> > \text{Continuous: probability is integrated}
> > }$$

---

> [!important]- Independence of Continuous Random Variables
> > [!abstract]- Why We Need a New Definition
> > For discrete random variables $X$ and $Y$, independence was defined using events:
> >
> > $$\{X=x\}\quad\text{and}\quad\{Y=y\}.$$
> >
> > We required:
> >
> > $$P(X=x,Y=y)=P(X=x)P(Y=y).$$
> >
> > However, for continuous random variables:
> >
> > $$P(X=x)=0,\qquad P(Y=y)=0$$
> >
> > for every $x,y$.
> >
> > Therefore, using individual events $\{X=x\}$ and $\{Y=y\}$ does not provide a useful definition of independence.
>
> > [!important]- Definition of Independence
> > Two continuous random variables $X$ and $Y$ are independent if, for **all** $x,y\in\mathbb R$, the events
> >
> > $$\{X\le x\}\quad\text{and}\quad\{Y\le y\}$$
> >
> > are independent.
> >
> > Therefore:
> >
> > $$\boxed{
> > P(X\le x,Y\le y)
> > =
> > P(X\le x)P(Y\le y)
> > }$$
> >
> > Equivalently, in terms of CDFs:
> >
> > $$\boxed{
> > F_{X,Y}(x,y)=F_X(x)F_Y(y)
> > }$$
> >
> > for all $x,y$.
>
> > [!tip]- This Is Actually the General Definition
> > The definition above is not only for continuous random variables.
> >
> > It is the general definition of independence of random variables:
> >
> > $$\boxed{
> > X\perp Y
> > \iff
> > P(X\le x,Y\le y)
> > =
> > P(X\le x)P(Y\le y)
> > \quad\forall x,y
> > }$$
> >
> > For discrete random variables, this definition is equivalent to the earlier definition based on:
> >
> > $$P(X=x,Y=y)=P(X=x)P(Y=y).$$
>
> > [!abstract]- Jointly Continuous Random Variables
> > Suppose $X$ and $Y$ are **jointly continuous** with joint pdf:
> >
> > $$f_{X,Y}(x,y).$$
> >
> > Then $X$ and $Y$ are independent if and only if:
> >
> > $$\boxed{
> > f_{X,Y}(x,y)=f_X(x)f_Y(y)
> > }$$
> >
> > for all $x,y$.
> >
> > Thus:
> >
> > $$\boxed{
> > X\perp Y
> > \iff
> > f_{X,Y}=f_Xf_Y
> > }$$
>
> > [!abstract]- Proof: Independence $\Rightarrow$ Product of PDFs
> > Assume $X$ and $Y$ are independent.
> >
> > Then:
> >
> > $$\begin{aligned}
> > F_{X,Y}(x,y)
> > &=P(X\le x,Y\le y)\\
> > &=P(X\le x)P(Y\le y)\\
> > &=F_X(x)F_Y(y).
> > \end{aligned}$$
> >
> > Since $X$ and $Y$ are continuous:
> >
> > $$F_X(x)=\int_{-\infty}^{x}f_X(u)\,du$$
> >
> > and:
> >
> > $$F_Y(y)=\int_{-\infty}^{y}f_Y(v)\,dv.$$
> >
> > Therefore:
> >
> > $$\begin{aligned}
> > F_{X,Y}(x,y)
> > &=
> > \left(\int_{-\infty}^{x}f_X(u)\,du\right)
> > \left(\int_{-\infty}^{y}f_Y(v)\,dv\right)\\
> > &=
> > \int_{-\infty}^{x}
> > \int_{-\infty}^{y}
> > f_X(u)f_Y(v)\,dv\,du.
> > \end{aligned}$$
> >
> > Comparing this with the definition of the joint CDF:
> >
> > $$F_{X,Y}(x,y)
> > =
> > \int_{-\infty}^{x}
> > \int_{-\infty}^{y}
> > f_{X,Y}(u,v)\,dv\,du,$$
> >
> > we see that:
> >
> > $$\boxed{
> > f_{X,Y}(x,y)=f_X(x)f_Y(y)
> > }$$
>
> > [!abstract]- Converse
> > If:
> >
> > $$f_{X,Y}(x,y)=f_X(x)f_Y(y),$$
> >
> > then:
> >
> > $$\begin{aligned}
> > F_{X,Y}(x,y)
> > &=\int_{-\infty}^{x}
> > \int_{-\infty}^{y}
> > f_{X,Y}(u,v)\,dv\,du\\
> > &=\int_{-\infty}^{x}
> > \int_{-\infty}^{y}
> > f_X(u)f_Y(v)\,dv\,du\\
> > &=\left(\int_{-\infty}^{x}f_X(u)\,du\right)
> > \left(\int_{-\infty}^{y}f_Y(v)\,dv\right)\\
> > &=F_X(x)F_Y(y).
> > \end{aligned}$$
> >
> > Hence:
> >
> > $$P(X\le x,Y\le y)
> > =
> > P(X\le x)P(Y\le y),$$
> >
> > so $X$ and $Y$ are independent.
>
> > [!tip]- Intuition
> > The joint pdf:
> >
> > $$f_{X,Y}(x,y)$$
> >
> > describes how $X$ and $Y$ behave **together**.
> >
> > If they are independent, their joint behavior can be completely constructed from their individual behaviors:
> >
> > $$\boxed{
> > f_{X,Y}(x,y)=f_X(x)f_Y(y)
> > }$$
> >
> > So knowing the value of $X$ gives no information about the distribution of $Y$, and vice versa.
>
> > [!important]- Key Relationships
> > **General definition:**
> >
> > $$\boxed{
> > X\perp Y
> > \iff
> > F_{X,Y}(x,y)=F_X(x)F_Y(y)
> > }$$
> >
> > **For jointly continuous random variables:**
> >
> > $$\boxed{
> > X\perp Y
> > \iff
> > f_{X,Y}(x,y)=f_X(x)f_Y(y)
> > }$$
> >
> > **For discrete random variables:**
> >
> > $$\boxed{
> > X\perp Y
> > \iff
> > f_{X,Y}(x,y)=f_X(x)f_Y(y)
> > }$$
> >
> > Thus, the **product-form condition** works for both discrete and jointly continuous random variables, although the underlying definitions of pmf and pdf are different.

> [!important]- Expectation of Continuous Random Variables
> > [!abstract]- Definition
> > Similar to the discrete case, expectation is the probability-weighted average of possible values.
> >
> > For a continuous random variable $X$ with pdf $f_X$:
> >
> > $$\boxed{
> > E[X]=\int_{-\infty}^{\infty}xf_X(x)\,dx
> > }$$
> >
> > provided the integral exists.
> >
> > Compare:
> >
> > **Discrete:**
> >
> > $$E[X]=\sum_xxf_X(x)$$
> >
> > **Continuous:**
> >
> > $$E[X]=\int_{-\infty}^{\infty}xf_X(x)\,dx$$
> >
> > The sum is replaced by an integral.
>
> > [!important]- Linearity of Expectation
> > Expectation is linear for continuous random variables.
> >
> > For continuous random variables $X,Y$ and constants $a,b$:
> >
> > $$\boxed{
> > E[aX+bY]
> > =
> > aE[X]+bE[Y]
> > }$$
> >
> > Independence is **not required** for linearity of expectation.
>
> > [!abstract]- Expectation of a Function of $X$
> > Let $g$ be an $\mathcal F$-measurable function such that $g(X)$ is a continuous random variable.
> >
> > Then:
> >
> > $$\boxed{
> > E[g(X)]
> > =
> > \int_{-\infty}^{\infty}g(x)f_X(x)\,dx
> > }$$
> >
> > This is the continuous version of **LOTUS (Law of the Unconscious Statistician)**.
> >
> > Compare:
> >
> > **Discrete:**
> >
> > $$E[g(X)]
> > =
> > \sum_xg(x)f_X(x)$$
> >
> > **Continuous:**
> >
> > $$E[g(X)]
> > =
> > \int_{-\infty}^{\infty}g(x)f_X(x)\,dx$$
>
> > [!important]- Lemma: Expectation of a Nonnegative Random Variable
> > Suppose $X$ is nonnegative:
> >
> > $$X\ge0.$$
> >
> > Then:
> >
> > $$\boxed{
> > E[X]
> > =
> > \int_0^\infty(1-F_X(x))\,dx
> > }$$
> >
> > Since:
> >
> > $$F_X(x)=P(X\le x),$$
> >
> > we have:
> >
> > $$1-F_X(x)=P(X>x).$$
> >
> > Therefore:
> >
> > $$\boxed{
> > E[X]
> > =
> > \int_0^\infty P(X>x)\,dx
> > }$$
> >
> > The function:
> >
> > $$1-F_X(x)$$
> >
> > is called the **complementary CDF (CCDF)** or **survival function**.
>
> > [!tip]- Intuition Behind the CCDF Formula
> > Instead of calculating the average using:
> >
> > $$E[X]=\int_0^\infty xf_X(x)\,dx,$$
> >
> > we can calculate it by measuring how long the random variable remains above each threshold $x$:
> >
> > $$E[X]=\int_0^\infty P(X>x)\,dx.$$
> >
> > Thus:
> >
> > $$\boxed{
> > \text{Expected value}
> > =
> > \text{area under the survival function}
> > }$$
>
> > [!abstract]- Proof of the Nonnegative Identity
> > Start with:
> >
> > $$\begin{aligned}
> > \int_0^\infty(1-F_X(x))\,dx
> > &=\int_0^\infty P(X>x)\,dx\\
> > &=\int_0^\infty
> > \int_x^\infty f_X(y)\,dy\,dx.
> > \end{aligned}$$
> >
> > The integration region is:
> >
> > $$0\le x\le y<\infty.$$
> >
> > Change the order of integration:
> >
> > $$\begin{aligned}
> > &=\int_0^\infty
> > \int_0^y f_X(y)\,dx\,dy\\
> > &=\int_0^\infty
> > \left(\int_0^y dx\right)f_X(y)\,dy\\
> > &=\int_0^\infty yf_X(y)\,dy.
> > \end{aligned}$$
> >
> > Since $X\ge0$:
> >
> > $$\int_0^\infty yf_X(y)\,dy
> > =
> > \int_{-\infty}^{\infty}yf_X(y)\,dy.$$
> >
> > Therefore:
> >
> > $$\boxed{
> > E[X]
> > =
> > \int_0^\infty(1-F_X(x))\,dx
> > }$$
>
> > [!important]- LOTUS for Nonnegative $g$
> > Suppose $g(X)\ge0$ and $g(X)$ is continuous.
> >
> > Applying the previous result to the random variable $g(X)$:
> >
> > $$E[g(X)]
> > =
> > \int_0^\infty P(g(X)>x)\,dx.$$
> >
> > For a fixed $x$, define:
> >
> > $$B_x=\{y:g(y)>x\}.$$
> >
> > Then:
> >
> > $$P(g(X)>x)
> > =
> > P(X\in B_x).$$
> >
> > Using the pdf of $X$:
> >
> > $$P(X\in B_x)
> > =
> > \int_{y\in B_x}f_X(y)\,dy.$$
> >
> > Hence:
> >
> > $$E[g(X)]
> > =
> > \int_0^\infty
> > \int_{y:g(y)>x}
> > f_X(y)\,dy\,dx.$$
>
> > [!abstract]- Changing the Order of Integration
> > The integration region is:
> >
> > $$\{(x,y):0\le x<\infty,\ g(y)>x\}.$$
> >
> > Equivalently:
> >
> > $$\{(x,y):-\infty<y<\infty,\ 0\le x<g(y)\}.$$
> >
> > Therefore, changing the order of integration:
> >
> > $$\begin{aligned}
> > E[g(X)]
> > &=\int_{-\infty}^{\infty}
> > \int_0^{g(y)}
> > f_X(y)\,dx\,dy\\
> > &=\int_{-\infty}^{\infty}
> > \left(\int_0^{g(y)}dx\right)f_X(y)\,dy\\
> > &=\boxed{
> > \int_{-\infty}^{\infty}
> > g(y)f_X(y)\,dy
> > }.
> > \end{aligned}$$
> >
> > Thus:
> >
> > $$\boxed{
> > E[g(X)]
> > =
> > \int_{-\infty}^{\infty}g(x)f_X(x)\,dx
> > }$$
> >
> > for nonnegative $g$.
>
> > [!abstract]- General $g$: Positive and Negative Parts
> > If $g$ can take both positive and negative values, write:
> >
> > $$\boxed{
> > g=g^+-g^-
> > }$$
> >
> > where:
> >
> > $$g^+=\max(g,0),\qquad
> > g^-=\max(-g,0).$$
> >
> > Both $g^+$ and $g^-$ are nonnegative.
> >
> > Applying the nonnegative result to each part and using linearity:
> >
> > $$\begin{aligned}
> > E[g(X)]
> > &=E[g^+(X)]-E[g^-(X)]\\
> > &=\int_{-\infty}^{\infty}
> > g^+(x)f_X(x)\,dx
> > -
> > \int_{-\infty}^{\infty}
> > g^-(x)f_X(x)\,dx\\
> > &=\boxed{
> > \int_{-\infty}^{\infty}
> > g(x)f_X(x)\,dx
> > }.
> > \end{aligned}$$
>
> > [!important]- Key Formulas
> > **Expectation:**
> >
> > $$\boxed{
> > E[X]=\int_{-\infty}^{\infty}xf_X(x)\,dx
> > }$$
> >
> > **Linearity:**
> >
> > $$\boxed{
> > E[aX+bY]=aE[X]+bE[Y]
> > }$$
> >
> > **LOTUS:**
> >
> > $$\boxed{
> > E[g(X)]
> > =
> > \int_{-\infty}^{\infty}g(x)f_X(x)\,dx
> > }$$
> >
> > **Nonnegative $X$:**
> >
> > $$\boxed{
> > E[X]
> > =
> > \int_0^\infty(1-F_X(x))\,dx
> > =
> > \int_0^\infty P(X>x)\,dx
> > }$$
>
> > [!tip]- Big Picture
> > The discrete and continuous formulas have the same underlying idea:
> >
> > $$\boxed{
> > \text{Expectation = average over the distribution}
> > }$$
> >
> > **Discrete:**
> >
> > $$E[g(X)]
> > =
> > \sum_xg(x)P(X=x)$$
> >
> > **Continuous:**
> >
> > $$E[g(X)]
> > =
> > \int g(x)f_X(x)\,dx.$$
> >
> > The integral is the continuous analogue of the sum.

---

> [!important]- Moments, Variance, and Common Continuous Distributions
> > [!abstract]- Moments
> > Moments for continuous random variables are defined in the same way as for discrete random variables, with sums replaced by integrals.
> >
> > The $k$th moment is:
> >
> > $$\boxed{
> > E[X^k]
> > =
> > \int_{-\infty}^{\infty}x^k f_X(x)\,dx
> > }$$
> >
> > The $k$th centered moment is:
> >
> > $$\boxed{
> > E[(X-E[X])^k]
> > }$$
> >
> > Important special cases:
> >
> > $$E[X] = \text{first moment}$$
> >
> > $$E[(X-E[X])^2]=\operatorname{Var}(X)$$
>
> > [!important]- Variance
> > Variance measures the spread of $X$ around its mean:
> >
> > $$\boxed{
> > \operatorname{Var}(X)
> > =
> > E[(X-E[X])^2]
> > }$$
> >
> > Equivalently:
> >
> > $$\boxed{
> > \operatorname{Var}(X)
> > =
> > E[X^2]-(E[X])^2
> > }$$
> >
> > For a continuous random variable:
> >
> > $$\operatorname{Var}(X)
> > =
> > \int_{-\infty}^{\infty}
> > (x-E[X])^2f_X(x)\,dx.$$
>
> > [!important]- Covariance
> > The covariance between continuous random variables $X$ and $Y$ is:
> >
> > $$\boxed{
> > \operatorname{Cov}(X,Y)
> > =
> > E[(X-E[X])(Y-E[Y])]
> > }$$
> >
> > Using linearity of expectation:
> >
> > $$\boxed{
> > \operatorname{Cov}(X,Y)
> > =
> > E[XY]-E[X]E[Y]
> > }$$
> >
> > If $X$ and $Y$ are uncorrelated:
> >
> > $$\boxed{
> > \operatorname{Cov}(X,Y)=0
> > }$$
>
> > [!warning]- Independence vs Uncorrelatedness
> > If $X$ and $Y$ are independent, then:
> >
> > $$\boxed{
> > X\perp Y\Rightarrow\operatorname{Cov}(X,Y)=0
> > }$$
> >
> > However, the converse is not generally true:
> >
> > $$\boxed{
> > \operatorname{Cov}(X,Y)=0
> > \not\Rightarrow
> > X\perp Y
> > }$$
> >
> > Thus, zero covariance means no linear dependence, but nonlinear dependence may still exist.
>
> > [!example]- Uniform Distribution
> > A random variable $X$ has a **uniform distribution** on $[a,b]$ if:
> >
> > $$\boxed{
> > f_X(x)=\frac{1}{b-a},
> > \qquad a\le x\le b
> > }$$
> >
> > and $f_X(x)=0$ otherwise.
> >
> > We write:
> >
> > $$\boxed{
> > X\sim\operatorname{Unif}[a,b]
> > }$$
> >
> > The special case:
> >
> > $$X\sim\operatorname{Unif}[0,1]$$
> >
> > was used in the stick-breaking example.
>
> > [!example]- Exponential Distribution
> > The exponential distribution arises as a continuous limit of a waiting-time distribution.
> >
> > Suppose independent Bernoulli trials occur at times:
> >
> > $$\delta,2\delta,3\delta,\ldots$$
> >
> > Let $X$ be the time of the first success.
>
> > [!abstract]- Deriving the Exponential Distribution
> > The number of trials until the first success follows a geometric distribution:
> >
> > $$N\sim\operatorname{Geom}(p).$$
> >
> > Therefore:
> >
> > $$\begin{aligned}
> > P(X>k\delta)
> > &=P(N>k)\\
> > &=(1-p)^k.
> > \end{aligned}$$
> >
> > Fix a time $t$. Approximately:
> >
> > $$k=\frac{t}{\delta}.$$
> >
> > Now choose:
> >
> > $$p=\delta\lambda.$$
> >
> > Then as $\delta\to0$:
> >
> > $$\begin{aligned}
> > P(X>t)
> > &\approx
> > (1-\delta\lambda)^{t/\delta}\\
> > &\longrightarrow e^{-\lambda t}.
> > \end{aligned}$$
> >
> > Therefore, the CDF is:
> >
> > $$\boxed{
> > F_X(t)=1-e^{-\lambda t},
> > \qquad t\ge0
> > }$$
> >
> > Differentiating:
> >
> > $$\boxed{
> > f_X(t)=\lambda e^{-\lambda t},
> > \qquad t\ge0
> > }$$
> >
> > This is the **exponential distribution** with rate parameter $\lambda$:
> >
> > $$\boxed{
> > X\sim\operatorname{Exp}(\lambda)
> > }$$
>
> > [!tip]- Interpretation of $\lambda$
> > $\lambda$ is called the **rate parameter**.
> >
> > Larger $\lambda$ means successes occur more frequently, so the waiting time tends to be shorter.
> >
> > The survival function is:
> >
> > $$\boxed{
> > P(X>t)=e^{-\lambda t}
> > }$$
>
> > [!example]- Gaussian / Normal Distribution
> > A Gaussian (or normal) random variable with mean $\mu$ and variance $\sigma^2$ has pdf:
> >
> > $$\boxed{
> > f_X(x)
> > =
> > \frac{1}{\sqrt{2\pi\sigma^2}}
> > \exp\left(
> > -\frac{(x-\mu)^2}{2\sigma^2}
> > \right)
> > }$$
> >
> > We write:
> >
> > $$\boxed{
> > X\sim N(\mu,\sigma^2)
> > }$$
> >
> > Here:
> >
> > $$E[X]=\mu$$
> >
> > $$\operatorname{Var}(X)=\sigma^2.$$
>
> > [!tip]- Origin of the Normal Distribution
> > The normal distribution arises as a limiting distribution of suitably scaled sums of independent random variables.
> >
> > In particular, it is closely connected to the **Central Limit Theorem (CLT)**.
> >
> > The lecture notes mention its connection with a suitably scaled binomial/Bernoulli model; this will be studied in more detail later.
>
> > [!important]- Standard Normal Distribution
> > The special case:
> >
> > $$\boxed{
> > N(0,1)
> > }$$
> >
> > is called the **standard normal distribution**.
> >
> > Its pdf is conventionally denoted by $\phi$:
> >
> > $$\boxed{
> > \phi(z)
> > =
> > \frac{1}{\sqrt{2\pi}}
> > e^{-z^2/2}
> > }$$
> >
> > Its CDF is conventionally denoted by $\Phi$:
> >
> > $$\boxed{
> > \Phi(z)
> > =
> > P(Z\le z)
> > =
> > \int_{-\infty}^{z}\phi(t)\,dt
> > }$$
> >
> > where $Z\sim N(0,1)$.
>
> > [!abstract]- Standardization of a Normal Random Variable
> > If:
> >
> > $$X\sim N(\mu,\sigma^2),$$
> >
> > define:
> >
> > $$\boxed{
> > Y=\frac{X-\mu}{\sigma}
> > }$$
> >
> > Then:
> >
> > $$\boxed{
> > Y\sim N(0,1)
> > }$$
> >
> > This transformation is called **standardization**.
>
> > [!abstract]- Derivation of Standardization
> > We want to find the CDF of:
> >
> > $$Y=\frac{X-\mu}{\sigma}.$$
> >
> > Assuming $\sigma>0$:
> >
> > $$\begin{aligned}
> > F_Y(y)
> > &=P(Y\le y)\\
> > &=P\left(\frac{X-\mu}{\sigma}\le y\right)\\
> > &=P(X\le\mu+\sigma y).
> > \end{aligned}$$
> >
> > Therefore:
> >
> > $$F_Y(y)
> > =
> > \int_{-\infty}^{\mu+\sigma y}
> > f_X(x)\,dx.$$
> >
> > Make the change of variable:
> >
> > $$x=\mu+\sigma z,$$
> >
> > so:
> >
> > $$dx=\sigma\,dz.$$
> >
> > The upper limit becomes $z=y$.
> >
> > Substituting the normal pdf gives:
> >
> > $$\begin{aligned}
> > F_Y(y)
> > &=\int_{-\infty}^{y}
> > \frac{1}{\sqrt{2\pi}}
> > e^{-z^2/2}\,dz\\
> > &=\int_{-\infty}^{y}\phi(z)\,dz\\
> > &=\Phi(y).
> > \end{aligned}$$
> >
> > Hence:
> >
> > $$\boxed{F_Y(y)=\Phi(y)}$$
> >
> > and therefore:
> >
> > $$\boxed{Y\sim N(0,1).}$$
>
> > [!tip]- Why Standardization Is Useful
> > Any normal random variable can be converted into the same standard normal variable:
> >
> > $$\boxed{
> > Z=\frac{X-\mu}{\sigma}
> > }$$
> >
> > Therefore probabilities involving any $N(\mu,\sigma^2)$ variable can be converted to probabilities involving $N(0,1)$:
> >
> > $$\boxed{
> > P(X\le x)
> > =
> > \Phi\left(\frac{x-\mu}{\sigma}\right)
> > }$$
>
> > [!important]- Key Distributions
> > **Uniform:**
> >
> > $$\boxed{
> > X\sim\operatorname{Unif}[a,b]
> > }$$
> >
> > $$f_X(x)=\frac1{b-a},\qquad a\le x\le b.$$
> >
> > **Exponential:**
> >
> > $$\boxed{
> > X\sim\operatorname{Exp}(\lambda)
> > }$$
> >
> > $$f_X(x)=\lambda e^{-\lambda x},\qquad x\ge0.$$
> >
> > **Normal:**
> >
> > $$\boxed{
> > X\sim N(\mu,\sigma^2)
> > }$$
> >
> > $$f_X(x)
> > =
> > \frac1{\sqrt{2\pi\sigma^2}}
> > e^{-(x-\mu)^2/(2\sigma^2)}.$$
> >
> > **Standard normal:**
> >
> > $$\boxed{
> > Z\sim N(0,1)
> > }$$
> >
> > with pdf $\phi$ and CDF $\Phi$.

> [!important]- Sum of Continuous Random Variables
> > [!abstract]- Density of the Sum
> > Let $X$ and $Y$ be jointly continuous random variables with joint density $f_{X,Y}(x,y)$.
> >
> > Define
> > $$Z=X+Y.$$
> >
> > Then the density of $Z$ is
> > $$\boxed{f_Z(z)=\int_{-\infty}^{\infty}f_{X,Y}(x,z-x)\,dx.}$$
> >
> > If $X$ and $Y$ are independent, then
> > $$f_{X,Y}(x,y)=f_X(x)f_Y(y),$$
> > so
> > $$\boxed{f_Z(z)=\int_{-\infty}^{\infty}f_X(x)f_Y(z-x)\,dx.}$$
> >
> > This is exactly the **convolution** of $f_X$ and $f_Y$:
> > $$\boxed{f_Z=f_X*f_Y.}$$
>
> > [!tip]- Intuition
> > To find the probability that $X+Y$ is around $z$, consider all possible values of $X=x$.
> >
> > If $X=x$, then we need
> > $$Y=z-x$$
> > to make the sum equal $z$.
> >
> > Therefore, we integrate the joint density along the line
> > $$x+y=z.$$
> >
> > The integral
> > $$\int_{-\infty}^{\infty}f_{X,Y}(x,z-x)\,dx$$
> > adds the contributions from every possible $x$.
>
> > [!abstract]- Derivation Using the CDF
> > Start with
> > $$F_Z(z)=P(Z\le z).$$
> >
> > Since $Z=X+Y$,
> > $$F_Z(z)=P(X+Y\le z).$$
> >
> > In the $(x,y)$-plane, this corresponds to the region
> > $$A=\{(x,y):x+y\le z\}.$$
> >
> > Equivalently,
> > $$A=\{(x,y):-\infty<x<\infty,\;-\infty<y\le z-x\}.$$
> >
> > Therefore,
> > $$F_Z(z)
> > =\int_{-\infty}^{\infty}
> > \int_{-\infty}^{z-x}
> > f_{X,Y}(x,y)\,dy\,dx.$$
> >
> > For fixed $x$, let
> > $$v=x+y.$$
> > Then
> > $$y=v-x,\qquad dy=dv.$$
> >
> > Hence
> > $$F_Z(z)
> > =\int_{-\infty}^{\infty}
> > \int_{-\infty}^{z}
> > f_{X,Y}(x,v-x)\,dv\,dx.$$
> >
> > Change the order of integration:
> > $$F_Z(z)
> > =\int_{-\infty}^{z}
> > \int_{-\infty}^{\infty}
> > f_{X,Y}(x,v-x)\,dx\,dv.$$
> >
> > Compare this with
> > $$F_Z(z)=\int_{-\infty}^{z}f_Z(v)\,dv.$$
> >
> > Therefore,
> > $$\boxed{f_Z(v)=\int_{-\infty}^{\infty}f_{X,Y}(x,v-x)\,dx.}$$
> >
> > Renaming $v$ as $z$ gives
> > $$\boxed{f_Z(z)=\int_{-\infty}^{\infty}f_{X,Y}(x,z-x)\,dx.}$$
>
> > [!example]- Example: Sum of Two Standard Gaussians
> > Let
> > $$X,Y\overset{\text{ind}}{\sim}N(0,1).$$
> >
> > Define
> > $$Z=X+Y.$$
> >
> > Since $X$ and $Y$ are independent,
> > $$f_Z(z)=\int_{-\infty}^{\infty}f_X(x)f_Y(z-x)\,dx.$$
> >
> > For $N(0,1)$,
> > $$f_X(x)=\frac1{\sqrt{2\pi}}e^{-x^2/2}.$$
> >
> > Therefore,
> > $$f_Z(z)
> > =\frac1{2\pi}\int_{-\infty}^{\infty}
> > \exp\left\{-\frac{x^2}{2}-\frac{(z-x)^2}{2}\right\}dx.$$
> >
> > Complete the square:
> > $$-\frac{x^2}{2}-\frac{(z-x)^2}{2}
> > =-\frac{z^2}{4}-\left(x-\frac z2\right)^2.$$
> >
> > Hence,
> > $$f_Z(z)
> > =\frac1{2\pi}e^{-z^2/4}
> > \int_{-\infty}^{\infty}
> > e^{-(x-z/2)^2}\,dx.$$
> >
> > Let
> > $$u=\sqrt2\left(x-\frac z2\right).$$
> > Then
> > $$dx=\frac{du}{\sqrt2}$$
> > and
> > $$e^{-(x-z/2)^2}=e^{-u^2/2}.$$
> >
> > Thus,
> > $$f_Z(z)
> > =\frac1{2\pi}e^{-z^2/4}
> > \frac1{\sqrt2}
> > \int_{-\infty}^{\infty}e^{-u^2/2}\,du.$$
> >
> > Since
> > $$\int_{-\infty}^{\infty}e^{-u^2/2}\,du=\sqrt{2\pi},$$
> > we obtain
> > $$f_Z(z)=\frac1{\sqrt{4\pi}}e^{-z^2/4}.$$
> >
> > This is the density of
> > $$\boxed{N(0,2)}.$$
> >
> > Therefore,
> > $$\boxed{X+Y\sim N(0,2).}$$
> >
> > More generally, if independent
> > $$X\sim N(\mu_1,\sigma_1^2),\qquad
> > Y\sim N(\mu_2,\sigma_2^2),$$
> > then
> > $$\boxed{X+Y\sim N(\mu_1+\mu_2,\sigma_1^2+\sigma_2^2).}$$
>
> > [!example]- Example: Sum of Two Exponential Random Variables
> > Let
> > $$X,Y\overset{\text{ind}}{\sim}\operatorname{Exp}(\lambda).$$
> >
> > Their densities are
> > $$f_X(x)=f_Y(x)=\lambda e^{-\lambda x},\qquad x\ge0.$$
> >
> > Let
> > $$Z=X+Y.$$
> >
> > By convolution,
> > $$f_Z(z)=\int_{-\infty}^{\infty}
> > f_X(x)f_Y(z-x)\,dx.$$
> >
> > Because both exponential densities are zero for negative arguments, the integrand is nonzero only when
> > $$x\ge0,\qquad z-x\ge0.$$
> >
> > Thus,
> > $$0\le x\le z,$$
> > which requires $z\ge0$.
> >
> > Therefore,
> > $$f_Z(z)
> > =\int_0^z
> > \lambda e^{-\lambda x}
> > \lambda e^{-\lambda(z-x)}\,dx.$$
> >
> > Simplify:
> > $$f_Z(z)
> > =\lambda^2e^{-\lambda z}\int_0^z1\,dx.$$
> >
> > Hence,
> > $$\boxed{f_Z(z)=\lambda^2ze^{-\lambda z},\qquad z\ge0.}$$
> >
> > This is a Gamma distribution with shape $2$ and rate $\lambda$:
> > $$\boxed{Z\sim\Gamma(2,\lambda).}$$
>
> > [!abstract]- Sum of $t$ Independent Exponentials
> > Let
> > $$X_1,\ldots,X_t\overset{\text{i.i.d.}}{\sim}\operatorname{Exp}(\lambda),$$
> > where $t$ is a positive integer.
> >
> > Define
> > $$Z=X_1+\cdots+X_t.$$
> >
> > Repeated convolution gives
> > $$\boxed{
> > f_Z(z)=
> > \frac{\lambda^t}{(t-1)!}
> > z^{t-1}e^{-\lambda z},
> > \qquad z\ge0.
> > }$$
> >
> > Therefore,
> > $$\boxed{Z\sim\Gamma(t,\lambda).}$$
> >
> > The parameter $t$ is called the **shape** and $\lambda$ is the **rate**.
>
> > [!abstract]- Gamma Distribution
> > The Gamma distribution generalizes the sum-of-exponentials result to any real shape parameter $t>0$.
> >
> > We write
> > $$X\sim\Gamma(t,\lambda),$$
> > where
> > $$t>0,\qquad\lambda>0.$$
> >
> > Its density is
> > $$\boxed{
> > f_X(x)=
> > \frac{\lambda^t}{\Gamma(t)}
> > x^{t-1}e^{-\lambda x},
> > \qquad x\ge0.
> > }$$
> >
> > Here $\Gamma(t)$ is the **Gamma function**:
> > $$\boxed{
> > \Gamma(t)=
> > \int_0^\infty x^{t-1}e^{-x}\,dx.
> > }$$
> >
> > For positive integers,
> > $$\boxed{\Gamma(t)=(t-1)!}.$$
> >
> > Therefore, when $t$ is an integer,
> > $$X\sim\Gamma(t,\lambda)$$
> > is exactly the sum of $t$ independent $\operatorname{Exp}(\lambda)$ random variables.
>
> > [!tip]- Big Picture
> > **Discrete case:**
> > $$P(X+Y=z)=\sum_x f_{X,Y}(x,z-x).$$
> >
> > **Continuous case:**
> > $$f_{X+Y}(z)=\int_{-\infty}^{\infty}f_{X,Y}(x,z-x)\,dx.$$
> >
> > If $X,Y$ are independent:
> > $$\boxed{
> > f_{X+Y}(z)=
> > \int_{-\infty}^{\infty}
> > f_X(x)f_Y(z-x)\,dx
> > }$$
> > which is the **convolution**.
> >
> > Important pattern:
> > $$\boxed{\text{Sum of independent variables}\quad\longrightarrow\quad\text{convolution}.}$$
> >
> > Important examples:
> > $$N(0,\sigma_1^2)+N(0,\sigma_2^2)
> > \sim N(0,\sigma_1^2+\sigma_2^2),$$
> > $$\operatorname{Exp}(\lambda)+\operatorname{Exp}(\lambda)
> > \sim\Gamma(2,\lambda),$$
> > $$\underbrace{\operatorname{Exp}(\lambda)+\cdots+\operatorname{Exp}(\lambda)}_{t\text{ terms}}
> > \sim\Gamma(t,\lambda).$$


