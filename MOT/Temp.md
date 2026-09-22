
> [!important]- Row Rank = Column Rank
>
> > [!abstract]- Different Dimensions
> >
> > Suppose:
> >
> > $$
> > A\in\mathbb R^{m\times n}
> > $$
> >
> > Then:
> >
> > - $m$ = number of rows
> > - $n$ = number of columns
> >
> > But the row space and column space live in different spaces:
> >
> > $$
> > \text{Row Space}\subseteq\mathbb R^n
> > $$
> >
> > $$
> > \text{Column Space}\subseteq\mathbb R^m
> > $$
> >
> > So they **do not have to have the same dimension as vectors**.
>
> > [!abstract]- Example
> >
> > Consider:
> >
> > $$
> > A=
> > \begin{bmatrix}
> > 1&0&1\\
> > 0&1&1
> > \end{bmatrix}
> > $$
> >
> > This is a $2\times3$ matrix.
> >
> > Therefore:
> >
> > - Each row has $3$ components → row vectors belong to $\mathbb R^3$.
> > - Each column has $2$ components → column vectors belong to $\mathbb R^2$.
> >
> > So rows and columns clearly **do not have the same vector dimension**.
>
> > [!abstract]- But Their Rank Is the Same
> >
> > The columns are:
> >
> > $$
> > c_1=
> > \begin{bmatrix}1\\0\end{bmatrix},
> > \quad
> > c_2=
> > \begin{bmatrix}0\\1\end{bmatrix},
> > \quad
> > c_3=
> > \begin{bmatrix}1\\1\end{bmatrix}
> > $$
> >
> > Since:
> >
> > $$
> > c_3=c_1+c_2
> > $$
> >
> > only $2$ columns are independent.
> >
> > Therefore:
> >
> > $$
> > \text{Column Rank}=2
> > $$
> >
> > The rows are:
> >
> > $$
> > r_1=[1,0,1],
> > \qquad
> > r_2=[0,1,1]
> > $$
> >
> > These two rows are independent, so:
> >
> > $$
> > \text{Row Rank}=2
> > $$
> >
> > Hence:
> >
> > $$
> > \boxed{\text{Row Rank}=\text{Column Rank}=2}
> > $$
>
> > [!abstract]- Physical Intuition
> >
> > Think of the matrix as a machine:
> >
> > $$
> > A:\mathbb R^n\rightarrow\mathbb R^m
> > $$
> >
> > It takes an $n$-dimensional input and produces an $m$-dimensional output.
> >
> > **Columns ask:**
> >
> > > How many independent output directions can this machine produce?
> >
> > **Rows ask:**
> >
> > > How many independent combinations of the input coordinates actually matter?
> >
> > These are two different perspectives of the **same transformation**.
> >
> > The number of independent directions/information is therefore the same:
> >
> > $$
> > \boxed{
> > \dim(\text{Row Space})
> > =
> > \dim(\text{Column Space})
> > =
> > \operatorname{rank}(A)
> > }
> > $$
>
> > [!abstract]- Most Important Distinction
> >
> > Do **not** think:
> >
> > > "Rows and columns have the same dimension because their ranks are equal."
> >
> > Instead think:
> >
> > > **Rows and columns can live in different-dimensional spaces, but they contain the same number of independent directions.**
> >
> > For an $m\times n$ matrix:
> >
> > $$
> > \text{Row Space}\subseteq\mathbb R^n
> > $$
> >
> > $$
> > \text{Column Space}\subseteq\mathbb R^m
> > $$
> >
> > while:
> >
> > $$
> > \boxed{
> > \dim(\text{Row Space})
> > =
> > \dim(\text{Column Space})
> > =
> > \operatorname{rank}(A)
> > }
> > $$
>
> > [!abstract]- One-Line Intuition
> >
> > $$
> > \boxed{\text{Rank = number of independent pieces of information in the transformation}}
> > $$



