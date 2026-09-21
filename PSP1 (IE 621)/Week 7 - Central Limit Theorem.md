
> [!important]- Law of Large Numbers
> 
> > [!abstract]- Motivation
> > Suppose $\{X_i\}$ are i.i.d. random variables with
> > $$X_i\sim N(\mu,\sigma^2).$$
> > 
> > Their sample mean is
> > $$\bar X_n=\frac{1}{n}\sum_{i=1}^nX_i.$$
> > 
> > Since a linear combination of independent Gaussian random variables is Gaussian,
> > $$\bar X_n\sim N\left(\mu,\frac{\sigma^2}{n}\right).$$
> > 
> > Therefore,
> > $$E[\bar X_n]=\mu,\qquad \operatorname{Var}(\bar X_n)=\frac{\sigma^2}{n}.$$
> > 
> > As $n\to\infty$,
> > $$\operatorname{Var}(\bar X_n)\to0,$$
> > so $\bar X_n$ becomes increasingly concentrated around $\mu$.
> > 
> > This motivates the idea that
> > $$\bar X_n\to\mu.$$
> 
> > [!abstract]- Convergence in Distribution
> > A sequence of random variables $\{Y_n\}$ is said to **converge in distribution** to a random variable $Y$ if
> > $$\boxed{\lim_{n\to\infty}F_{Y_n}(y)=F_Y(y)}$$
> > for every **continuity point** $y$ of $F_Y$.
> > 
> > We write
> > $$Y_n\xrightarrow{d}Y.$$
> > 
> > The restriction to continuity points is important because a CDF may have jumps.
> 
> > [!example]- Sample Mean Converging to a Constant
> > For the sample mean,
> > $$Y_n=\bar X_n,\qquad Y=\mu,$$
> > where $\mu$ is treated as a constant random variable.
> > 
> > The CDF of the constant random variable $\mu$ is
> > $$F_Y(y)=
> > \begin{cases}
> > 0,&y<\mu,\\
> > 1,&y\ge\mu.
> > \end{cases}$$
> > 
> > Therefore, $F_Y$ has a discontinuity at $y=\mu$.
> > Every $y\neq\mu$ is a continuity point.
> > 
> > Hence, to establish
> > $$\bar X_n\xrightarrow{d}\mu,$$
> > we need the CDFs of $\bar X_n$ to converge to the above step-function CDF at every $y\neq\mu$.
> 
> > [!tip]- Equivalent Probability Interpretation
> > A useful fact is:
> > $$Y_n\xrightarrow{d}Y$$
> > can be established by showing that, for every $c>0$,
> > $$\boxed{\lim_{n\to\infty}P(|Y_n-Y|>c)=0.}$$
> > 
> > In words:
> > **the probability that $Y_n$ is more than $c$ away from $Y$ goes to zero.**
> > 
> > For the sample mean, this becomes
> > $$\boxed{\lim_{n\to\infty}P(|\bar X_n-\mu|>c)=0,\qquad c>0.}$$
> > 
> > This is the form that will be used to prove the Law of Large Numbers.
> 
> > [!important]- Key Idea Behind the Proof
> > We want to show
> > $$P(|\bar X_n-\mu|>c)\to0.$$
> > 
> > Directly calculating this probability may be difficult.
> > 
> > The strategy is therefore to **bound this probability using an expectation**:
> > $$P(\text{large deviation})
> > \quad\longrightarrow\quad
> > \text{an upper bound involving }E[\text{something}].$$
> > 
> > This leads to inequalities such as **Markov's inequality** and, for the usual LLN proof, **Chebyshev's inequality**.
> 
> > [!warning]- Important Distinction
> > The Gaussian example is only a motivating example.
> > 
> > The Law of Large Numbers is much more general: the $X_i$ do **not** have to be Gaussian.
> > 
> > Under appropriate conditions, if $X_1,X_2,\ldots$ are i.i.d. with
> > $$E[X_i]=\mu,$$
> > then
> > $$\bar X_n\xrightarrow{P}\mu,$$
> > which is the **Weak Law of Large Numbers**.
> > 
> > If additionally the stronger conditions of the Strong Law are satisfied, then
> > $$\bar X_n\xrightarrow{\text{a.s.}}\mu.$$
> > 
> > Thus, the main idea is:
> > $$\boxed{\text{More observations}\;\Rightarrow\;\text{sample mean gets closer to the population mean.}}$$

> [!important]- Important Probability Inequalities
>
> > [!abstract]- Motivation
> > In many applications, calculating a probability directly can be difficult, while calculating an expectation is easier.
> >
> > Therefore, we often use **inequalities to bound probabilities using expectations**:
> > $$\text{Probability} \leq \text{expression involving an expectation}.$$
> >
> > The main inequalities introduced here are:
> > - **Markov's inequality**
> > - **Chebyshev's inequality**
> > - **Chernoff's bound**
>
> > [!abstract]- Markov's Inequality
> > Suppose $X$ is a **nonnegative random variable**:
> > $$X\geq0$$
> > and let $c>0$.
> >
> > Consider the indicator function
> > $$\mathbf 1_{\{X\geq c\}}.$$
> >
> > If $X\geq c$, then
> > $$\mathbf 1_{\{X\geq c\}}=1\leq\frac{X}{c}.$$
> >
> > If $X<c$, then
> > $$\mathbf 1_{\{X\geq c\}}=0\leq\frac{X}{c}.$$
> >
> > Therefore, always,
> > $$\mathbf 1_{\{X\geq c\}}\leq\frac{X}{c}.$$
> >
> > Taking expectations:
> > $$E[\mathbf 1_{\{X\geq c\}}]
> > \leq E\left[\frac{X}{c}\right].$$
> >
> > Since
> > $$E[\mathbf 1_{\{X\geq c\}}]=P(X\geq c),$$
> > we obtain
> > $$\boxed{P(X\geq c)\leq\frac{E[X]}{c}}.$$
> >
> > This is **Markov's inequality**.
>
> > [!important]- Markov's Inequality — Interpretation
> > $$\boxed{P(X\geq c)\leq\frac{E[X]}{c}}$$
> >
> > It says that if a nonnegative random variable has a small expected value, then the probability of observing a very large value cannot be too large.
> >
> > The bound becomes smaller as $c$ increases:
> > $$c\uparrow\quad\Longrightarrow\quad\frac{E[X]}{c}\downarrow.$$
>
> > [!example]- Simple Example
> > Suppose
> > $$E[X]=10$$
> > and $X\geq0$.
> >
> > Then Markov's inequality gives
> > $$P(X\geq50)\leq\frac{10}{50}=0.2.$$
> >
> > So even without knowing the full distribution of $X$, we know that
> > $$P(X\geq50)\leq0.2.$$
>
> > [!abstract]- Chebyshev's Inequality
> > Markov's inequality can be applied to a transformed random variable.
> >
> > Define
> > $$Y=(X-E[X])^2.$$
> >
> > Since $Y\geq0$, Markov's inequality applies:
> > $$P(Y\geq c)\leq\frac{E[Y]}{c}.$$
> >
> > But
> > $$E[Y]
> > =E[(X-E[X])^2]
> > =\operatorname{Var}(X).$$
> >
> > Hence,
> > $$P((X-E[X])^2\geq c)
> > \leq\frac{\operatorname{Var}(X)}{c}.$$
> >
> > Taking $c=t^2$, where $t>0$:
> > $$\boxed{
> > P(|X-E[X]|\geq t)
> > \leq
> > \frac{\operatorname{Var}(X)}{t^2}
> > }.$$
> >
> > This is **Chebyshev's inequality**.
>
> > [!tip]- Why Chebyshev is Useful
> > Chebyshev measures the probability that $X$ is far away from its mean.
> >
> > $$P(|X-\mu|\geq t)
> > \leq\frac{\sigma^2}{t^2},$$
> > where
> > $$\mu=E[X],\qquad \sigma^2=\operatorname{Var}(X).$$
> >
> > Therefore:
> > - larger variance $\Rightarrow$ weaker bound;
> > - larger deviation $t$ $\Rightarrow$ smaller bound;
> > - the bound decreases as $1/t^2$.
>
> > [!abstract]- Chernoff's Bound
> > Sometimes Chebyshev's inequality is not tight enough.
> >
> > We can transform $X$ using an exponential:
> > $$e^{\theta X},\qquad \theta>0.$$
> >
> > Since
> > $$e^{\theta X}\geq0,$$
> > Markov's inequality gives
> > $$P(e^{\theta X}\geq e^{\theta c})
> > \leq
> > \frac{E[e^{\theta X}]}{e^{\theta c}}.$$
> >
> > Because the exponential function is increasing,
> > $$X\geq c
> > \iff
> > e^{\theta X}\geq e^{\theta c}.$$
> >
> > Therefore,
> > $$P(X\geq c)
> > \leq
> > e^{-\theta c}E[e^{\theta X}].$$
> >
> > Hence,
> > $$\boxed{
> > P(X\geq c)
> > \leq
> > e^{-\theta c}E[e^{\theta X}],
> > \qquad \theta>0.
> > }$$
>
> > [!important]- Optimizing the Chernoff Bound
> > The inequality holds for **every** $\theta>0$.
> >
> > Therefore, we can choose the value of $\theta$ that gives the smallest upper bound:
> > $$\boxed{
> > P(X\geq c)
> > \leq
> > \inf_{\theta>0}
> > \left\{
> > e^{-\theta c}E[e^{\theta X}]
> > \right\}.
> > $$
> >
> > This is the basic idea behind **Chernoff's bound**.
> >
> > The important strategy is:
> > $$\boxed{
> > \text{Transform}
> > \;\to\;
> > \text{apply Markov}
> > \;\to\;
> > \text{optimize}.
> > }$$
>
> > [!abstract]- Why $E[e^{\theta X}]$ Matters
> > Chernoff's bound introduces the quantity
> > $$\boxed{E[e^{\theta X}]}.$$
> >
> > This quantity contains information about the distribution of $X$ and is called the **moment-generating function (MGF)** when it is finite:
> > $$M_X(\theta)=E[e^{\theta X}].$$
> >
> > Thus, the study of Chernoff bounds naturally motivates the study of **MGFs**.
>
> > [!important]- Relationship Between the Three
> > The inequalities follow a common pattern:
> >
> > $$\boxed{
> > \begin{array}{c}
> > \text{Markov}\\
> > P(X\geq c)\leq\dfrac{E[X]}{c}
> > \end{array}
> > }$$
> >
> > $$\boxed{
> > \begin{array}{c}
> > \text{Chebyshev}\\
> > P(|X-E[X]|\geq t)
> > \leq\dfrac{\operatorname{Var}(X)}{t^2}
> > \end{array}
> > }$$
> >
> > $$\boxed{
> > \begin{array}{c}
> > \text{Chernoff}\\
> > P(X\geq c)
> > \leq
> > \inf_{\theta>0}
> > e^{-\theta c}E[e^{\theta X}]
> > \end{array}
> > }$$
> >
> > Conceptually:
> > $$\boxed{
> > \text{Markov}
> > \longrightarrow
> > \text{Chebyshev}
> > \longrightarrow
> > \text{Chernoff}
> > }$$
> > uses increasingly informative transformations of $X$ to obtain probability bounds.

> [!important]- Back to Law of Large Numbers — Proof Using Chebyshev's Inequality
>
> > [!abstract]- Goal
> > Let $\{X_i\}$ be i.i.d. random variables with
> > $$E[X_1]=\mu.$$
> >
> > Define the sample mean
> > $$\bar X_n=\frac1n\sum_{i=1}^nX_i.$$
> >
> > We want to show that
> > $$\boxed{P(|\bar X_n-\mu|>c)\to0\qquad\text{for every }c>0.}$$
> >
> > This means that the probability of the sample mean being more than $c$ away from the true mean becomes arbitrarily small as $n$ increases.
>
> > [!abstract]- Step 1: Center the Random Variables
> > Write
> > $$\bar X_n-\mu
> > =\frac1n\sum_{i=1}^n(X_i-\mu).$$
> >
> > Define
> > $$Y_i=X_i-\mu.$$
> >
> > Then $\{Y_i\}$ are still i.i.d. and
> > $$E[Y_i]=E[X_i-\mu]=\mu-\mu=0.$$
> >
> > Therefore, we can work with zero-mean random variables without loss of generality.
> >
> > Our goal becomes
> > $$P(|\bar Y_n|>c)\to0,$$
> > where
> > $$\bar Y_n=\frac1n\sum_{i=1}^nY_i.$$
>
> > [!abstract]- Attempt 1: Markov's Inequality
> > Since $|\bar Y_n|\geq0$, Markov's inequality gives
> > $$P(|\bar Y_n|>c)
> > \leq\frac{E[|\bar Y_n|]}{c}.$$
> >
> > Now
> > $$E[|\bar Y_n|]
> > =E\left[\left|\frac1n\sum_{i=1}^nY_i\right|\right]
> > =\frac1nE\left[\left|\sum_{i=1}^nY_i\right|\right].$$
> >
> > By the triangle inequality,
> > $$\left|\sum_{i=1}^nY_i\right|
> > \leq\sum_{i=1}^n|Y_i|.$$
> >
> > Therefore,
> > $$E[|\bar Y_n|]
> > \leq\frac1n\sum_{i=1}^nE[|Y_i|].$$
> >
> > Since the $Y_i$ are identically distributed,
> > $$E[|Y_i|]=E[|Y_1|].$$
> >
> > Hence
> > $$E[|\bar Y_n|]\leq E[|Y_1|].$$
> >
> > Thus,
> > $$P(|\bar Y_n|>c)
> > \leq\frac{E[|Y_1|]}{c}.$$
> >
> > The right-hand side does **not depend on $n$**.
> >
> > Therefore, this bound does not show that the probability goes to $0$.
>
> > [!warning]- Why Markov Is Not Enough Here
> > We need an upper bound that satisfies
> > $$\text{RHS}\to0\qquad(n\to\infty).$$
> >
> > But Markov gives
> > $$P(|\bar Y_n|>c)
> > \leq\frac{E[|Y_1|]}{c},$$
> > which is just a constant.
> >
> > So Markov's inequality is too weak for this proof.
> >
> > The problem is that taking the absolute value destroys the cancellation between positive and negative terms in the sum.
>
> > [!abstract]- Step 2: Use Chebyshev's Inequality
> > Chebyshev's inequality gives
> > $$P(|\bar Y_n-E[\bar Y_n]|>c)
> > \leq\frac{\operatorname{Var}(\bar Y_n)}{c^2}.$$
> >
> > Since $E[\bar Y_n]=0$,
> > $$P(|\bar Y_n|>c)
> > \leq\frac{\operatorname{Var}(\bar Y_n)}{c^2}.$$
> >
> > Now
> > $$\bar Y_n=\frac1n\sum_{i=1}^nY_i.$$
> >
> > Using
> > $$\operatorname{Var}(aX)=a^2\operatorname{Var}(X),$$
> > we get
> > $$\operatorname{Var}(\bar Y_n)
> > =\frac1{n^2}
> > \operatorname{Var}\left(\sum_{i=1}^nY_i\right).$$
>
> > [!abstract]- Step 3: Variance of the Sum
> > Because the $Y_i$ are independent, they are uncorrelated:
> > $$\operatorname{Cov}(Y_i,Y_j)=0,\qquad i\neq j.$$
> >
> > Therefore,
> > $$\operatorname{Var}\left(\sum_{i=1}^nY_i\right)
> > =\sum_{i=1}^n\operatorname{Var}(Y_i).$$
> >
> > Since the variables are identically distributed,
> > $$\operatorname{Var}(Y_i)=\operatorname{Var}(Y_1).$$
> >
> > Hence
> > $$\operatorname{Var}\left(\sum_{i=1}^nY_i\right)
> > =n\operatorname{Var}(Y_1).$$
> >
> > Therefore,
> > $$\operatorname{Var}(\bar Y_n)
> > =\frac1{n^2}\cdot n\operatorname{Var}(Y_1)
> > =\frac{\operatorname{Var}(Y_1)}{n}.$$
>
> > [!important]- Step 4: Apply Chebyshev
> > Substituting the variance into the Chebyshev bound:
> > $$P(|\bar Y_n|>c)
> > \leq
> > \frac{\operatorname{Var}(Y_1)}{nc^2}.$$
> >
> > Since $Y_1=X_1-\mu$,
> > $$\operatorname{Var}(Y_1)=\operatorname{Var}(X_1).$$
> >
> > Thus,
> > $$\boxed{
> > P(|\bar X_n-\mu|>c)
> > \leq
> > \frac{\operatorname{Var}(X_1)}{nc^2}
> > }.$$
> >
> > If
> > $$\operatorname{Var}(X_1)<\infty,$$
> > then
> > $$\frac{\operatorname{Var}(X_1)}{nc^2}\to0.$$
> >
> > Since probabilities are nonnegative,
> > $$0\leq P(|\bar X_n-\mu|>c)
> > \leq\frac{\operatorname{Var}(X_1)}{nc^2}\to0.$$
> >
> > Therefore,
> > $$\boxed{
> > P(|\bar X_n-\mu|>c)\to0.
> > }$$
>
> > [!tip]- Why This Proves the Weak LLN
> > We have shown that for every $c>0$,
> > $$P(|\bar X_n-\mu|>c)\to0.$$
> >
> > This is precisely
> > $$\boxed{\bar X_n\xrightarrow{P}\mu,}$$
> > i.e. convergence in probability.
> >
> > Convergence in probability to a constant also implies convergence in distribution:
> > $$\boxed{\bar X_n\xrightarrow{P}\mu
> > \quad\Longrightarrow\quad
> > \bar X_n\xrightarrow{d}\mu.}$$
>
> > [!warning]- Finiteness of Variance
> > The above **Chebyshev proof** requires
> > $$\operatorname{Var}(X_1)<\infty.$$
> >
> > However, the Weak Law of Large Numbers itself is more general.
> >
> > If $\{X_i\}$ are i.i.d. and
> > $$E[|X_1|]<\infty,$$
> > then the Weak Law still holds even when
> > $$\operatorname{Var}(X_1)=\infty.$$
> >
> > The proof of this more general result is beyond the scope of this course.
>
> > [!important]- Weak Law of Large Numbers
> > Let $\{X_i\}$ be i.i.d. random variables such that
> > $$E[|X_1|]<\infty,$$
> > and let
> > $$\bar X_n=\frac1n\sum_{i=1}^nX_i.$$
> >
> > Then, for every $c>0$,
> > $$\boxed{
> > \lim_{n\to\infty}
> > P(|\bar X_n-\mu|>c)=0,
> > }$$
> > where
> > $$\mu=E[X_1].$$
> >
> > Equivalently,
> > $$\boxed{\bar X_n\xrightarrow{P}\mu.}$$
> >
> > Consequently,
> > $$\boxed{\bar X_n\xrightarrow{d}\mu.}$$
> >
> > This is called the **Weak Law of Large Numbers (WLLN)**.
>
> > [!abstract]- Intuition
> > The key phenomenon is **averaging**.
> >
> > Each $X_i$ may fluctuate around $\mu$, but when we average many independent observations:
> > $$\bar X_n=\frac{X_1+\cdots+X_n}{n},$$
> > the random fluctuations partially cancel.
> >
> > In particular,
> > $$\operatorname{Var}(\bar X_n)
> > =\frac{\operatorname{Var}(X_1)}{n}
> > \longrightarrow0.$$
> >
> > So the sample mean becomes increasingly concentrated around the true mean.
> >
> > Plain English:
> > $$\boxed{
> > \text{With many i.i.d. observations, their sample mean gets close to the true mean.}
> > }$$

---

> [!important]- Beyond the Law of Large Numbers — Central Limit Theorem
>
> > [!abstract]- Setup
> > Let
> > $$X_1,X_2,\ldots$$
> > be i.i.d. random variables with
> > $$E[X_i]=\mu,\qquad \operatorname{Var}(X_i)=\sigma^2.$$
> >
> > Define the sum
> > $$S_n=\sum_{i=1}^nX_i.$$
> >
> > The sample mean is
> > $$\bar X_n=\frac{S_n}{n}.$$
>
> > [!abstract]- Gaussian Case
> > First suppose
> > $$X_i\sim N(\mu,\sigma^2).$$
> >
> > Since sums of independent Gaussian random variables are Gaussian,
> > $$S_n\sim N(n\mu,n\sigma^2).$$
> >
> > Therefore,
> > $$S_n-n\mu\sim N(0,n\sigma^2).$$
> >
> > Dividing by $\sigma$:
> > $$\frac{S_n-n\mu}{\sigma}\sim N(0,n).$$
>
> > [!abstract]- What LLN Tells Us
> > The Law of Large Numbers tells us that
> > $$\bar X_n=\frac{S_n}{n}\xrightarrow{P}\mu.$$
> >
> > Equivalently,
> > $$\frac{S_n}{n}\to\mu.$$
> >
> > Therefore,
> > $$\frac{S_n-n\mu}{n}\xrightarrow{P}0.$$
> >
> > This tells us that the difference between the sample mean and $\mu$ becomes small:
> > $$\bar X_n-\mu=\frac{S_n-n\mu}{n}\to0.$$
> >
> > But LLN does **not** tell us the scale of these fluctuations or their limiting distribution.
>
> > [!abstract]- The Important Scaling
> > Consider
> > $$\sqrt n\left(\frac{S_n-n\mu}{n\sigma}\right).$$
> >
> > Simplifying,
> > $$\boxed{
> > \sqrt n\left(\frac{S_n-n\mu}{n\sigma}\right)
> > =
> > \frac{S_n-n\mu}{\sigma\sqrt n}.
> > }$$
> >
> > In the Gaussian case,
> > $$S_n-n\mu\sim N(0,n\sigma^2),$$
> > so
> > $$\boxed{
> > \frac{S_n-n\mu}{\sigma\sqrt n}\sim N(0,1)
> > }$$
> > for **every $n$**.
> >
> > Thus, although
> > $$\frac{S_n-n\mu}{n\sigma}\to0,$$
> > multiplying it by $\sqrt n$ produces a non-degenerate random quantity:
> > $$\sqrt n\left(\frac{S_n-n\mu}{n\sigma}\right)
> > \sim N(0,1).$$
>
> > [!tip]- Why $\sqrt n$?
> > The variance of the sample mean is
> > $$\operatorname{Var}(\bar X_n)=\frac{\sigma^2}{n}.$$
> >
> > Therefore, its standard deviation is
> > $$\operatorname{SD}(\bar X_n)=\frac{\sigma}{\sqrt n}.$$
> >
> > So the typical size of the fluctuation
> > $$\bar X_n-\mu$$
> > is approximately
> > $$\frac{\sigma}{\sqrt n}.$$
> >
> > To obtain a quantity with constant scale, we therefore multiply by $\sqrt n$:
> > $$\frac{\sqrt n(\bar X_n-\mu)}{\sigma}
> > =
> > \frac{S_n-n\mu}{\sigma\sqrt n}.$$
>
> > [!important]- Central Limit Theorem
> > The remarkable fact is that the Gaussian result is **not limited to Gaussian random variables**.
> >
> > If
> > $$X_1,X_2,\ldots$$
> > are i.i.d. random variables satisfying
> > $$E[X_1]=\mu,\qquad
> > \operatorname{Var}(X_1)=\sigma^2<\infty,$$
> > then
> > $$\boxed{
> > \frac{S_n-n\mu}{\sigma\sqrt n}
> > \xrightarrow{d}N(0,1).
> > }$$
> >
> > Equivalently, since $\bar X_n=S_n/n$,
> > $$\boxed{
> > \frac{\sqrt n(\bar X_n-\mu)}{\sigma}
> > \xrightarrow{d}N(0,1).
> > }$$
> >
> > This is the **Central Limit Theorem (CLT)**.
>
> > [!abstract]- LLN vs CLT
> > The two theorems answer different questions.
> >
> > **Law of Large Numbers:**
> > $$\boxed{\bar X_n\xrightarrow{P}\mu}$$
> >
> > It tells us:
> > $$\text{Where does the sample mean go?}$$
> >
> > Answer: it goes to $\mu$.
> >
> > **Central Limit Theorem:**
> > $$\boxed{
> > \frac{\sqrt n(\bar X_n-\mu)}{\sigma}
> > \xrightarrow{d}N(0,1)
> > }$$
> >
> > It tells us:
> > $$\text{How does the sample mean fluctuate around }\mu\text{?}$$
> >
> > Answer: after scaling by its standard deviation, the fluctuations become approximately standard normal.
>
> > [!example]- Intuition
> > Think of the sample mean as
> > $$\bar X_n=\mu+\text{random error}.$$
> >
> > LLN says
> > $$\text{random error}\to0.$$
> >
> > CLT says the error is typically of size
> > $$\frac{\sigma}{\sqrt n},$$
> > and after rescaling,
> > $$\frac{\bar X_n-\mu}{\sigma/\sqrt n}
> > \xrightarrow{d}N(0,1).
> > $$
> >
> > So:
> > $$\boxed{
> > \text{LLN: convergence to the mean}
> > \qquad
> > \text{CLT: distribution of the fluctuations}
> > }$$
>
> > [!important]- Big Picture
> > For i.i.d. observations with finite mean and variance:
> >
> > $$\bar X_n\xrightarrow{P}\mu
> > \qquad\text{(LLN)}$$
> >
> > while
> >
> > $$\frac{\sqrt n(\bar X_n-\mu)}{\sigma}
> > \xrightarrow{d}N(0,1)
> > \qquad\text{(CLT)}.$$
> >
> > The LLN explains **consistency of averaging**.
> >
> > The CLT explains the **approximately normal behavior of the error around the mean**.
> >
> > The CLT is therefore the foundation for many statistical tools such as confidence intervals, hypothesis tests, and normal approximations.

> [!important]- Moment Generating Function (MGF)
>
> > [!abstract]- Motivation
> > The **Central Limit Theorem (CLT)** will be proved using **characteristic functions**.
> >
> > Before introducing characteristic functions, we first study expectations of exponentials of the form
> > $$E[e^{tX}].$$
> >
> > This leads to the **moment generating function (MGF)**.
>
> > [!abstract]- Definition
> > The moment generating function of a random variable $X$ is
> > $$\boxed{M_X(t)=E[e^{tX}].}$$
> >
> > Here, $t\in\mathbb R$ is a parameter.
> >
> > Since
> > $$e^{tX}\geq0,$$
> > the expectation always exists in the extended sense, although it may be
> > $$+\infty.$$
>
> > [!tip]- Why Is It Called "Moment Generating"?
> > Differentiate the MGF:
> > $$M_X(t)=E[e^{tX}].$$
> >
> > Assuming we can interchange differentiation and expectation,
> > $$M_X'(t)
> > =E\left[\frac{d}{dt}e^{tX}\right]
> > =E[Xe^{tX}].$$
> >
> > Evaluating at $t=0$:
> > $$M_X'(0)
> > =E[Xe^0]
> > =E[X].$$
> >
> > Therefore,
> > $$\boxed{E[X]=M_X'(0).}$$
> >
> > Differentiating repeatedly,
> > $$M_X^{(k)}(t)=E[X^ke^{tX}],$$
> > so at $t=0$,
> > $$\boxed{M_X^{(k)}(0)=E[X^k].}$$
> >
> > Thus, the MGF generates the moments of $X$:
> > $$E[X],\ E[X^2],\ E[X^3],\ldots$$
>
> > [!warning]- Technical Condition
> > The step
> > $$M_X'(t)=E[Xe^{tX}]$$
> > requires justification for interchanging differentiation and expectation.
> >
> > For this course, we will not focus on the technical conditions required for this step.
> >
> > Also, an MGF may fail to be finite, so statements involving moments through derivatives are typically made where the MGF exists in a neighborhood of $0$.
>
> > [!example]- Example: Exponential Distribution
> > Let
> > $$X\sim\operatorname{Exp}(\lambda),$$
> > with density
> > $$f_X(x)=\lambda e^{-\lambda x},\qquad x\geq0.$$
> >
> > By definition,
> > $$M_X(t)=E[e^{tX}].$$
> >
> > Using the density,
> > $$M_X(t)
> > =\int_0^\infty e^{tx}\lambda e^{-\lambda x}\,dx.$$
> >
> > Combining the exponentials:
> > $$M_X(t)
> > =\lambda\int_0^\infty e^{-(\lambda-t)x}\,dx.$$
>
> > [!abstract]- When Is the Integral Finite?
> > The integral
> > $$\int_0^\infty e^{-(\lambda-t)x}\,dx$$
> > is finite only when
> > $$\lambda-t>0,$$
> > i.e.
> > $$t<\lambda.$$
> >
> > For $t<\lambda$,
> > $$\int_0^\infty e^{-(\lambda-t)x}\,dx
> > =\frac1{\lambda-t}.$$
> >
> > Therefore,
> > $$\boxed{
> > M_X(t)=\frac{\lambda}{\lambda-t},
> > \qquad t<\lambda.
> > }$$
> >
> > For $t\geq\lambda$, the integral diverges:
> > $$M_X(t)=\infty.$$
> >
> > Hence,
> > $$\boxed{
> > M_X(t)=
> > \begin{cases}
> > \dfrac{\lambda}{\lambda-t},&t<\lambda,\\[6pt]
> > \infty,&t\geq\lambda.
> > \end{cases}
> > }$$
>
> > [!example]- Recovering the Mean of an Exponential
> > For $X\sim\operatorname{Exp}(\lambda)$,
> > $$M_X(t)=\frac{\lambda}{\lambda-t}.$$
> >
> > Differentiate:
> > $$M_X'(t)=\frac{\lambda}{(\lambda-t)^2}.$$
> >
> > Therefore,
> > $$E[X]=M_X'(0)=\frac{\lambda}{\lambda^2}=\frac1\lambda.$$
> >
> > This agrees with the known mean of the exponential distribution.
>
> > [!important]- MGF of a Sum of Independent Random Variables
> > Suppose $X$ and $Y$ are independent.
> >
> > Then
> > $$M_{X+Y}(t)
> > =E[e^{t(X+Y)}].$$
> >
> > Since
> > $$e^{t(X+Y)}=e^{tX}e^{tY},$$
> > we have
> > $$M_{X+Y}(t)
> > =E[e^{tX}e^{tY}].$$
> >
> > Independence implies that the expectation factors:
> > $$E[e^{tX}e^{tY}]
> > =E[e^{tX}]E[e^{tY}].$$
> >
> > Hence,
> > $$\boxed{
> > M_{X+Y}(t)=M_X(t)M_Y(t).
> > }$$
> >
> > More generally, for independent $X_1,\ldots,X_n$,
> > $$\boxed{
> > M_{\sum_{i=1}^nX_i}(t)
> > =\prod_{i=1}^nM_{X_i}(t).
> > }$$
>
> > [!tip]- Why This Property Is Useful for the CLT
> > The CLT deals with sums:
> > $$S_n=X_1+\cdots+X_n.$$
> >
> > For independent variables, their MGF satisfies
> > $$M_{S_n}(t)=\prod_{i=1}^nM_{X_i}(t).$$
> >
> > If the variables are identically distributed,
> > $$\boxed{M_{S_n}(t)=[M_X(t)]^n.}$$
> >
> > This makes MGFs particularly useful for studying the distribution of sums.
> >
> > However, the course will next introduce **characteristic functions**, which are closely related to MGFs but have an important advantage: they always exist because
> > $$|e^{itX}|=1.$$

> [!important]- Characteristic Function
>
> > [!abstract]- Motivation
> > The moment generating function
> > $$M_X(t)=E[e^{tX}]$$
> > is useful, but it has one important limitation: it may be infinite.
> >
> > To avoid this problem, we use complex numbers. Let
> > $$i=\sqrt{-1}.$$
> >
> > The key idea is to replace $e^{tX}$ with
> > $$e^{itX}.$$
> >
> > Since
> > $$|e^{itX}|=1,$$
> > the expectation is always well-defined and finite.
>
> > [!abstract]- Definition
> > The **characteristic function** of a random variable $X$ is
> > $$\boxed{\phi_X(t)=E[e^{itX}],\qquad t\in\mathbb R.}$$
> >
> > Using Euler's formula,
> > $$e^{itX}=\cos(tX)+i\sin(tX),$$
> > so
> > $$\boxed{
> > \phi_X(t)
> > =E[\cos(tX)]+iE[\sin(tX)].
> > }$$
> >
> > Thus, $\phi_X(t)$ is generally a complex-valued function.
>
> > [!tip]- Why the Characteristic Function Always Exists
> > Since
> > $$|e^{itX}|=1,$$
> > we have
> > $$E[|e^{itX}|]=1.$$
> >
> > By the triangle inequality for expectations,
> > $$|\phi_X(t)|
> > =|E[e^{itX}]|
> > \leq E[|e^{itX}|]
> > =1.$$
> >
> > Therefore,
> > $$\boxed{|\phi_X(t)|\leq1\qquad\text{for all }t.}$$
> >
> > This is the key advantage over MGFs: **a characteristic function is always finite.**
>
> > [!abstract]- Basic Properties
> > If $\phi$ is the characteristic function of some random variable, then:
> >
> > $$\boxed{\phi(0)=1}$$
> > because
> > $$\phi(0)=E[e^{i0X}]=E[1]=1.$$
> >
> > Also,
> > $$\boxed{|\phi(t)|\leq1.}$$
> >
> > Furthermore, $\phi$ is **uniformly continuous** on $\mathbb R$.
> >
> > A deeper property is **positive definiteness**:
> > $$\boxed{
> > \sum_{j,k=1}^n
> > \phi(t_j-t_k)z_j\overline{z_k}\geq0
> > }$$
> > for all real numbers $t_1,\ldots,t_n$ and complex numbers $z_1,\ldots,z_n$.
>
> > [!important]- Characterization Theorem
> > Remarkably, the above properties are not merely necessary.
> >
> > A function $\phi:\mathbb R\to\mathbb C$ is a characteristic function **if and only if** it satisfies:
> >
> > $$\boxed{
> > \begin{aligned}
> > &\phi(0)=1,\\
> > &|\phi(t)|\leq1,\\
> > &\phi\text{ is uniformly continuous},\\
> > &\phi\text{ is positive definite}.
> > \end{aligned}}
> > $$
> >
> > This means characteristic functions can be characterized entirely through properties of the function itself.
>
> > [!abstract]- Moments from the Characteristic Function
> > Similar to the MGF, moments can be obtained from derivatives of $\phi_X$.
> >
> > Assuming the required moments/regularity conditions exist,
> > $$\phi_X^{(k)}(t)
> > =E[(iX)^ke^{itX}].$$
> >
> > Setting $t=0$:
> > $$\phi_X^{(k)}(0)=E[(iX)^k]
> > =i^kE[X^k].$$
> >
> > Therefore,
> > $$\boxed{
> > E[X^k]=i^{-k}\phi_X^{(k)}(0).
> > }$$
> >
> > In particular,
> > $$\phi_X'(0)=iE[X],$$
> > so
> > $$\boxed{E[X]=\frac{\phi_X'(0)}{i}=-i\phi_X'(0).}$$
>
> > [!abstract]- Expansion Around $t=0$
> > If
> > $$E[|X|^k]<\infty,$$
> > then the characteristic function has the expansion
> > $$\boxed{
> > \phi_X(t)
> > =
> > \sum_{j=0}^{k}
> > \frac{E[X^j]}{j!}(it)^j
> > +o(t^k).
> > }$$
> >
> > Here,
> > $$g(t)=o(t^k)$$
> > means
> > $$\boxed{
> > \frac{g(t)}{t^k}\to0
> > \qquad\text{as }t\to0.
> > }$$
> >
> > Thus, near $t=0$, the characteristic function is determined by the moments of $X$.
>
> > [!abstract]- Characteristic Function of a Sum
> > If $X$ and $Y$ are independent, then
> > $$\phi_{X+Y}(t)
> > =E[e^{it(X+Y)}].$$
> >
> > Since
> > $$e^{it(X+Y)}=e^{itX}e^{itY},$$
> > independence gives
> > $$E[e^{itX}e^{itY}]
> > =E[e^{itX}]E[e^{itY}].$$
> >
> > Therefore,
> > $$\boxed{
> > \phi_{X+Y}(t)
> > =\phi_X(t)\phi_Y(t).
> > }$$
> >
> > More generally, for independent $X_1,\ldots,X_n$,
> > $$\boxed{
> > \phi_{\sum_{i=1}^nX_i}(t)
> > =\prod_{i=1}^n\phi_{X_i}(t).
> > }$$
> >
> > This property is extremely important when studying sums of independent random variables.
>
> > [!example]- Bernoulli Distribution
> > Let
> > $$X\sim\operatorname{Ber}(p),$$
> > and let
> > $$q=1-p.$$
> >
> > Since $X$ takes values $1$ and $0$:
> > $$\phi_X(t)
> > =pe^{it}+qe^{i0}.$$
> >
> > Therefore,
> > $$\boxed{\phi_X(t)=pe^{it}+q.}$$
>
> > [!example]- Binomial Distribution
> > A binomial random variable can be written as a sum of independent Bernoulli random variables:
> > $$X=\sum_{i=1}^nX_i,
> > \qquad X_i\sim\operatorname{Ber}(p).$$
> >
> > Therefore,
> > $$\phi_X(t)
> > =\prod_{i=1}^n\phi_{X_i}(t)
> > =(pe^{it}+q)^n.$$
> >
> > Hence,
> > $$\boxed{
> > \phi_X(t)=(pe^{it}+1-p)^n.
> > }$$
>
> > [!example]- Linear Transformation
> > Let
> > $$Y=aX+b.$$
> >
> > Then
> > $$\phi_Y(t)
> > =E[e^{it(aX+b)}].$$
> >
> > Separate the terms:
> > $$\phi_Y(t)
> > =e^{itb}E[e^{i(at)X}].$$
> >
> > Therefore,
> > $$\boxed{
> > \phi_Y(t)=e^{itb}\phi_X(at).
> > }$$
> >
> > This transformation property is analogous to properties of the **Fourier transform**.
>
> > [!example]- Exponential Distribution
> > Let
> > $$X\sim\operatorname{Exp}(\lambda).$$
> >
> > Its characteristic function is
> > $$\phi_X(t)
> > =\int_0^\infty e^{itx}\lambda e^{-\lambda x}\,dx.$$
> >
> > Combining the exponentials:
> > $$\phi_X(t)
> > =\lambda\int_0^\infty e^{-(\lambda-it)x}\,dx.$$
> >
> > The result is
> > $$\boxed{
> > \phi_X(t)=\frac{\lambda}{\lambda-it}.
> > }$$
> >
> > Unlike the MGF, this expression is finite for **every real $t$**.
>
> > [!example]- Standard Normal Distribution
> > Let
> > $$X\sim N(0,1).$$
> >
> > Its MGF is
> > $$M_X(t)=E[e^{tX}].$$
> >
> > Evaluating the Gaussian integral by completing the square gives
> > $$\boxed{M_X(t)=e^{t^2/2}.}$$
> >
> > Replacing $t$ by $it$ gives the characteristic function:
> > $$\phi_X(t)=M_X(it).$$
> >
> > Hence,
> > $$\boxed{
> > \phi_X(t)=e^{-t^2/2}.
> > }$$
>
> > [!example]- General Normal Distribution
> > Let
> > $$X\sim N(\mu,\sigma^2).$$
> >
> > Write
> > $$X=\sigma Y+\mu,$$
> > where
> > $$Y\sim N(0,1).$$
> >
> > Using the linear transformation property:
> > $$\phi_X(t)
> > =e^{i\mu t}\phi_Y(\sigma t).$$
> >
> > Since
> > $$\phi_Y(t)=e^{-t^2/2},$$
> > we obtain
> > $$\boxed{
> > \phi_X(t)
> > =
> > \exp\left(
> > i\mu t-\frac{\sigma^2t^2}{2}
> > \right).
> > }$$
>
> > [!example]- Cauchy Distribution
> > Let $X$ have the standard Cauchy density
> > $$f_X(x)=\frac1{\pi(1+x^2)}.$$
> >
> > Its characteristic function is
> > $$\phi_X(t)
> > =\int_{-\infty}^{\infty}
> > e^{itx}\frac1{\pi(1+x^2)}\,dx.$$
> >
> > Evaluating this integral requires more care than the exponential or Gaussian examples; treating $i$ simply as an ordinary constant inside a real-variable integration argument does not give the needed justification.
> >
> > The result is
> > $$\boxed{\phi_X(t)=e^{-|t|}.}$$
> >
> > Notice that $\phi_X(t)$ is **not differentiable at $t=0$** because of the $|t|$.
> >
> > This is consistent with the fact that the Cauchy distribution does not have a finite first moment:
> > $$E[|X|]=\infty.$$
>
> > [!important]- MGF vs Characteristic Function
> > $$\boxed{
> > M_X(t)=E[e^{tX}]
> > }$$
> >
> > $$\boxed{
> > \phi_X(t)=E[e^{itX}]
> > }$$
> >
> > The key difference is:
> >
> > $$e^{tX}\geq0$$
> > but may have infinite expectation, whereas
> > $$|e^{itX}|=1.$$
> >
> > Therefore:
> > $$\boxed{
> > \text{MGF may not exist}
> > \qquad\text{but}\qquad
> > \text{CF always exists}.
> > }$$
> >
> > Both have the useful property that independence turns sums into products:
> > $$M_{X+Y}(t)=M_X(t)M_Y(t),$$
> > $$\phi_{X+Y}(t)=\phi_X(t)\phi_Y(t).$$
> >
> > This product property is one of the main reasons characteristic functions are powerful for proving the **Central Limit Theorem**.

> [!important]- Joint Characteristic Function
>
> > [!abstract]- Characteristic Function Determines the Distribution
> > The characteristic function contains enough information to completely determine the distribution of a random variable.
> >
> > In other words, we can recover the distribution of $X$ from $\phi_X$ using a **Fourier inversion formula**.
> >
> > We will not need the explicit inversion formula in this course.
> >
> > Therefore, two random variables have the same distribution if and only if their characteristic functions are identical:
> > $$\boxed{
> > X\overset{d}=Y
> > \iff
> > \phi_X(t)=\phi_Y(t)\quad\forall t\in\mathbb R.
> > }$$
> >
> > Here,
> > $$X\overset{d}=Y$$
> > means that $X$ and $Y$ have the same distribution.
>
> > [!tip]- Why This Is Important
> > The characteristic function can be viewed as the **Fourier transform of the probability distribution**.
> >
> > Thus:
> > $$\boxed{
> > \text{distribution of }X
> > \longleftrightarrow
> > \phi_X
> > }$$
> >
> > This means that instead of working directly with probability distributions, we can sometimes work with characteristic functions and recover the distribution afterward.
>
> > [!abstract]- Joint Characteristic Function
> > For a random vector
> > $$(X,Y),$$
> > we define its **joint characteristic function** by
> > $$\boxed{
> > \phi_{X,Y}(s,t)
> > =
> > E\left[e^{isX+itY}\right],
> > \qquad s,t\in\mathbb R.
> > }$$
> >
> > Compare this with the ordinary characteristic function:
> > $$\phi_X(s)=E[e^{isX}],$$
> > $$\phi_Y(t)=E[e^{itY}].$$
> >
> > The joint characteristic function captures information about the **pair $(X,Y)$ together**, including their dependence structure.
>
> > [!important]- Independence Characterized by the Joint Characteristic Function
> > The random variables $X$ and $Y$ are independent **if and only if**
> > $$\boxed{
> > \phi_{X,Y}(s,t)
> > =
> > \phi_X(s)\phi_Y(t)
> > \qquad\forall s,t\in\mathbb R.
> > }$$
> >
> > This gives a complete characterization of independence.
>
> > [!abstract]- Why Independence Gives the Product
> > Start with the joint characteristic function:
> > $$\phi_{X,Y}(s,t)
> > =E[e^{isX+itY}].$$
> >
> > Since
> > $$e^{isX+itY}
> > =e^{isX}e^{itY},$$
> > we have
> > $$\phi_{X,Y}(s,t)
> > =E[e^{isX}e^{itY}].$$
> >
> > If $X$ and $Y$ are independent, then $e^{isX}$ and $e^{itY}$ are also independent. Therefore,
> > $$E[e^{isX}e^{itY}]
> > =
> > E[e^{isX}]E[e^{itY}].$$
> >
> > Hence,
> > $$\boxed{
> > \phi_{X,Y}(s,t)
> > =
> > \phi_X(s)\phi_Y(t).
> > }$$
>
> > [!important]- The Converse
> > The remarkable part is that the converse also holds.
> >
> > If
> > $$\phi_{X,Y}(s,t)
> > =
> > \phi_X(s)\phi_Y(t)
> > \qquad\forall s,t,$$
> > then $X$ and $Y$ are independent.
> >
> > Why?
> >
> > The product
> > $$\phi_X(s)\phi_Y(t)$$
> > is exactly the joint characteristic function of two independent random variables having the marginal distributions of $X$ and $Y$.
> >
> > Since characteristic functions uniquely determine distributions, the joint distribution must equal the product distribution.
> >
> > Therefore,
> > $$\boxed{
> > X\perp Y
> > \iff
> > \phi_{X,Y}(s,t)=\phi_X(s)\phi_Y(t).
> > }$$
>
> > [!tip]- Important Connection
> > There are two closely related facts:
> >
> > **For sums:**
> > $$\boxed{
> > \phi_{X+Y}(t)=\phi_X(t)\phi_Y(t)
> > \quad\text{if }X\perp Y.
> > }$$
> >
> > **For independence itself:**
> > $$\boxed{
> > \phi_{X,Y}(s,t)=\phi_X(s)\phi_Y(t)
> > \iff X\perp Y.
> > }$$
> >
> > The first concerns the **distribution of the sum**.
> >
> > The second completely characterizes the **dependence between $X$ and $Y$**.

---

> [!important]- Jointly Gaussian Random Vectors
>
> > [!abstract]- From Univariate to Multivariate Normal
> > We know the univariate normal distribution:
> > $$X\sim N(\mu,\sigma^2).$$
> >
> > We also encountered the bivariate normal distribution.
> >
> > The multivariate normal distribution generalizes this idea to an $n$-dimensional random vector:
> > $$X=(X_1,\ldots,X_n)^T.$$
>
> > [!abstract]- Multivariate Normal Distribution
> > Let
> > $$\mu\in\mathbb R^n$$
> > be a mean vector and let
> > $$V\in\mathbb R^{n\times n}$$
> > be a symmetric positive definite matrix.
> >
> > A random vector $X$ has a **multivariate normal distribution** if its joint density is
> > $$\boxed{
> > f_X(x)
> > =
> > \frac{1}
> > {(2\pi)^{n/2}\det(V)^{1/2}}
> > \exp\left\{
> > -\frac12(x-\mu)^TV^{-1}(x-\mu)
> > \right\}.
> > }$$
> >
> > We write
> > $$\boxed{X\sim N(\mu,V).}$$
> >
> > Here:
> > $$\mu=E[X]$$
> > is the mean vector, and
> > $$V=\operatorname{Cov}(X)$$
> > is the covariance matrix.
>
> > [!abstract]- Mean Vector and Covariance Matrix
> > The mean vector is
> > $$\mu=
> > \begin{pmatrix}
> > E[X_1]\\
> > \vdots\\
> > E[X_n]
> > \end{pmatrix}.$$
> >
> > The covariance matrix is
> > $$V=
> > \begin{pmatrix}
> > \operatorname{Cov}(X_1,X_1)&\cdots&\operatorname{Cov}(X_1,X_n)\\
> > \vdots&\ddots&\vdots\\
> > \operatorname{Cov}(X_n,X_1)&\cdots&\operatorname{Cov}(X_n,X_n)
> > \end{pmatrix}.$$
> >
> > Therefore,
> > $$\boxed{V_{ij}=\operatorname{Cov}(X_i,X_j).}$$
> >
> > In particular,
> > $$V_{ii}=\operatorname{Var}(X_i).$$
>
> > [!warning]- Limitation of the Density Definition
> > The density-based definition is mathematically correct but can be difficult to work with.
> >
> > More importantly, it only directly describes the case where the covariance matrix is positive definite and the random vector has a joint density.
> >
> > A more useful definition of a jointly Gaussian random vector does **not require a joint density**.
>
> > [!important]- Definition: Jointly Gaussian Random Variables
> > A collection of random variables
> > $$X_1,\ldots,X_n$$
> > is called **jointly Gaussian** if for every vector
> > $$a=(a_1,\ldots,a_n)^T\in\mathbb R^n,$$
> > the linear combination
> > $$\boxed{
> > a_1X_1+\cdots+a_nX_n
> > }$$
> > has a Gaussian distribution.
> >
> > Equivalently,
> > $$\boxed{a^TX\text{ is Gaussian for every }a\in\mathbb R^n.}$$
> >
> > This definition is more general because $(X_1,\ldots,X_n)$ need not have a joint density.
>
> > [!example]- Example Without a Joint Density
> > Let
> > $$X\sim N(0,1)$$
> > and consider the random vector
> > $$\begin{pmatrix}X\\X\end{pmatrix}.$$
> >
> > For any $a=(a_1,a_2)^T$,
> > $$a^TX=a_1X+a_2X=(a_1+a_2)X,$$
> > which is Gaussian.
> >
> > Therefore,
> > $$\boxed{(X,X)\text{ is jointly Gaussian}.}$$
> >
> > However, $(X,X)$ lies entirely on the line
> > $$x_1=x_2,$$
> > so its distribution does not have a two-dimensional density with respect to ordinary area.
> >
> > This illustrates why the linear-combination definition is more general.
>
> > [!abstract]- Joint Characteristic Function
> > Let
> > $$X=(X_1,\ldots,X_n)^T$$
> > be jointly Gaussian.
> >
> > Its joint characteristic function is
> > $$\phi_X(t)
> > =
> > E\left[
> > \exp\left\{
> > i(t_1X_1+\cdots+t_nX_n)
> > \right\}
> > \right].$$
> >
> > In vector notation,
> > $$\boxed{
> > \phi_X(t)=E[e^{it^TX}],
> > \qquad t\in\mathbb R^n.
> > }$$
>
> > [!abstract]- Why the Characteristic Function Has a Simple Form
> > Since $X$ is jointly Gaussian, every linear combination
> > $$t^TX=t_1X_1+\cdots+t_nX_n$$
> > is a univariate Gaussian random variable.
> >
> > Its mean is
> > $$E[t^TX]
> > =t^TE[X]
> > =t^T\mu.$$
> >
> > Its variance is
> > $$\operatorname{Var}(t^TX)
> > =t^TVt.$$
> >
> > Therefore,
> > $$t^TX\sim N(t^T\mu,t^TVt).$$
>
> > [!important]- Characteristic Function of a Jointly Gaussian Vector
> > For a Gaussian random variable $Z\sim N(m,s^2)$,
> > $$\phi_Z(1)=E[e^{iZ}]
> > =e^{im-s^2/2}.$$
> >
> > Applying this to
> > $$Z=t^TX\sim N(t^T\mu,t^TVt),$$
> > gives
> > $$\boxed{
> > \phi_X(t)
> > =
> > \exp\left\{
> > it^T\mu-\frac12t^TVt
> > \right\}.
> > }$$
> >
> > Thus the entire joint distribution is encoded by just two objects:
> > $$\boxed{\mu\quad\text{and}\quad V.}$$
>
> > [!tip]- Key Intuition
> > The defining property of a jointly Gaussian vector is:
> > $$\boxed{
> > \text{Every linear combination of its components is Gaussian.}
> > }$$
> >
> > For any direction $t$,
> > $$t^TX$$
> > is Gaussian with
> > $$E[t^TX]=t^T\mu,$$
> > $$\operatorname{Var}(t^TX)=t^TVt.$$
> >
> > This is why the characteristic function takes the elegant quadratic form
> > $$\boxed{
> > \phi_X(t)=
> > e^{\,it^T\mu-\frac12t^TVt}.
> > }$$
>
> > [!important]- Important Special Case
> > If
> > $$V=I_n,\qquad\mu=0,$$
> > then
> > $$X\sim N(0,I_n),$$
> > and
> > $$\phi_X(t)
> > =e^{-\frac12t^Tt}
> > =e^{-\frac12\|t\|^2}.$$
> >
> > In this case, the components are independent standard normal random variables:
> > $$X_i\overset{\text{i.i.d.}}{\sim}N(0,1).$$
>
> > [!abstract]- Connection to the Univariate Case
> > For $n=1$:
> > $$X\sim N(\mu,\sigma^2),$$
> > so
> > $$\mu=\mu,\qquad V=\sigma^2.$$
> >
> > The multivariate characteristic function becomes
> > $$\phi_X(t)
> > =
> > \exp\left\{
> > i\mu t-\frac12\sigma^2t^2
> > \right\},$$
> > which is exactly the familiar characteristic function of
> > $$N(\mu,\sigma^2).$$

> [!important]- Characteristic Functions and Convergence in Distribution
>
> > [!abstract]- Characteristic Function Determines the Distribution
> > The characteristic function
> > $$\phi_X(t)=E[e^{itX}]$$
> > contains all the information about the distribution of $X$.
> >
> > In fact, $\phi_X$ can be viewed as the **Fourier transform of the distribution of $X$**.
> >
> > There is an inversion formula that allows us to recover the distribution from $\phi_X$, but we will not need the formula itself.
> >
> > Therefore,
> > $$\boxed{
> > X\overset{d}=Y
> > \iff
> > \phi_X(t)=\phi_Y(t)
> > \quad\forall t\in\mathbb R.
> > }$$
>
> > [!abstract]- Characteristic Functions and Convergence
> > A very useful theorem connects characteristic functions with convergence in distribution.
> >
> > Let
> > $$X_1,X_2,\ldots$$
> > be a sequence of random variables.
> >
> > Then
> > $$\boxed{
> > X_n\xrightarrow{d}X
> > \iff
> > \phi_{X_n}(t)\to\phi_X(t)
> > \quad\forall t\in\mathbb R.
> > }$$
> >
> > In words:
> >
> > $$\boxed{
> > \text{Convergence in distribution}
> > \iff
> > \text{pointwise convergence of characteristic functions}.
> > }$$
>
> > [!tip]- Why This Is Powerful
> > Directly proving
> > $$X_n\xrightarrow{d}X$$
> > using CDFs can be difficult, especially when $X_n$ is a complicated sum of random variables.
> >
> > Characteristic functions provide an alternative:
> >
> > $$X_n
> > \longrightarrow
> > X
> > \quad\text{in distribution}$$
> >
> > can be replaced by checking
> >
> > $$\phi_{X_n}(t)
> > \longrightarrow
> > \phi_X(t).$$
> >
> > This is particularly useful for sums because independent random variables satisfy
> > $$\phi_{X+Y}(t)
> > =\phi_X(t)\phi_Y(t).$$
> >
> > Therefore, complicated sums turn into products of characteristic functions.
>
> > [!important]- Method of Characteristic Functions
> > The strategy
> > $$\boxed{
> > \text{Find }\phi_{X_n}(t)
> > \;\longrightarrow\;
> > \text{find its limit}
> > \;\longrightarrow\;
> > \text{identify the limiting CF}
> > \;\longrightarrow\;
> > X_n\xrightarrow{d}X
> > }$$
> > is called the **method of characteristic functions**.
> >
> > This is the method we will use to prove the **Central Limit Theorem**.
>
> > [!abstract]- Converse-Type Result
> > There is an even stronger result.
> >
> > Suppose
> > $$\phi_{X_n}(t)\to\phi(t)
> > \qquad\text{for every }t\in\mathbb R.$$
> >
> > If the limiting function $\phi$ is **continuous at $0$**, then:
> >
> > $$\boxed{
> > \phi\text{ is the characteristic function of some random variable }X
> > }$$
> >
> > and
> > $$\boxed{
> > X_n\xrightarrow{d}X.
> > }$$
> >
> > Thus, we do **not** need to know the limiting random variable $X$ beforehand.
> >
> > We can:
> > $$\boxed{
> > \text{calculate the limiting CF}
> > \;\to\;
> > \text{verify continuity at }0
> > \;\to\;
> > \text{identify the distribution}.
> > }$$
>
> > [!warning]- Why Continuity at $0$ Matters
> > A pointwise limit of characteristic functions is not automatically a characteristic function.
> >
> > The additional condition
> > $$\boxed{\phi\text{ is continuous at }0}$$
> > guarantees that the limiting function corresponds to a genuine probability distribution.
> >
> > This result is especially useful in the CLT, where we will calculate the limiting characteristic function and show that it is
> > $$e^{-t^2/2},$$
> > which is the characteristic function of $N(0,1)$.
>
> > [!important]- CLT Roadmap
> > For the Central Limit Theorem, we will consider
> > $$Z_n=
> > \frac{S_n-n\mu}{\sigma\sqrt n}.$$
> >
> > The goal is to prove
> > $$Z_n\xrightarrow{d}N(0,1).$$
> >
> > Using characteristic functions, the proof becomes:
> >
> > $$\boxed{
> > \phi_{Z_n}(t)
> > \longrightarrow
> > e^{-t^2/2}
> > }$$
> >
> > Since
> > $$e^{-t^2/2}$$
> > is the characteristic function of $N(0,1)$, we conclude
> > $$\boxed{
> > Z_n\xrightarrow{d}N(0,1).
> > }$$
> >
> > This is the **method of characteristic functions** in action.

> [!important]- Central Limit Theorem — Proof Using Characteristic Functions
>
> > [!abstract]- Theorem
> > Let
> > $$X_1,X_2,\ldots$$
> > be i.i.d. random variables with
> > $$E[X_i]=\mu,\qquad \operatorname{Var}(X_i)=\sigma^2<\infty.$$
> >
> > Define
> > $$S_n=\sum_{j=1}^nX_j.$$
> >
> > Then the **Central Limit Theorem** states
> > $$\boxed{
> > \frac{S_n-n\mu}{\sigma\sqrt n}
> > \xrightarrow{d}N(0,1).
> > }$$
> >
> > Equivalently,
> > $$\boxed{
> > \frac{\sqrt n(\bar X_n-\mu)}{\sigma}
> > \xrightarrow{d}N(0,1).
> > }$$
> >
> > The proof below uses the **method of characteristic functions**.
>
> > [!abstract]- Step 1: Standardize Each Random Variable
> > Define
> > $$Y_j=\frac{X_j-\mu}{\sigma}.$$
> >
> > Then the $Y_j$ are still i.i.d. and
> > $$E[Y_j]=0,$$
> > $$\operatorname{Var}(Y_j)=1.$$
> >
> > Let $\phi_Y$ denote their common characteristic function.
>
> > [!abstract]- Step 2: Expand the Characteristic Function Near $0$
> > Since
> > $$E[Y]=0,\qquad E[Y^2]=1,$$
> > the moment expansion of the characteristic function gives
> > $$\phi_Y(t)
> > =
> > 1+E[Y](it)
> > +\frac{E[Y^2]}{2!}(it)^2
> > +o(t^2).$$
> >
> > Substituting the moments:
> > $$\phi_Y(t)
> > =1+0+\frac12(it)^2+o(t^2).$$
> >
> > Since
> > $$i^2=-1,$$
> > we obtain
> > $$\boxed{
> > \phi_Y(t)=1-\frac{t^2}{2}+o(t^2).
> > }$$
> >
> > This approximation is the key ingredient of the proof.
>
> > [!abstract]- Step 3: Define the Normalized Sum
> > Define
> > $$U_n=\frac{S_n-n\mu}{\sigma\sqrt n}.$$
> >
> > Since
> > $$S_n-n\mu
> > =\sum_{j=1}^n(X_j-\mu),$$
> > we have
> > $$U_n
> > =\frac1{\sqrt n}
> > \sum_{j=1}^n\frac{X_j-\mu}{\sigma}.$$
> >
> > Therefore,
> > $$\boxed{
> > U_n=\frac1{\sqrt n}\sum_{j=1}^nY_j.
> > }$$
>
> > [!abstract]- Step 4: Find the Characteristic Function of $U_n$
> > By definition,
> > $$\phi_{U_n}(t)
> > =E[e^{itU_n}].$$
> >
> > Substitute the expression for $U_n$:
> > $$\phi_{U_n}(t)
> > =
> > E\left[
> > \exp\left\{
> > \frac{it}{\sqrt n}
> > \sum_{j=1}^nY_j
> > \right\}
> > \right].$$
> >
> > Using
> > $$e^{a_1+\cdots+a_n}
> > =e^{a_1}\cdots e^{a_n},$$
> > we get
> > $$\phi_{U_n}(t)
> > =
> > E\left[
> > \prod_{j=1}^n
> > e^{itY_j/\sqrt n}
> > \right].$$
>
> > [!abstract]- Step 5: Use Independence
> > Since $Y_1,\ldots,Y_n$ are independent,
> > $$E\left[
> > \prod_{j=1}^n
> > e^{itY_j/\sqrt n}
> > \right]
> > =
> > \prod_{j=1}^n
> > E[e^{itY_j/\sqrt n}].$$
> >
> > Therefore,
> > $$\phi_{U_n}(t)
> > =
> > \prod_{j=1}^n
> > \phi_Y\left(\frac{t}{\sqrt n}\right).$$
> >
> > Since the $Y_j$ are identically distributed, all factors are the same:
> > $$\boxed{
> > \phi_{U_n}(t)
> > =
> > \left[
> > \phi_Y\left(\frac{t}{\sqrt n}\right)
> > \right]^n.
> > }$$
>
> > [!abstract]- Step 6: Use the Expansion of $\phi_Y$
> > We know that, as $u\to0$,
> > $$\phi_Y(u)
> > =1-\frac{u^2}{2}+o(u^2).$$
> >
> > Substitute
> > $$u=\frac{t}{\sqrt n}.$$
> >
> > Then
> > $$\phi_Y\left(\frac{t}{\sqrt n}\right)
> > =
> > 1-\frac12\frac{t^2}{n}
> > +o\left(\frac{t^2}{n}\right).$$
> >
> > Hence,
> > $$\phi_{U_n}(t)
> > =
> > \left[
> > 1-\frac{t^2}{2n}
> > +o\left(\frac{t^2}{n}\right)
> > \right]^n.$$
>
> > [!abstract]- Step 7: Take the Limit
> > For fixed $t$,
> > $$\phi_{U_n}(t)
> > =
> > \left[
> > 1-\frac{t^2}{2n}
> > +o\left(\frac1n\right)
> > \right]^n.$$
> >
> > Recall the fundamental limit
> > $$\left(1+\frac{x}{n}\right)^n\to e^x.$$
> >
> > Therefore,
> > $$\boxed{
> > \phi_{U_n}(t)
> > \longrightarrow
> > e^{-t^2/2}.
> > }$$
> >
> > This holds for every fixed $t\in\mathbb R$.
>
> > [!abstract]- Step 8: Identify the Limit
> > The characteristic function of a standard normal random variable
> > $$Z\sim N(0,1)$$
> > is
> > $$\phi_Z(t)=e^{-t^2/2}.$$
> >
> > Therefore,
> > $$\phi_{U_n}(t)\to\phi_Z(t).$$
> >
> > By the convergence theorem for characteristic functions,
> > $$\boxed{
> > U_n\xrightarrow{d}Z\sim N(0,1).
> > }$$
> >
> > Hence,
> > $$\boxed{
> > \frac{S_n-n\mu}{\sigma\sqrt n}
> > \xrightarrow{d}N(0,1).
> > }$$
> >
> > This proves the **Central Limit Theorem**.
>
> > [!important]- Proof in One Chain
> > The entire proof can be summarized as
> > $$Y_j=\frac{X_j-\mu}{\sigma}$$
> > $$\Downarrow$$
> > $$E[Y_j]=0,\qquad \operatorname{Var}(Y_j)=1$$
> > $$\Downarrow$$
> > $$\phi_Y(t)=1-\frac{t^2}{2}+o(t^2)$$
> > $$\Downarrow$$
> > $$U_n=\frac1{\sqrt n}\sum_{j=1}^nY_j$$
> > $$\Downarrow$$
> > $$\phi_{U_n}(t)
> > =\left[\phi_Y\left(\frac{t}{\sqrt n}\right)\right]^n$$
> > $$\Downarrow$$
> > $$\phi_{U_n}(t)
> > =
> > \left[
> > 1-\frac{t^2}{2n}+o\left(\frac1n\right)
> > \right]^n$$
> > $$\Downarrow$$
> > $$\phi_{U_n}(t)\to e^{-t^2/2}$$
> > $$\Downarrow$$
> > $$\boxed{U_n\xrightarrow{d}N(0,1).}$$
>
> > [!tip]- What Makes the CLT Work?
> > The crucial fact is that when $t/\sqrt n$ is small, the characteristic function has the approximation
> > $$\phi_Y(t)
> > =1-\frac{t^2}{2}+o(t^2).$$
> >
> > The mean-zero condition removes the linear term:
> > $$E[Y](it)=0.$$
> >
> > The variance-one condition determines the quadratic term:
> > $$\frac{E[Y^2]}{2}(it)^2=-\frac{t^2}{2}.$$
> >
> > Higher-order terms become negligible after the scaling by $1/\sqrt n$.
> >
> > Thus, remarkably, only the **first two moments** determine the limiting distribution.
>
> > [!warning]- Conditions Used
> > The proof relies on
> > $$E[X_1]=\mu<\infty$$
> > and
> > $$\operatorname{Var}(X_1)=\sigma^2<\infty.$$
> >
> > In particular, the finite variance assumption is needed for the second-order expansion
> > $$\phi_Y(t)=1-\frac{t^2}{2}+o(t^2).$$
> >
> > There are more general versions of the CLT that weaken these assumptions, but this is the standard i.i.d. finite-variance version.
>
> > [!abstract]- LLN vs CLT
> > The **LLN** says
> > $$\bar X_n\xrightarrow{P}\mu.$$
> >
> > It describes the limiting value of the sample mean.
> >
> > The **CLT** says
> > $$\frac{\sqrt n(\bar X_n-\mu)}{\sigma}
> > \xrightarrow{d}N(0,1).$$
> >
> > It describes the fluctuations around $\mu$.
> >
> > Therefore:
> > $$\boxed{
> > \text{LLN: where the average goes}
> > \qquad
> > \text{CLT: how the average fluctuates}
> > }$$
>
> > [!abstract]- Exercise: LLN Using Characteristic Functions
> > The same method can be used to prove the LLN.
> >
> > The idea is to consider
> > $$\bar X_n=\frac1n\sum_{j=1}^nX_j$$
> > and calculate
> > $$\phi_{\bar X_n}(t).$$
> >
> > Then show that
> > $$\phi_{\bar X_n}(t)
> > \to e^{i\mu t},$$
> > which is the characteristic function of the constant random variable $\mu$.
> >
> > Therefore,
> > $$\bar X_n\xrightarrow{d}\mu.$$
>
> > [!important]- Next Topic
> > So far, the main focus has been on **independent random variables**.
> >
> > The next part of the course studies random variables with a **dependency structure**, where independence is no longer available and the relationships between variables become important.



