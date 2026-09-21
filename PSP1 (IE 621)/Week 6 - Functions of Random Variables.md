
> [!important]- Functions of Random Variables
> > [!abstract]- CDF of a Function of a Random Variable
> > Let $X$ be a continuous random variable with pdf $f_X$, and let
> > $$Y=g(X).$$
> >
> > To find the CDF of $Y$:
> > $$F_Y(y)=P(Y\le y)=P(g(X)\le y).$$
> >
> > Define the inverse image (preimage):
> > $$g^{-1}(A)=\{x:g(x)\in A\}.$$
> >
> > Then
> > $$\boxed{
> > F_Y(y)=\int_{x\in g^{-1}((-\infty,y])}f_X(x)\,dx.
> > }$$
> >
> > The important idea is:
> > $$\boxed{\text{Find the values of }x\text{ that make }g(x)\le y.}$$
> >
> > Then integrate $f_X$ over those values.
>
> > [!example]- Example: $Y=X^2$ for $X\sim N(0,1)$
> > Let
> > $$X\sim N(0,1),\qquad Y=X^2.$$
> >
> > For $y\ge0$,
> > $$P(Y\le y)=P(X^2\le y).$$
> >
> > Since
> > $$X^2\le y
> > \iff-\sqrt y\le X\le\sqrt y,$$
> > we get
> > $$F_Y(y)=P(-\sqrt y\le X\le\sqrt y).$$
> >
> > Using the standard normal CDF $\Phi$:
> > $$F_Y(y)=\Phi(\sqrt y)-\Phi(-\sqrt y).$$
> >
> > Differentiate:
> > $$f_Y(y)
> > =\frac{d}{dy}
> > \left[\Phi(\sqrt y)-\Phi(-\sqrt y)\right].$$
> >
> > Since $\Phi'(x)=\phi(x)$:
> > $$f_Y(y)
> > =\frac{1}{2\sqrt y}
> > \left[\phi(\sqrt y)+\phi(-\sqrt y)\right].$$
> >
> > The standard normal pdf is even:
> > $$\phi(-x)=\phi(x).$$
> >
> > Therefore,
> > $$\boxed{
> > f_Y(y)=\frac{1}{\sqrt y}\phi(\sqrt y)
> > =\frac{1}{\sqrt{2\pi y}}e^{-y/2},
> > \qquad y>0.
> > }$$
> >
> > This is the Gamma density with shape $\frac12$ and rate $\frac12$:
> > $$\boxed{X^2\sim\Gamma\left(\frac12,\frac12\right).}$$
>
> > [!tip]- Why the Factor $1/\sqrt y$ Appears
> > The transformation
> > $$Y=X^2$$
> > is **not one-to-one**.
> >
> > Both
> > $$X=\sqrt y\qquad\text{and}\qquad X=-\sqrt y$$
> > produce the same value $Y=y$.
> >
> > Therefore, both parts of the original density contribute:
> > $$f_Y(y)
> > =\frac{f_X(\sqrt y)}{2\sqrt y}
> > +\frac{f_X(-\sqrt y)}{2\sqrt y}.$$
> >
> > For a standard normal distribution, the two contributions are equal.
>
> > [!abstract]- Chi-Squared Distribution
> > Let
> > $$X_1,\ldots,X_k\overset{\text{ind}}{\sim}N(0,1).$$
> >
> > Define
> > $$Y=X_1^2+\cdots+X_k^2.$$
> >
> > Then $Y$ has a **chi-squared distribution with $k$ degrees of freedom**:
> > $$\boxed{Y\sim\chi_k^2.}$$
> >
> > Its density is
> > $$\boxed{
> > f_Y(y)=
> > \frac{1}{2^{k/2}\Gamma(k/2)}
> > y^{k/2-1}e^{-y/2},
> > \qquad y\ge0.
> > }$$
> >
> > Comparing with the Gamma density,
> > $$f(x)=\frac{\lambda^t}{\Gamma(t)}
> > x^{t-1}e^{-\lambda x},$$
> > gives
> > $$\boxed{\chi_k^2=\Gamma\left(\frac{k}{2},\frac12\right).}$$
> >
> > In particular,
> > $$X^2\sim\chi_1^2
> > =\Gamma\left(\frac12,\frac12\right).$$
> >
> > And
> > $$X^2+Y^2\sim\chi_2^2
> > =\Gamma\left(1,\frac12\right).$$
>
> > [!important]- Transformation of a Random Vector
> > Suppose $(X_1,X_2)$ is jointly continuous with joint density
> > $$f_{X_1,X_2}(x_1,x_2).$$
> >
> > Define a transformation
> > $$\begin{pmatrix}Y_1\\Y_2\end{pmatrix}
> > =T(X_1,X_2),$$
> > where
> > $$T:\mathbb R^2\to\mathbb R^2$$
> > is one-to-one.
> >
> > Suppose the inverse transformation is
> > $$x_1=x_1(y_1,y_2),\qquad
> > x_2=x_2(y_1,y_2).$$
> >
> > Then the joint density of $(Y_1,Y_2)$ is
> > $$\boxed{
> > f_{Y_1,Y_2}(y_1,y_2)
> > =
> > f_{X_1,X_2}(x_1(y_1,y_2),x_2(y_1,y_2))
> > |J(y_1,y_2)|
> > }$$
> > where
> > $$J(y_1,y_2)
> > =
> > \det
> > \begin{pmatrix}
> > \dfrac{\partial x_1}{\partial y_1}
> > &
> > \dfrac{\partial x_1}{\partial y_2}
> > \\[6pt]
> > \dfrac{\partial x_2}{\partial y_1}
> > &
> > \dfrac{\partial x_2}{\partial y_2}
> > \end{pmatrix}.
> > $$
> >
> > Therefore,
> > $$\boxed{
> > f_Y(y)=f_X(x(y))|\det J|
> > }$$
> > in the multidimensional case.
>
> > [!tip]- Why Do We Need the Jacobian?
> > A transformation changes the size of small regions.
> >
> > Suppose a tiny rectangle in $(y_1,y_2)$-space has area
> > $$dy_1\,dy_2.$$
> >
> > When mapped back to $(x_1,x_2)$-space, its area becomes approximately
> > $$|J(y_1,y_2)|\,dy_1\,dy_2.$$
> >
> > Therefore, the Jacobian tells us how the transformation stretches or compresses area.
> >
> > The absolute value is required because density and area must be nonnegative.
>
> > [!warning]- Conditions
> > The change-of-variables formula requires appropriate regularity conditions.
> >
> > In particular, the inverse transformation should be sufficiently differentiable so that the Jacobian exists.
> >
> > For the examples here, these conditions are satisfied.
>
> > [!example]- Example: $U=XY$
> > Let $(X,Y)$ have joint density
> > $$f_{X,Y}(x,y)=f(x,y).$$
> >
> > We want the density of
> > $$U=XY.$$
> >
> > Introduce another variable:
> > $$V=X.$$
> >
> > Define
> > $$u=xy,\qquad v=x.$$
> >
> > Inverse transformation:
> > $$x=v,\qquad y=\frac uv.$$
> >
> > The Jacobian of the inverse transformation is
> > $$J=
> > \begin{pmatrix}
> > \dfrac{\partial x}{\partial u}
> > &
> > \dfrac{\partial x}{\partial v}
> > \\[6pt]
> > \dfrac{\partial y}{\partial u}
> > &
> > \dfrac{\partial y}{\partial v}
> > \end{pmatrix}
> > =
> > \begin{pmatrix}
> > 0&1\\[4pt]
> > \dfrac1v&-\dfrac{u}{v^2}
> > \end{pmatrix}.
> > $$
> >
> > Hence,
> > $$\det J=-\frac1v,$$
> > so
> > $$|J|=\frac1{|v|}.$$
> >
> > Therefore,
> > $$\boxed{
> > f_{U,V}(u,v)
> > =
> > \frac1{|v|}
> > f\left(v,\frac uv\right).
> > }$$
> >
> > Finally, marginalize over $v$:
> > $$\boxed{
> > f_U(u)=
> > \int_{-\infty}^{\infty}
> > \frac1{|v|}
> > f\left(v,\frac uv\right)\,dv.
> > }$$
> >
> > Note: the absolute value $|v|$ is essential. The lecture's displayed $1/v$ should be understood as $1/|v|$ after taking the absolute value of the Jacobian determinant.
>
> > [!example]- Example: Sum and Ratio of Two Exponentials
> > Let
> > $$X_1,X_2\overset{\text{ind}}{\sim}\operatorname{Exp}(\lambda).$$
> >
> > Define
> > $$Y_1=X_1+X_2,\qquad
> > Y_2=\frac{X_1}{X_2}.$$
> >
> > Transformation:
> > $$y_1=x_1+x_2,\qquad
> > y_2=\frac{x_1}{x_2}.$$
> >
> > Solve for $x_1,x_2$:
> > $$\boxed{
> > x_1=\frac{y_1y_2}{1+y_2},
> > \qquad
> > x_2=\frac{y_1}{1+y_2}.
> > }$$
> >
> > The inverse Jacobian is
> > $$J=
> > \begin{pmatrix}
> > \dfrac{y_2}{1+y_2}
> > &
> > \dfrac{y_1}{(1+y_2)^2}
> > \\[6pt]
> > \dfrac1{1+y_2}
> > &
> > -\dfrac{y_1}{(1+y_2)^2}
> > \end{pmatrix}.
> > $$
> >
> > Its determinant is
> > $$\det J=-\frac{y_1}{(1+y_2)^2}.$$
> >
> > Therefore,
> > $$|J|=\frac{y_1}{(1+y_2)^2}.$$
> >
> > Since $X_1,X_2$ are independent:
> > $$f_{X_1,X_2}(x_1,x_2)
> > =\lambda^2e^{-\lambda(x_1+x_2)}.$$
> >
> > But
> > $$x_1+x_2=y_1,$$
> > so
> > $$f_{Y_1,Y_2}(y_1,y_2)
> > =
> > \frac{y_1}{(1+y_2)^2}
> > \lambda^2e^{-\lambda y_1}.$$
> >
> > Hence,
> > $$\boxed{
> > f_{Y_1,Y_2}(y_1,y_2)
> > =
> > \left(\lambda^2y_1e^{-\lambda y_1}\right)
> > \left(\frac1{(1+y_2)^2}\right),
> > }$$
> > for
> > $$y_1>0,\qquad y_2>0.$$
>
> > [!tip]- Recognizing Independence After Transformation
> > The joint density factors:
> > $$f_{Y_1,Y_2}(y_1,y_2)
> > =g(y_1)h(y_2).$$
> >
> > Since the two factors are individually normalized densities,
> > $$Y_1\perp Y_2.$$
> >
> > Also,
> > $$g(y_1)=\lambda^2y_1e^{-\lambda y_1},$$
> > which is the $\Gamma(2,\lambda)$ density.
> >
> > Therefore,
> > $$\boxed{
> > Y_1\sim\Gamma(2,\lambda),
> > \qquad Y_1\perp Y_2.
> > }$$
> >
> > This is an interesting result because $Y_1$ is the **sum** while $Y_2$ is the **ratio**, yet they turn out to be independent.
>
> > [!warning]- Infinite Mean of the Ratio
> > The marginal density of $Y_2$ is
> > $$f_{Y_2}(y_2)=\frac1{(1+y_2)^2},
> > \qquad y_2>0.$$
> >
> > Its mean is
> > $$E[Y_2]
> > =\int_0^\infty
> > y_2\frac1{(1+y_2)^2}\,dy_2.$$
> >
> > For large $y_2$,
> > $$\frac{y_2}{(1+y_2)^2}\sim\frac1{y_2}.$$
> >
> > Since
> > $$\int^\infty\frac1y\,dy=\infty,$$
> > the integral diverges:
> > $$\boxed{E[Y_2]=\infty.}$$
> >
> > Thus, $Y_2=X_1/X_2$ has an infinite mean, even though both $X_1$ and $X_2$ individually have finite means.
>
> > [!important]- Key Takeaways
> > **One-dimensional transformation:**
> > $$Y=g(X)
> > \quad\Rightarrow\quad
> > F_Y(y)=P(g(X)\le y).$$
> >
> > **Vector transformation:**
> > $$Y=T(X)
> > \quad\Rightarrow\quad
> > f_Y(y)=f_X(x(y))|\det J|.$$
> >
> > **For $X\sim N(0,1)$:**
> > $$X^2\sim\chi_1^2
> > =\Gamma\left(\frac12,\frac12\right).$$
> >
> > **For independent standard normals:**
> > $$\sum_{i=1}^kX_i^2\sim\chi_k^2
> > =\Gamma\left(\frac k2,\frac12\right).$$
> >
> > **Most important idea:**
> > $$\boxed{
> > \text{Transformation of RVs}
> > \longrightarrow
> > \text{inverse transformation + Jacobian}.
> > }$$

> [!important]- Other Important Continuous Distributions
> > [!abstract]- Cauchy Distribution
> > The **Cauchy distribution** has density
> > $$\boxed{
> > f_X(x)=\frac{1}{\pi(1+x^2)},
> > \qquad x\in\mathbb R.
> > }$$
> >
> > This is the standard Cauchy distribution.
> >
> > It is an important example of a distribution whose **mean does not exist**:
> > $$\boxed{E[X]\text{ does not exist}.}$$
> >
> > The reason is that its tails decay too slowly:
> > $$xf_X(x)\sim\frac{1}{\pi x}$$
> > as $|x|\to\infty$, and
> > $$\int^\infty\frac1x\,dx$$
> > diverges.
> >
> > Therefore, although the Cauchy distribution is symmetric around $0$, we cannot say that its mean is $0$.
> >
> > **Important distinction:**
> > $$\boxed{\text{Symmetry does not guarantee that the mean exists.}}$$
>
> > [!abstract]- Beta Distribution
> > The **Beta distribution** has parameters
> > $$a,b>0$$
> > and density
> > $$\boxed{
> > f_X(x)=
> > \frac{1}{B(a,b)}
> > x^{a-1}(1-x)^{b-1},
> > \qquad 0\le x\le1.
> > }$$
> >
> > We write
> > $$\boxed{X\sim\operatorname{Beta}(a,b).}$$
> >
> > Here $B(a,b)$ is the **Beta function**:
> > $$\boxed{
> > B(a,b)=
> > \int_0^1x^{a-1}(1-x)^{b-1}\,dx.
> > }$$
> >
> > The Beta function acts as the normalization constant that makes the density integrate to $1$.
>
> > [!tip]- Gamma-to-Beta Connection
> > Suppose
> > $$X\sim\Gamma(\alpha,\lambda),$$
> > $$Y\sim\Gamma(\beta,\lambda),$$
> > and $X,Y$ are independent.
> >
> > Define
> > $$U=\frac{X}{X+Y}.$$
> >
> > Then
> > $$\boxed{
> > U\sim\operatorname{Beta}(\alpha,\beta).
> > }$$
> >
> > Notice that $X$ and $Y$ must have the **same rate parameter** $\lambda$.
> >
> > The ratio
> > $$\frac{X}{X+Y}$$
> > always lies in $[0,1]$, which explains why the Beta distribution has support $[0,1]$.
> >
> > This gives a useful connection:
> > $$\boxed{
> > \text{Independent Gamma variables}
> > \longrightarrow
> > \text{normalized ratio}
> > \longrightarrow
> > \text{Beta distribution}.
> > }$$
>
> > [!abstract]- Weibull Distribution
> > The **Weibull distribution** has CDF
> > $$\boxed{
> > F_X(x)=1-e^{-\alpha x^\beta},
> > \qquad x\ge0,
> > }$$
> > where
> > $$\alpha>0,\qquad\beta>0.$$
> >
> > The corresponding density is obtained by differentiation:
> > $$\boxed{
> > f_X(x)=
> > \alpha\beta x^{\beta-1}
> > e^{-\alpha x^\beta},
> > \qquad x\ge0.
> > }$$
> >
> > The parameters have different roles:
> > - $\alpha$: scale/rate-related parameter
> > - $\beta$: shape parameter
> >
> > When
> > $$\beta=1,$$
> > the CDF becomes
> > $$F_X(x)=1-e^{-\alpha x},$$
> > which is exactly the exponential CDF.
> >
> > Therefore,
> > $$\boxed{
> > \operatorname{Weibull}(\alpha,1)
> > =\operatorname{Exp}(\alpha).
> > }$$
>
> > [!tip]- How the Weibull Generalizes the Exponential
> > For the exponential distribution, the hazard rate is constant.
> >
> > For the Weibull distribution, the hazard rate is
> > $$h(x)=\frac{f_X(x)}{1-F_X(x)}
> > =\alpha\beta x^{\beta-1}.$$
> >
> > Thus:
> > $$\beta=1
> > \quad\Rightarrow\quad
> > h(x)=\alpha
> > $$
> > (constant hazard).
> >
> > The shape parameter $\beta$ controls how the hazard changes with time.
>
> > [!abstract]- Summary of Important Continuous Distributions
> > | Distribution | Parameters | Support | Key idea / Applications |
> > |---|---|---|---|
> > | **Normal (Gaussian)** | Mean $\mu$, variance $\sigma^2$ | $\mathbb R$ | Measurement errors, physical measurements |
> > | **Exponential** | Rate $\lambda>0$ | $x\ge0$ | Waiting time until the next event |
> > | **Uniform** | Bounds $a,b$ | $a\le x\le b$ | Random selection, simulation |
> > | **Gamma** | Shape $t$, rate $\lambda$ | $x\ge0$ | Waiting times, queueing, rainfall |
> > | **Beta** | Shape $a,b>0$ | $0\le x\le1$ | Proportions, probabilities, CTR |
> > | **Weibull** | Shape $\beta$, parameter $\alpha$ | $x\ge0$ | Component lifetime, survival analysis |
> > | **Cauchy** | Location $x_0$, scale $\gamma$ | $\mathbb R$ | Heavy-tailed phenomena, spectral line broadening |
>
> > [!important]- Important Relationships
> > **Normal:**
> > $$X\sim N(\mu,\sigma^2).$$
> >
> > **Exponential:**
> > $$X\sim\operatorname{Exp}(\lambda)
> > =\Gamma(1,\lambda).$$
> >
> > **Gamma:**
> > $$\Gamma(t,\lambda).$$
> >
> > If $t$ is an integer:
> > $$\Gamma(t,\lambda)
> > =\sum_{i=1}^t\operatorname{Exp}(\lambda).$$
> >
> > **Chi-squared:**
> > $$\boxed{
> > \chi_k^2
> > =\Gamma\left(\frac{k}{2},\frac12\right).
> > }$$
> >
> > **Beta from Gamma:**
> > $$X\sim\Gamma(a,\lambda),\quad
> > Y\sim\Gamma(b,\lambda),\quad X\perp Y$$
> > implies
> > $$\boxed{
> > \frac{X}{X+Y}\sim\operatorname{Beta}(a,b).
> > }$$
> >
> > **Weibull:**
> > $$\operatorname{Weibull}(\alpha,1)
> > =\operatorname{Exp}(\alpha).$$
>
> > [!warning]- Parameterization Reminder
> > Different textbooks use different parameterizations, especially for the **Gamma** and **Weibull** distributions.
> >
> > In these notes:
> >
> > Gamma uses **shape + rate**:
> > $$f(x)=
> > \frac{\lambda^t}{\Gamma(t)}
> > x^{t-1}e^{-\lambda x}.$$
> >
> > Weibull uses:
> > $$F(x)=1-e^{-\alpha x^\beta}.$$
> >
> > Always check the parameterization before comparing formulas from different sources.
>
> > [!important]- Distribution Map to Remember
> > $$\boxed{
> > \begin{array}{c}
> > \text{Exponential}\\
> > \downarrow\text{sum}\\
> > \text{Gamma}\\
> > \downarrow\text{special case}\\
> > \text{Chi-squared}
> > \end{array}
> > }$$
> >
> > and
> >
> > $$\boxed{
> > \begin{array}{c}
> > X\sim\Gamma(a,\lambda),\
> > Y\sim\Gamma(b,\lambda)\\
> > \downarrow\\
> > \dfrac{X}{X+Y}\\
> > \downarrow\\
> > \operatorname{Beta}(a,b)
> > \end{array}
> > }$$
> >
> > Also:
> > $$\boxed{
> > X_i\overset{\text{i.i.d.}}{\sim}N(0,1)
> > \quad\Rightarrow\quad
> > \sum_{i=1}^kX_i^2\sim\chi_k^2.
> > }$$

> [!important]- Conditional Distributions and Conditional Expectations
> > [!abstract]- Conditional Distribution for Continuous Random Variables
> > Let $(X,Y)$ be jointly continuous with joint density
> > $$f_{X,Y}(x,y).$$
> >
> > In the discrete case, we can condition directly on the event $\{X=x\}$ when $P(X=x)>0$.
> >
> > For continuous $X$,
> > $$P(X=x)=0.$$
> >
> > So $\{X=x\}$ cannot be used directly in the ordinary event-based definition of conditional probability.
> >
> > Instead, consider a small interval:
> > $$\{x\le X\le x+dx\}.$$
> >
> > If $f_X(x)>0$, then approximately
> > $$P(x\le X\le x+dx)\approx f_X(x)\,dx.$$
> >
> > Similarly,
> > $$P(Y\le y,\;x\le X\le x+dx)
> > \approx
> > \left(\int_{-\infty}^y f_{X,Y}(x,v)\,dv\right)dx.$$
> >
> > Therefore,
> > $$P(Y\le y\mid x\le X\le x+dx)
> > \approx
> > \frac{\int_{-\infty}^y f_{X,Y}(x,v)\,dv}
> > {f_X(x)}.$$
> >
> > This motivates the definition of the conditional distribution.
>
> > [!abstract]- Conditional CDF and Conditional PDF
> > For $x$ such that
> > $$f_X(x)>0,$$
> > the conditional CDF of $Y$ given $X=x$ is
> > $$\boxed{
> > F_{Y|X}(y|x)
> > =
> > \int_{-\infty}^y
> > \frac{f_{X,Y}(x,v)}{f_X(x)}\,dv.
> > }$$
> >
> > Differentiating with respect to $y$ gives the conditional pdf:
> > $$\boxed{
> > f_{Y|X}(y|x)
> > =
> > \frac{f_{X,Y}(x,y)}
> > {f_X(x)}.
> > }$$
> >
> > This is the continuous analogue of the discrete formula
> > $$P(Y=y|X=x)
> > =
> > \frac{P(X=x,Y=y)}
> > {P(X=x)}.$$
> >
> > The important formula to remember is
> > $$\boxed{
> > \text{conditional pdf}
> > =
> > \frac{\text{joint pdf}}
> > {\text{marginal pdf}}.
> > }$$
>
> > [!tip]- Intuition
> > Conditioning on $X=x$ means:
> >
> > **Fix $X$ at $x$ and look at how the joint density varies with $Y$.**
> >
> > The joint density
> > $$f_{X,Y}(x,y)$$
> > tells us the density around $(x,y)$.
> >
> > Dividing by
> > $$f_X(x)$$
> > normalizes this slice so that it becomes a valid probability density in $y$:
> > $$\int_{-\infty}^{\infty}f_{Y|X}(y|x)\,dy=1.$$
>
> > [!abstract]- Conditional Expectation
> > Since $f_{Y|X}(y|x)$ is a valid pdf, we can calculate an expectation using it.
> >
> > The conditional expectation of $Y$ given $X=x$ is
> > $$\boxed{
> > E[Y|X=x]
> > =
> > \int_{-\infty}^{\infty}
> > y f_{Y|X}(y|x)\,dy.
> > }$$
> >
> > Substituting the conditional pdf:
> > $$\boxed{
> > E[Y|X=x]
> > =
> > \frac{
> > \int_{-\infty}^{\infty}
> > y f_{X,Y}(x,y)\,dy
> > }{f_X(x)}.
> > }$$
>
> > [!abstract]- Conditional Expectation as a Random Variable
> > For every value of $x$, we have a number:
> > $$E[Y|X=x].$$
> >
> > Since $X$ itself is random, we can replace $x$ by the random variable $X$:
> > $$\boxed{
> > E[Y|X]
> > =
> > g(X),
> > \qquad
> > g(x)=E[Y|X=x].
> > }$$
> >
> > Thus, $E[Y|X]$ is itself a random variable.
> >
> > Conceptually:
> > $$\boxed{
> > E[Y|X=x]
> > \text{ is a number,}
> > \qquad
> > E[Y|X]
> > \text{ is a random variable.}
> > }$$
>
> > [!important]- Law of Iterated Expectations
> > The **law of iterated expectations**, also called the **tower property**, states
> > $$\boxed{
> > E[E[Y|X]]=E[Y].
> > }$$
> >
> > Intuition:
> > $$\text{average within each value of }X
> > \longrightarrow
> > \text{average over all values of }X.$$
> >
> > In integral form:
> > $$E[E[Y|X]]
> > =
> > \int_{-\infty}^{\infty}
> > E[Y|X=x]f_X(x)\,dx.$$
> >
> > Substituting the conditional expectation:
> > $$=
> > \int_{-\infty}^{\infty}
> > \left[
> > \int_{-\infty}^{\infty}
> > y f_{Y|X}(y|x)\,dy
> > \right]f_X(x)\,dx.$$
> >
> > Since
> > $$f_{Y|X}(y|x)f_X(x)=f_{X,Y}(x,y),$$
> > we get
> > $$=
> > \int_{-\infty}^{\infty}
> > \int_{-\infty}^{\infty}
> > y f_{X,Y}(x,y)\,dy\,dx.$$
> >
> > Integrating out $x$ gives the marginal density $f_Y(y)$:
> > $$=
> > \int_{-\infty}^{\infty}y f_Y(y)\,dy
> > =E[Y].$$
>
> > [!example]- Standard Bivariate Normal Distribution
> > Let $-1<\rho<1$ and define the joint density
> > $$\boxed{
> > f_{X,Y}(x,y)
> > =
> > \frac{1}{2\pi\sqrt{1-\rho^2}}
> > \exp\left[
> > -\frac{x^2-2\rho xy+y^2}
> > {2(1-\rho^2)}
> > \right].
> > }$$
> >
> > A random vector $(X,Y)$ having this density is called a **standard bivariate normal distribution** with correlation parameter $\rho$.
> >
> > Its marginals are
> > $$X\sim N(0,1),\qquad Y\sim N(0,1).$$
> >
> > The parameter $\rho$ is the covariance:
> > $$\boxed{\operatorname{Cov}(X,Y)=\rho.}$$
> >
> > Since both variables have variance $1$,
> > $$\rho
> > =
> > \operatorname{Corr}(X,Y).$$
>
> > [!tip]- Special Case: $\rho=0$
> > If
> > $$\rho=0,$$
> > the joint density becomes
> > $$f_{X,Y}(x,y)
> > =
> > \frac1{2\pi}
> > e^{-(x^2+y^2)/2}.$$
> >
> > Factorize:
> > $$f_{X,Y}(x,y)
> > =
> > \left(\frac1{\sqrt{2\pi}}e^{-x^2/2}\right)
> > \left(\frac1{\sqrt{2\pi}}e^{-y^2/2}\right).$$
> >
> > Therefore,
> > $$f_{X,Y}(x,y)=f_X(x)f_Y(y),$$
> > which implies
> > $$\boxed{X\perp Y.}$$
> >
> > Thus, for the bivariate normal distribution:
> > $$\boxed{
> > \rho=0
> > \iff
> > \operatorname{Cov}(X,Y)=0
> > \iff
> > X\text{ and }Y\text{ are independent}.
> > }$$
> >
> > This is a special property of jointly Gaussian random variables.
> >
> > In general:
> > $$\operatorname{Cov}(X,Y)=0
> > \not\Rightarrow
> > X\perp Y.$$
>
> > [!abstract]- Conditional Distribution of a Bivariate Normal
> > We want
> > $$f_{Y|X}(y|x)
> > =
> > \frac{f_{X,Y}(x,y)}{f_X(x)}.$$
> >
> > Since
> > $$f_X(x)=\frac1{\sqrt{2\pi}}e^{-x^2/2},$$
> > substitution and completing the square gives
> > $$\boxed{
> > f_{Y|X}(y|x)
> > =
> > \frac1{\sqrt{2\pi(1-\rho^2)}}
> > \exp\left[
> > -\frac{(y-\rho x)^2}
> > {2(1-\rho^2)}
> > \right].
> > }$$
> >
> > Compare this with the normal density:
> > $$\frac1{\sqrt{2\pi\sigma^2}}
> > e^{-(y-\mu)^2/(2\sigma^2)}.$$
> >
> > Therefore,
> > $$\boxed{
> > Y|X=x\sim N(\rho x,1-\rho^2).
> > }$$
>
> > [!important]- Conditional Mean and Variance
> > From
> > $$Y|X=x\sim N(\rho x,1-\rho^2),$$
> > we immediately obtain
> > $$\boxed{
> > E[Y|X=x]=\rho x
> > }$$
> > and
> > $$\boxed{
> > \operatorname{Var}(Y|X=x)=1-\rho^2.
> > }$$
> >
> > Replacing $x$ by the random variable $X$:
> > $$\boxed{
> > E[Y|X]=\rho X.
> > }$$
> >
> > This is a particularly simple example of conditional expectation being a function of $X$.
>
> > [!tip]- Geometric Intuition for the Bivariate Normal
> > The conditional mean is
> > $$E[Y|X=x]=\rho x.$$
> >
> > Therefore, the conditional mean lies on the straight line
> > $$y=\rho x.$$
> >
> > The conditional variance is
> > $$1-\rho^2.$$
> >
> > Hence:
> > - $\rho=0$: conditional mean is $0$, and $X,Y$ are independent.
> > - $|\rho|$ close to $1$: knowing $X$ gives strong information about $Y$.
> > - $|\rho|=1$: the variables become perfectly linearly related, although the standard bivariate-normal density above is defined for $|\rho|<1$.
>
> > [!important]- Key Formulas
> > **Conditional CDF:**
> > $$\boxed{
> > F_{Y|X}(y|x)
> > =
> > \int_{-\infty}^y
> > \frac{f_{X,Y}(x,v)}{f_X(x)}\,dv
> > }$$
> >
> > **Conditional PDF:**
> > $$\boxed{
> > f_{Y|X}(y|x)
> > =
> > \frac{f_{X,Y}(x,y)}{f_X(x)}
> > }$$
> >
> > **Conditional expectation:**
> > $$\boxed{
> > E[Y|X=x]
> > =
> > \int_{-\infty}^{\infty}
> > y f_{Y|X}(y|x)\,dy
> > }$$
> >
> > **Tower property:**
> > $$\boxed{
> > E[E[Y|X]]=E[Y]
> > }$$
> >
> > **Bivariate normal:**
> > $$\boxed{
> > Y|X=x\sim N(\rho x,1-\rho^2)
> > }$$
> >
> > hence
> > $$\boxed{
> > E[Y|X]=\rho X.
> > }$$
>
> > [!important]- Discrete vs Continuous Conditioning
> > **Discrete:**
> > $$P(Y=y|X=x)
> > =
> > \frac{P(X=x,Y=y)}{P(X=x)}.$$
> >
> > **Continuous:**
> > $$f_{Y|X}(y|x)
> > =
> > \frac{f_{X,Y}(x,y)}{f_X(x)}.$$
> >
> > The formulas look almost identical:
> > $$\boxed{
> > \text{conditional}=
> > \frac{\text{joint}}{\text{marginal}}.
> > }$$
> >
> > The key difference is that in the continuous case,
> > $$P(X=x)=0,$$
> > so we work with **densities** rather than point probabilities.

---

> [!important]- Sums of Independent Gaussians and the Law of Large Numbers
> > [!abstract]- Sum of Two Independent Gaussians
> > If
> > $$X,Y\overset{\text{ind}}{\sim}N(0,1),$$
> > then
> > $$\boxed{X+Y\sim N(0,2).}$$
> >
> > Dividing by $2$ gives
> > $$\frac{X+Y}{2}\sim N\left(0,\frac{2}{4}\right),$$
> > so
> > $$\boxed{\frac{X+Y}{2}\sim N\left(0,\frac12\right).}$$
> >
> > Notice that dividing a random variable by $a$ divides its variance by $a^2$:
> > $$\operatorname{Var}\left(\frac Xa\right)
> > =\frac1{a^2}\operatorname{Var}(X).$$
>
> > [!abstract]- Sequence of i.i.d. Gaussian Random Variables
> > Let
> > $$X_1,X_2,\ldots$$
> > be independent and identically distributed random variables with
> > $$\boxed{X_i\sim N(\mu,\sigma^2).}$$
> >
> > Thus:
> > $$E[X_i]=\mu,\qquad
> > \operatorname{Var}(X_i)=\sigma^2.$$
> >
> > The sample mean of the first $n$ observations is
> > $$\boxed{
> > \bar X_n=\frac1n\sum_{i=1}^nX_i.
> > }$$
>
> > [!abstract]- Mean of the Sample Mean
> > By linearity of expectation,
> > $$E[\bar X_n]
> > =
> > E\left[\frac1n\sum_{i=1}^nX_i\right].$$
> >
> > Therefore,
> > $$E[\bar X_n]
> > =\frac1n\sum_{i=1}^nE[X_i]
> > =\frac1n(n\mu).$$
> >
> > Hence,
> > $$\boxed{E[\bar X_n]=\mu.}$$
> >
> > So the sample mean is **unbiased** for the true mean $\mu$.
>
> > [!abstract]- Variance of the Sample Mean
> > Since the $X_i$ are independent,
> > $$\operatorname{Var}\left(\sum_{i=1}^nX_i\right)
> > =
> > \sum_{i=1}^n\operatorname{Var}(X_i).$$
> >
> > Therefore,
> > $$\operatorname{Var}(\bar X_n)
> > =
> > \operatorname{Var}\left(
> > \frac1n\sum_{i=1}^nX_i
> > \right)$$
> > $$=
> > \frac1{n^2}
> > \sum_{i=1}^n\sigma^2.$$
> >
> > Hence,
> > $$\boxed{
> > \operatorname{Var}(\bar X_n)=\frac{\sigma^2}{n}.
> > }$$
> >
> > As $n$ increases:
> > $$\boxed{
> > \operatorname{Var}(\bar X_n)\to0.
> > }$$
>
> > [!abstract]- Distribution of the Sample Mean
> > A key property of Gaussian random variables is that a linear combination of independent Gaussian random variables is also Gaussian.
> >
> > Since
> > $$\bar X_n=\frac1n\sum_{i=1}^nX_i,$$
> > $\bar X_n$ is Gaussian.
> >
> > We already found
> > $$E[\bar X_n]=\mu$$
> > and
> > $$\operatorname{Var}(\bar X_n)=\frac{\sigma^2}{n}.$$
> >
> > Therefore,
> > $$\boxed{
> > \bar X_n\sim N\left(\mu,\frac{\sigma^2}{n}\right).
> > }$$
>
> > [!tip]- What Happens as $n\to\infty$?
> > The distribution is
> > $$\bar X_n\sim N\left(\mu,\frac{\sigma^2}{n}\right).$$
> >
> > As $n\to\infty$:
> > $$\frac{\sigma^2}{n}\to0.$$
> >
> > Thus the distribution becomes increasingly concentrated around $\mu$.
> >
> > In the limit, the randomness disappears and $\bar X_n$ approaches the constant
> > $$\mu.$$
> >
> > Informally:
> > $$\boxed{
> > \bar X_n\longrightarrow\mu.
> > }$$
> >
> > This means that averaging more and more independent observations makes the sample mean more stable and closer to the true mean.
>
> > [!example]- Numerical Intuition
> > Suppose
> > $$X_i\sim N(10,4).$$
> >
> > Then
> > $$\mu=10,\qquad\sigma^2=4.$$
> >
> > For $n=1$:
> > $$\bar X_1\sim N(10,4).$$
> >
> > For $n=4$:
> > $$\bar X_4\sim N\left(10,\frac44\right)
> > =N(10,1).$$
> >
> > For $n=100$:
> > $$\bar X_{100}\sim N\left(10,\frac4{100}\right)
> > =N(10,0.04).$$
> >
> > The mean remains $10$, but the variance gets smaller:
> > $$4\longrightarrow1\longrightarrow0.04.$$
> >
> > Hence, the sample mean becomes increasingly concentrated around $10$.
>
> > [!important]- This Is Not Specific to Gaussians
> > The phenomenon
> > $$\bar X_n\to\mu$$
> > is much more general.
> >
> > We do **not** need the $X_i$ to be Gaussian for the sample mean to approach the true mean.
> >
> > If
> > $$X_1,X_2,\ldots$$
> > are i.i.d. random variables with a finite mean $\mu$, then under the appropriate conditions,
> > $$\boxed{
> > \bar X_n=
> > \frac1n\sum_{i=1}^nX_i
> > \longrightarrow\mu.
> > }$$
> >
> > This fundamental result is called the **Law of Large Numbers (LLN)**.
>
> > [!abstract]- Law of Large Numbers: Intuition
> > The LLN says:
> >
> > $$\boxed{
> > \text{More independent observations}
> > \quad\Longrightarrow\quad
> > \text{sample average gets closer to the true average}.
> > }$$
> >
> > For example, if a fair coin is tossed many times,
> > $$\frac{\text{number of Heads}}{\text{number of tosses}}
> > \to\frac12.$$
> >
> > Similarly, for i.i.d. observations,
> > $$\frac{X_1+\cdots+X_n}{n}
> > \to E[X_1].$$
> >
> > This is one of the fundamental **limit theorems of probability**.
>
> > [!warning]- Important Distinction
> > The fact that
> > $$\operatorname{Var}(\bar X_n)=\frac{\sigma^2}{n}\to0$$
> > explains why the sample mean becomes concentrated around $\mu$ in the Gaussian example.
> >
> > But the general **Law of Large Numbers** is a stronger and more general mathematical statement. It applies far beyond Gaussian random variables.
> >
> > Also, saying
> > $$\bar X_n\to\mu
> > $$
> > requires specifying the **mode of convergence**. The most common form of the LLN is convergence in probability:
> > $$\boxed{
> > \bar X_n\xrightarrow{P}\mu.
> > }$$
> >
> > A stronger result, the strong law of large numbers, gives almost sure convergence:
> > $$\boxed{
> > \bar X_n\xrightarrow{\text{a.s.}}\mu.
> > }$$
>
> > [!important]- Key Takeaways
> > For
> > $$X_i\overset{\text{i.i.d.}}{\sim}N(\mu,\sigma^2),$$
> > the sample mean is
> > $$\boxed{
> > \bar X_n=\frac1n\sum_{i=1}^nX_i
> > \sim N\left(\mu,\frac{\sigma^2}{n}\right).
> > }$$
> >
> > Therefore:
> > $$\boxed{E[\bar X_n]=\mu}$$
> > $$\boxed{\operatorname{Var}(\bar X_n)=\frac{\sigma^2}{n}}$$
> > $$\boxed{\operatorname{Var}(\bar X_n)\to0}$$
> > $$\boxed{\bar X_n\to\mu\quad\text{(in the LLN sense)}}$$
> >
> > The broader principle is:
> > $$\boxed{
> > \text{Sample mean}
> > \longrightarrow
> > \text{true mean as sample size increases}.
> > }$$
> >
> > The next step is to introduce the precise mathematical tools needed to define and prove these different types of convergence.

> [!important]- Expectation for General Random Variables
> > [!abstract]- Why Do We Need a General Definition?
> > So far, expectation has been defined separately for:
> >
> > **Discrete random variables:**
> > $$E[X]=\sum_x xf_X(x).$$
> >
> > **Continuous random variables:**
> > $$E[X]=\int_{-\infty}^{\infty}xf_X(x)\,dx.$$
> >
> > But not every random variable is purely discrete or continuous. Therefore, we need a definition that works for **any random variable**, regardless of its type.
> >
> > The key idea is to express expectation in terms of the **CDF** $F$:
> > $$\boxed{
> > E[X]=\int_{-\infty}^{\infty}x\,dF(x).
> > }$$
> >
> > This is a **Riemann–Stieltjes integral**.
>
> > [!abstract]- Continuous Case as a Stieltjes Integral
> > For a continuous random variable with CDF $F$ and pdf $f$,
> > $$f(x)=F'(x).$$
> >
> > The ordinary expectation is
> > $$E[X]=\int_{-\infty}^{\infty}xf(x)\,dx.$$
> >
> > Since
> > $$dF(x)=F'(x)\,dx=f(x)\,dx,$$
> > we can write
> > $$\boxed{
> > E[X]=\int_{-\infty}^{\infty}x\,dF(x).
> > }$$
> >
> > Thus, the Stieltjes notation is simply a more general way of writing the usual integral in the continuous case.
>
> > [!abstract]- Discrete Case as a Stieltjes Integral
> > For a discrete random variable,
> > $$E[X]=\sum_xxP(X=x).$$
> >
> > If $F$ is the CDF, it has jumps at the possible values of $X$.
> >
> > At a point $x$,
> > $$\Delta F(x)
> > =F(x)-F(x^-)
> > =P(X=x).$$
> >
> > Therefore, informally,
> > $$dF(x)
> > \leftrightarrow P(X=x)$$
> > at the points where $X$ has positive probability.
> >
> > Hence,
> > $$\int_{-\infty}^{\infty}x\,dF(x)
> > =
> > \sum_xxP(X=x).$$
> >
> > So the same expression works for both discrete and continuous random variables:
> > $$\boxed{
> > E[X]=\int_{-\infty}^{\infty}x\,dF(x).
> > }$$
>
> > [!tip]- Big Picture
> > The expression
> > $$\boxed{\int x\,dF(x)}$$
> > unifies the two familiar formulas:
> >
> > **Discrete:**
> > $$\int x\,dF(x)
> > \longrightarrow
> > \sum_xxP(X=x).$$
> >
> > **Continuous:**
> > $$\int x\,dF(x)
> > \longrightarrow
> > \int xf(x)\,dx.$$
> >
> > Therefore, expectation is fundamentally an operation with respect to the **distribution of $X$**, not something restricted to discrete or continuous variables.
>
> > [!abstract]- Simple Random Variables
> > A random variable $X$ is called **simple** if it takes only finitely many distinct values.
> >
> > Suppose
> > $$X\in\{x_1,x_2,\ldots,x_n\}.$$
> >
> > Then its expectation is defined as
> > $$\boxed{
> > E[X]=\sum_{i=1}^nx_iP(X=x_i).
> > }$$
> >
> > This is simply the usual probability-weighted average.
> >
> > For example, if
> > $$P(X=1)=0.2,\qquad P(X=3)=0.8,$$
> > then
> > $$E[X]=1(0.2)+3(0.8)=2.6.$$
>
> > [!abstract]- Approximating a Nonnegative Random Variable
> > Any nonnegative random variable
> > $$X:\Omega\to[0,\infty)$$
> > can be approximated by an increasing sequence of simple random variables:
> > $$X_1\le X_2\le\cdots\le X_n\le\cdots$$
> > such that
> > $$\boxed{
> > X_n(\omega)\uparrow X(\omega).
> > }$$
> >
> > One possible approximation is obtained by rounding $X$ **down** to increasingly fine dyadic levels.
> >
> > For example, define
> > $$X_n(\omega)=k2^{-n}$$
> > whenever
> > $$k2^{-n}\le X(\omega)<(k+1)2^{-n}.$$
> >
> > As $n$ increases, the grid becomes finer:
> > $$2^{-n}\to0.$$
> >
> > Therefore,
> > $$X_n(\omega)\uparrow X(\omega).$$
> >
> > Each $X_n$ takes only finitely many values, so each $X_n$ is a simple random variable.
>
> > [!abstract]- Defining Expectation for Nonnegative $X$
> > Since each $X_n$ is simple, $E[X_n]$ is already defined.
> >
> > Because
> > $$X_n\le X_{n+1},$$
> > we have
> > $$X_{n+1}-X_n\ge0.$$
> >
> > By monotonicity of expectation,
> > $$E[X_n]\le E[X_{n+1}].$$
> >
> > Therefore,
> > $$\{E[X_n]\}$$
> > is a nondecreasing sequence.
> >
> > Its limit exists in the extended real numbers:
> > $$\lim_{n\to\infty}E[X_n]\in[0,\infty].$$
> >
> > We define
> > $$\boxed{
> > E[X]=\lim_{n\to\infty}E[X_n].
> > }$$
> >
> > Thus, expectation of a general nonnegative random variable is obtained by approximating it from below using simple random variables.
>
> > [!tip]- Why Use an Increasing Approximation?
> > The condition
> > $$X_n\uparrow X$$
> > ensures that the approximation gets progressively closer to $X$ without overshooting it.
> >
> > Consequently,
> > $$E[X_1]\le E[X_2]\le\cdots\le E[X].$$
> >
> > The expectation is obtained as the limiting value:
> > $$\boxed{
> > E[X]=\lim_{n\to\infty}E[X_n].
> > }$$
> >
> > The important theorem behind this idea is the **Monotone Convergence Theorem**.
>
> > [!warning]- Choice of Approximation
> > There can be many different sequences of simple random variables that increase to $X$.
> >
> > A fundamental result shows that the resulting limit
> > $$\lim_{n\to\infty}E[X_n]$$
> > is the same regardless of which valid increasing simple approximation is used.
> >
> > Thus, expectation is well-defined.
>
> > [!abstract]- Positive and Negative Parts
> > A general random variable can take both positive and negative values.
> >
> > We split $X$ into its **positive part** and **negative part**:
> > $$\boxed{
> > X^+=\max\{0,X\}
> > }$$
> > and
> > $$\boxed{
> > X^-=-\min\{0,X\}.
> > }$$
> >
> > Equivalently,
> > $$X^+=
> > \begin{cases}
> > X,&X>0,\\
> > 0,&X\le0,
> > \end{cases}
> > $$
> > and
> > $$X^-=
> > \begin{cases}
> > -X,&X<0,\\
> > 0,&X\ge0.
> > \end{cases}
> > $$
> >
> > Both $X^+$ and $X^-$ are nonnegative random variables.
> >
> > Most importantly,
> > $$\boxed{
> > X=X^+-X^-.
> > }$$
> >
> > Also,
> > $$X^+X^-=0$$
> > for every outcome, because $X$ cannot be simultaneously positive and negative.
>
> > [!abstract]- Expectation of a General Random Variable
> > Since $X^+$ and $X^-$ are nonnegative, their expectations have already been defined:
> > $$E[X^+]\in[0,\infty],$$
> > $$E[X^-]\in[0,\infty].$$
> >
> > If at least one is finite, i.e.
> > $$E[X^+]<\infty
> > \quad\text{or}\quad
> > E[X^-]<\infty,$$
> > then we define
> > $$\boxed{
> > E[X]=E[X^+]-E[X^-].
> > }$$
> >
> > If both are finite, $E[X]$ is a finite real number.
> >
> > If exactly one is infinite, the expectation can be $+\infty$ or $-\infty$:
> > $$E[X^+]=\infty,\ E[X^-]<\infty
> > \Rightarrow E[X]=+\infty,$$
> > $$E[X^+]<\infty,\ E[X^-]=\infty
> > \Rightarrow E[X]=-\infty.$$
>
> > [!warning]- When Is Expectation Undefined?
> > If
> > $$\boxed{
> > E[X^+]=\infty
> > \quad\text{and}\quad
> > E[X^-]=\infty,
> > }$$
> > then
> > $$E[X]=E[X^+]-E[X^-]$$
> > would involve
> > $$\infty-\infty,$$
> > which is undefined.
> >
> > Therefore,
> > $$\boxed{
> > E[X]\text{ is undefined if }
> > E[X^+]=E[X^-]=\infty.
> > }$$
>
> > [!example]- Cauchy Distribution
> > For the standard Cauchy distribution,
> > $$f_X(x)=\frac1{\pi(1+x^2)}.$$
> >
> > Its positive and negative tails are symmetric.
> >
> > On the positive side,
> > $$E[X^+]
> > =
> > \int_0^\infty
> > x\frac1{\pi(1+x^2)}\,dx
> > =\infty.
> > $$
> >
> > By symmetry,
> > $$E[X^-]=\infty.$$
> >
> > Therefore,
> > $$\boxed{
> > E[X]\text{ is undefined}.
> > }$$
> >
> > It is tempting to say that the mean is $0$ because the Cauchy distribution is symmetric about $0$, but this is incorrect.
> >
> > Symmetry suggests cancellation, but mathematically that would require the positive and negative contributions to be finite. Here both are infinite.
>
> > [!tip]- Important Distinction
> > $$\boxed{
> > E[X^+]=E[X^-]=\infty
> > \quad\not\Rightarrow\quad
> > E[X]=0.
> > }$$
> >
> > Instead:
> > $$\boxed{E[X]\text{ is undefined}.}$$
> >
> > This is why the Cauchy distribution is a standard example showing that **not every random variable has an expectation**.
>
> > [!important]- Final Picture
> > The construction proceeds from simple to general:
> >
> > $$\boxed{
> > \text{Simple RV}
> > \longrightarrow
> > \text{Nonnegative RV}
> > \longrightarrow
> > \text{General RV}
> > }$$
> >
> > **Simple $X$:**
> > $$E[X]=\sum_i x_iP(X=x_i).$$
> >
> > **Nonnegative $X$:**
> > $$X_n\uparrow X
> > \quad\Rightarrow\quad
> > E[X]=\lim_{n\to\infty}E[X_n].$$
> >
> > **General $X$:**
> > $$X=X^+-X^-,$$
> > $$E[X]=E[X^+]-E[X^-],$$
> > provided we do not encounter $\infty-\infty$.
> >
> > Ultimately, for a random variable with CDF $F$:
> > $$\boxed{
> > E[X]=\int_{-\infty}^{\infty}x\,dF(x)
> > }$$
> > whenever the expectation is well-defined.

---

> [!important]- Correlation Coefficient
> > [!abstract]- Definition
> > Recall the covariance:
> > $$\operatorname{Cov}(X,Y)
> > =E[(X-E[X])(Y-E[Y])].$$
> >
> > Covariance can take **any real value**:
> > $$\operatorname{Cov}(X,Y)\in\mathbb R.$$
> >
> > Therefore, covariance is not naturally restricted to a fixed scale, making it difficult to compare the strength of relationships between different pairs of random variables.
> >
> > We normalize covariance by the standard deviations.
> >
> > Assuming
> > $$\operatorname{Var}(X)>0,\qquad
> > \operatorname{Var}(Y)>0,$$
> > the **correlation coefficient** is
> > $$\boxed{
> > \rho(X,Y)=
> > \frac{\operatorname{Cov}(X,Y)}
> > {\sqrt{\operatorname{Var}(X)\operatorname{Var}(Y)}}.
> > }$$
> >
> > Since
> > $$\sigma_X=\sqrt{\operatorname{Var}(X)},\qquad
> > \sigma_Y=\sqrt{\operatorname{Var}(Y)},$$
> > we can also write
> > $$\boxed{
> > \rho(X,Y)=\frac{\operatorname{Cov}(X,Y)}
> > {\sigma_X\sigma_Y}.
> > }$$
>
> > [!tip]- Why Normalize?
> > Covariance depends on the scale of $X$ and $Y$.
> >
> > For example, changing the units of $X$ changes its covariance with $Y$.
> >
> > Correlation removes this scale dependence by dividing by the product of the standard deviations.
> >
> > Therefore,
> > $$\boxed{-1\le\rho(X,Y)\le1.}$$
> >
> > Correlation is **dimensionless** and always lies in the fixed interval $[-1,1]$.
>
> > [!abstract]- Cauchy–Schwarz Inequality
> > The bound on correlation follows from the **Cauchy–Schwarz inequality**.
> >
> > For random variables $U$ and $V$ with finite second moments:
> > $$\boxed{
> > |E[UV]|
> > \le
> > \sqrt{E[U^2]E[V^2]}.
> > }$$
> >
> > Apply this to the centered random variables
> > $$U=X-E[X],$$
> > $$V=Y-E[Y].$$
> >
> > Then
> > $$E[UV]=\operatorname{Cov}(X,Y),$$
> > $$E[U^2]=\operatorname{Var}(X),$$
> > $$E[V^2]=\operatorname{Var}(Y).$$
> >
> > Hence,
> > $$|\operatorname{Cov}(X,Y)|
> > \le
> > \sqrt{\operatorname{Var}(X)\operatorname{Var}(Y)}.$$
> >
> > Dividing by the positive denominator:
> > $$\boxed{
> > |\rho(X,Y)|\le1.
> > }$$
>
> > [!important]- Equality Case
> > Cauchy–Schwarz has equality exactly when the two random variables are linearly dependent almost surely.
> >
> > Applied to
> > $$U=X-E[X],\qquad V=Y-E[Y],$$
> > this means
> > $$U+cV=0$$
> > almost surely for some constant $c$.
> >
> > Therefore,
> > $$X-E[X]+c(Y-E[Y])=0
> > \quad\text{a.s.}$$
> >
> > Rearranging:
> > $$X+cY
> > =
> > E[X]+cE[Y]
> > \quad\text{a.s.}$$
> >
> > Thus,
> > $$\boxed{
> > |\rho(X,Y)|=1
> > \iff
> > X+cY\text{ is constant almost surely}
> > }$$
> > for some constant $c$.
> >
> > Equivalently, there exist constants $a,b$ (with the relationship nontrivial) such that
> > $$X=aY+b\quad\text{a.s.}$$
>
> > [!abstract]- Interpretation
> > $$\rho(X,Y)>0$$
> > means that $X$ and $Y$ tend to move in the same linear direction.
> >
> > $$\rho(X,Y)<0$$
> > means that they tend to move in opposite linear directions.
> >
> > $$\rho(X,Y)=0$$
> > means that they are **uncorrelated**, i.e.
> > $$\operatorname{Cov}(X,Y)=0.$$
> >
> > Importantly,
> > $$\boxed{
> > \rho(X,Y)=0
> > \not\Rightarrow
> > X\text{ and }Y\text{ are independent}
> > }$$
> > in general.
> >
> > However, for jointly Gaussian random variables:
> > $$\boxed{
> > \rho(X,Y)=0
> > \iff
> > X\perp Y.
> > }$$
>
> > [!example]- Extreme Correlation
> > If
> > $$Y=aX+b,\qquad a>0,$$
> > then
> > $$\boxed{\rho(X,Y)=1.}$$
> >
> > If
> > $$Y=aX+b,\qquad a<0,$$
> > then
> > $$\boxed{\rho(X,Y)=-1.}$$
> >
> > Thus, $|\rho|=1$ means there is an exact linear relationship between the variables (almost surely).
>
> > [!important]- Key Takeaways
> > **Covariance:**
> > $$\operatorname{Cov}(X,Y)
> > =E[(X-E[X])(Y-E[Y])].$$
> >
> > **Correlation:**
> > $$\boxed{
> > \rho(X,Y)=
> > \frac{\operatorname{Cov}(X,Y)}
> > {\sigma_X\sigma_Y}.
> > }$$
> >
> > **Bound:**
> > $$\boxed{-1\le\rho(X,Y)\le1.}$$
> >
> > **Perfect correlation:**
> > $$\boxed{
> > |\rho(X,Y)|=1
> > \iff
> > X+cY\text{ is constant a.s.}
> > }$$
> >
> > **Zero correlation:**
> > $$\rho(X,Y)=0
> > \iff
> > \operatorname{Cov}(X,Y)=0.$$
> >
> > But generally:
> > $$\boxed{
> > \text{independence}\Rightarrow\text{zero correlation},
> > \qquad
> > \text{zero correlation}\not\Rightarrow\text{independence}.
> > }$$

> [!important]- Cauchy–Schwarz Inequality
> > [!abstract]- Theorem
> > For random variables $X$ and $Y$ with finite second moments,
> > $$\boxed{
> > \big(E[XY]\big)^2
> > \le
> > E[X^2]E[Y^2].
> > }$$
> >
> > Equality holds if and only if there exists a constant $c\in\mathbb R$ such that
> > $$\boxed{
> > P(Y=cX)=1.
> > }$$
> >
> > We say that
> > $$\boxed{Y=cX\quad\text{almost surely (a.s.)}.}$$
>
> > [!tip]- Main Idea of the Proof
> > Consider the random variable
> > $$\boxed{Z=tX-Y}$$
> > for any real number $t$.
> >
> > Since the square of every real number is nonnegative,
> > $$Z^2\ge0.$$
> >
> > Therefore,
> > $$E[Z^2]\ge0.$$
> >
> > Expanding:
> > $$E[(tX-Y)^2]\ge0.$$
> >
> > Hence,
> > $$t^2E[X^2]-2tE[XY]+E[Y^2]\ge0
> > \qquad\forall t\in\mathbb R.$$
> >
> > Thus, we have a quadratic polynomial in $t$:
> > $$q(t)=
> > E[X^2]t^2-2E[XY]t+E[Y^2].$$
> >
> > The crucial fact is:
> > $$\boxed{q(t)\ge0\quad\text{for every }t.}$$
>
> > [!abstract]- Using the Discriminant
> > A quadratic
> > $$at^2+bt+c$$
> > with $a>0$ can remain nonnegative for every real $t$ only if it has at most one real root.
> >
> > Therefore, its discriminant must satisfy
> > $$\Delta\le0.$$
> >
> > For
> > $$q(t)=
> > E[X^2]t^2-2E[XY]t+E[Y^2],$$
> > we have
> > $$a=E[X^2],$$
> > $$b=-2E[XY],$$
> > $$c=E[Y^2].$$
> >
> > Thus,
> > $$\Delta
> > =
> > [-2E[XY]]^2
> > -4E[X^2]E[Y^2].$$
> >
> > Since $\Delta\le0$:
> > $$4(E[XY])^2
> > -4E[X^2]E[Y^2]\le0.$$
> >
> > Divide by $4$:
> > $$\boxed{
> > (E[XY])^2
> > \le
> > E[X^2]E[Y^2].
> > }$$
> >
> > This is the Cauchy–Schwarz inequality.
>
> > [!abstract]- Equality Case
> > Equality occurs when
> > $$\big(E[XY]\big)^2
> > =
> > E[X^2]E[Y^2].$$
> >
> > This means the discriminant is zero:
> > $$\Delta=0.$$
> >
> > Therefore, the quadratic has a real root, say
> > $$t=c.$$
> >
> > At this value,
> > $$q(c)=E[(cX-Y)^2]=0.$$
> >
> > But $(cX-Y)^2\ge0$ always.
> >
> > A nonnegative random variable can have expectation $0$ only if it equals $0$ almost surely:
> > $$E[(cX-Y)^2]=0
> > \Rightarrow
> > (cX-Y)^2=0\quad\text{a.s.}$$
> >
> > Therefore,
> > $$cX-Y=0\quad\text{a.s.}$$
> >
> > Hence,
> > $$\boxed{Y=cX\quad\text{a.s.}}$$
>
> > [!tip]- Why Does $E[W]=0$ Imply $W=0$ a.s.?
> > If
> > $$W\ge0$$
> > and
> > $$E[W]=0,$$
> > then $W$ cannot be positive with positive probability.
> >
> > Otherwise, if
> > $$P(W>0)>0,$$
> > there would be some positive contribution to the expectation.
> >
> > Therefore,
> > $$\boxed{
> > W\ge0,\ E[W]=0
> > \Rightarrow
> > W=0\text{ a.s.}
> > }$$
> >
> > Applying this to
> > $$W=(cX-Y)^2$$
> > gives the equality condition.
>
> > [!abstract]- Connection to Correlation
> > Apply Cauchy–Schwarz to the centered variables
> > $$U=X-E[X],$$
> > $$V=Y-E[Y].$$
> >
> > Then
> > $$E[UV]=\operatorname{Cov}(X,Y),$$
> > $$E[U^2]=\operatorname{Var}(X),$$
> > $$E[V^2]=\operatorname{Var}(Y).$$
> >
> > Cauchy–Schwarz gives
> > $$\operatorname{Cov}(X,Y)^2
> > \le
> > \operatorname{Var}(X)\operatorname{Var}(Y).$$
> >
> > Taking square roots:
> > $$|\operatorname{Cov}(X,Y)|
> > \le
> > \sqrt{\operatorname{Var}(X)\operatorname{Var}(Y)}.$$
> >
> > Dividing by the standard deviations gives
> > $$\boxed{|\rho(X,Y)|\le1.}$$
> >
> > So the bound on the correlation coefficient is a direct consequence of Cauchy–Schwarz.
>
> > [!important]- Key Takeaway
> > The whole proof follows one simple chain:
> >
> > $$Z=tX-Y$$
> > $$\Downarrow$$
> > $$E[Z^2]\ge0$$
> > $$\Downarrow$$
> > $$E[X^2]t^2-2E[XY]t+E[Y^2]\ge0$$
> > $$\Downarrow$$
> > $$\Delta\le0$$
> > $$\Downarrow$$
> > $$\boxed{(E[XY])^2\le E[X^2]E[Y^2]}. $$
> >
> > Equality:
> > $$\Delta=0
> > \Rightarrow
> > E[(cX-Y)^2]=0
> > \Rightarrow
> > \boxed{Y=cX\text{ a.s.}}$$
> >
> > **Memory trick:**
> > $$\boxed{
> > \text{nonnegative square}
> > \rightarrow
> > \text{quadratic}
> > \rightarrow
> > \text{discriminant}
> > \rightarrow
> > \text{Cauchy–Schwarz}
> > }$$


