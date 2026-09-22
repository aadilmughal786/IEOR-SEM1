
> [!important]- MATLAB Fundamentals
> 
>  MATLAB is a numerical computing environment primarily designed for:
>  - numerical computation
>  - matrix/vector operations
>  - visualization
>  - simulation
>  - optimization
>  - data analysis
>  - mathematical modeling
>
>---
>
> > [!tip]- A key idea in MATLAB
> > **Everything is treated as an array/matrix.**
> >
> > Therefore:
> > - scalar → $1\times1$ matrix
> > - row vector → $1\times n$ matrix
> > - column vector → $n\times1$ matrix
> > - matrix → $m\times n$ array
>
> > [!abstract]- Command Window
> > The **Command Window** allows you to execute MATLAB commands interactively.
> >
> > Example:
> > ```matlab
> > a = 3
> > b = 5
> > a + b
> > ```
> >
> > MATLAB immediately displays the result.
> >
> >---
> >
> > **This is useful for:**
> > - testing commands
> > - checking syntax
> > - experimenting with calculations
> > - understanding MATLAB behavior
>
> > [!abstract]- Comments
> > Comments are notes written inside MATLAB code that MATLAB does not execute.
> >
> > Use `%` to create a comment.
> >
> > ```matlab
> > % This is a comment
> > a = 3;
> > ```
> >
> > Everything after `%` on that line is ignored by MATLAB.
> >
> > Good practice:
> > ```matlab
> > % Compute the square of a
> > a = 5;
> > a^2
> > ```
> >
> > Comments explain **why** a piece of code is being written.
>
> > [!abstract]- Basic Arithmetic Operators
> > MATLAB uses the standard arithmetic operators:
> >
> > | Operation | MATLAB |
> > |---|---|
> > | Addition | `+` |
> > | Subtraction | `-` |
> > | Multiplication | `*` |
> > | Division | `/` |
> > | Power | `^` |
> >
> > **Example:**
> > 
> > ```matlab
> > 3 + 5
> > 7 - 2
> > 4 * 3
> > 10 / 2
> > 2^3
> > ```
> >
> >---
> >
> > MATLAB follows the usual order of operations.
> >
> > ```matlab
> > 3 * (1 + 4)^2
> > ```
> >
> > First:
> > $1+4=5$
> >
> > Then:
> > $5^2=25$
> >
> > Finally:
> > $3(25)=75$
>
>---
>
> > [!abstract]- Mathematical Functions
> > MATLAB provides many built-in mathematical functions.
> >
> > Common examples:
> >
> > ```matlab
> > sin(x)
> > cos(x)
> > tan(x)
> > exp(x)
> > log(x)
> > sqrt(x)
> > ```
> >
> > Important:
> >
> > `sin`, `cos`, and `tan` use **radians**, not degrees.
> >
> > Example:
> > ```matlab
> > sin(pi/2)
> > ```
> >
> > gives: $1$
> >
> > ```matlab
> > exp(3)
> > ```
> >
> > gives: $e^3$
> >
> > ```matlab
> > log(3)
> > ```
> >
> > gives: $\ln(3)$
> >
> > MATLAB's `log()` means the **natural logarithm**.
>
> > [!abstract]- Variables (see workspace)
> > A variable stores a value.
> >
> > ```matlab
> > a = 3;
> > b = 10;
> > ```
> >
> > MATLAB creates the variables `a` and `b` in the **workspace**.
> >
> > You can then use them:
> >
> > ```matlab
> > c = a + b;
> > ```
> >
> > MATLAB is dynamically typed, so you do not need to declare the data type first.
> >
> > A variable can also store a vector:
> >
> > ```matlab
> > b = [1 5 7 3 6];
> > ```
>
> > [!abstract]- Row Vector
> > A row vector has one row and multiple columns.
> >
> > ```matlab
> > b = [1 5 7 3 6];
> > ```
> >
> > Its dimensions are:
> >
> > $1\times5$
> >
> > Elements are separated by spaces or commas:
> >
> > ```matlab
> > b = [1 5 7 3 6];
> > ```
> >
> > or
> >
> > ```matlab
> > b = [1, 5, 7, 3, 6];
> > ```
>
> > [!abstract]- Column Vector
> > A column vector has one column and multiple rows.
> >
> > ```matlab
> > c = [1; 5; 1; 0; -2];
> > ```
> >
> > Its dimensions are:
> >
> > $5\times1$
> >
> > The semicolon `;` inside `[...]` separates rows.
> >
> > ```matlab
> > [1; 2; 3]
> > ```
> >
> > gives:
> >
> > $$
> > \begin{bmatrix}
> > 1\\
> > 2\\
> > 3
> > \end{bmatrix}
> > $$
>
>---
>
> > [!abstract]- Transpose
> > The transpose operator `'` changes rows into columns and columns into rows.
> >
> > ```matlab
> > b = [1 2 3 4];
> > c = b';
> > ```
> >
> > `b` is:
> >
> > $1\times4$
> >
> > while `c` is:
> >
> > $4\times1$
> >
> > Therefore:
> >
> > ```matlab
> > c = [1 2 3 4]';
> > ```
> >
> > creates a column vector.
>
> > [!abstract]- Indexing
> > MATLAB uses **1-based indexing**.
> >
> > This means the first element has index `1`, not `0`.
> >
> > ```matlab
> > b = [1 5 7 3 6];
> > b(1)
> > ```
> >
> > gives: `1`
> >
> > ```matlab
> > b(3)
> > ```
> >
> > gives: `7`
> >
> > Therefore:
> >
> > ```matlab
> > b(k)
> > ```
> >
> > accesses the $k$-th element.
>
>---
>
> > [!important]- Matrix Multiplication vs Element-wise Multiplication
> > This is one of the **most important MATLAB concepts**.
> >
> > `*` means **matrix multiplication**.
> >
> > `.*` means **element-by-element multiplication**.
> >
> > Example:
> >
> > ```matlab
> > a = [1 2 3];
> > b = [4 5 6];
> > ```
> >
> > Element-wise multiplication:
> >
> > ```matlab
> > a .* b
> > ```
> >
> > gives:
> >
> > ```text
> > [4 10 18]
> > ```
> >
> > because:
> >
> > $[1(4),2(5),3(6)]$
> >
> > But:
> >
> > ```matlab
> > a * b
> > ```
> >
> > is matrix multiplication and is not valid for two $1\times3$ row vectors.
> >
> > The dimensions must be compatible for matrix multiplication:
> >
> > $$
> > (m\times n)(n\times p)=(m\times p)
> > $$
>
> > [!important]- Element-wise Operators
> > MATLAB uses a dot `.` before an operator when you want the operation to be performed **element by element**.
> >
> > Important operators:
> >
> > | Mathematical operation | MATLAB |
> > |---|---|
> > | Matrix multiplication | `*` |
> > | Element-wise multiplication | `.*` |
> > | Matrix right division | `/` |
> > | Element-wise division | `./` |
> > | Matrix power | `^` |
> > | Element-wise power | `.^` |
> >
> > Example:
> >
> > ```matlab
> > x = [1 2 3];
> > x.^2
> > ```
> >
> > gives:
> >
> > ```text
> > [1 4 9]
> > ```
> >
> > This means:
> >
> > $$
> > [1^2,\;2^2,\;3^2]
> > $$
> >
> > Similarly:
> >
> > ```matlab
> > x ./ 2
> > ```
> >
> > divides every element by $2$.
>
> > [!important]- Why `.^` Matters
> > Suppose:
> >
> > ```matlab
> > x = [1 2 3 4];
> > ```
> >
> > If you want:
> >
> > $$
> > [1^2,2^2,3^2,4^2]
> > $$
> >
> > you must use:
> >
> > ```matlab
> > x.^2
> > ```
> >
> > not:
> >
> > ```matlab
> > x^2
> > ```
> >
> > `x^2` asks MATLAB to perform **matrix power**, while `x.^2` squares each element.
>
>---
>
> > [!abstract]- Applying Functions to Vectors
> > Many MATLAB functions can operate directly on vectors.
> >
> > Example:
> >
> > ```matlab
> > b = [1 5 7 3 6];
> > y = exp(b);
> > ```
> >
> > This produces:
> >
> > $$
> > [e^1,e^5,e^7,e^3,e^6]
> > $$
> >
> > Similarly:
> >
> > ```matlab
> > log(y)
> > ```
> >
> > returns approximately the original vector `b`.
> >
> > Conceptually:
> >
> > $$
> > \log(e^x)=x
> > $$
>
> > [!abstract]- `sum` and `prod`
> > `sum()` adds elements.
> >
> > ```matlab
> > b = [1 5 7 3 6];
> > sum(b)
> > ```
> >
> > gives:
> >
> > $$
> > 1+5+7+3+6=22
> > $$
> >
> >---
> >
> > `prod()` multiplies elements.
> >
> > ```matlab
> > prod(b)
> > ```
> >
> > gives:
> >
> > $$
> > 1\times5\times7\times3\times6
> > $$
>
>---
>
> > [!abstract]- Creating Vectors Using `:`
> > The colon operator `:` is one of the most useful MATLAB tools for creating sequences.
> >
> > Basic syntax:
> >
> > ```matlab
> > start:end
> > ```
> >
> > Example:
> >
> > ```matlab
> > c = 1:5
> > ```
> >
> > gives:
> >
> > ```text
> > [1 2 3 4 5]
> > ```
> >
> > The default step size is $1$.
>
> > [!abstract]- Colon Operator with Step Size
> > General syntax:
> >
> > ```matlab
> > start:step:end
> > ```
> >
> > Example:
> >
> > ```matlab
> > d = 1:2:15
> > ```
> >
> > gives:
> >
> > ```text
> > [1 3 5 7 9 11 13 15]
> > ```
> >
> > Here:
> > - start = $1$
> > - step = $2$
> > - end = $15$
> >
> > MATLAB continues adding the step until the next value would pass the endpoint.
>
> > [!important]- Creating Equally Spaced Values
> > Suppose we want exactly $n$ equally spaced values between $a$ and $b$, including both endpoints.
> >
> > The required step size is:
> >
> > $$
> > \Delta=\frac{b-a}{n-1}
> > $$
> >
> > Example:
> >
> > To create $9$ equally spaced values between $1$ and $4$:
> >
> > $$
> > \Delta=\frac{4-1}{9-1}
> > =\frac{3}{8}
> > $$
> >
> > Then:
> >
> > ```matlab
> > w = 1:(4-1)/8:4
> > ```
> >
> > gives $9$ values.
> >
> > Important distinction:
> >
> > ```matlab
> > start:step:end
> > ```
> >
> > specifies the **step size**.
> >
> > It does not specify the number of points.
>
> > [!warning]- Common Mistake: `n` vs `n-1`
> > If you want $n$ equally spaced points from $a$ to $b$, there are only $n-1$ intervals.
> >
> > Therefore:
> >
> > $$
> > \boxed{\Delta=\frac{b-a}{n-1}}
> > $$
> >
> > For example, $10$ points between $\pi/2$ and $\pi$ require:
> >
> > $$
> > \Delta=
> > \frac{\pi-\pi/2}{10-1}
> > =\frac{\pi}{18}
> > $$
> >
> > Not $\pi/20$.
>
>---
>
> > [!abstract]- Semicolon `;`
> > A semicolon at the end of a MATLAB command suppresses its output.
> >
> > Without semicolon:
> >
> > ```matlab
> > a = 10
> > ```
> >
> > MATLAB displays:
> >
> > ```text
> > a =
> >     10
> > ```
> >
> > With semicolon:
> >
> > ```matlab
> > a = 10;
> > ```
> >
> > MATLAB stores the value but does not display it.
> >
> > The variable still exists:
> >
> > ```matlab
> > ans
> > ```
> >
> > is **not** the general way to retrieve a suppressed variable.
> >
> > If you explicitly assigned:
> >
> > ```matlab
> > a = 10;
> > ```
> >
> > use:
> >
> > ```matlab
> > a
> > ```
> >
> > to display it.
>
> > [!warning]- `ans` and Semicolon
> > `ans` stores the result of an expression when you did not assign it to a variable.
> >
> > Example:
> >
> > ```matlab
> > 3 + 4
> > ```
> >
> > gives:
> >
> > ```text
> > ans =
> >      7
> > ```
> >
> > Then:
> >
> > ```matlab
> > ans
> > ```
> >
> > displays $7$.
> >
> > But if you write:
> >
> > ```matlab
> > a = 3 + 4;
> > ```
> >
> > the result is stored in `a`, not `ans`.
>
>---
>
> > [!abstract]- Script Files (`.m`)
> > A MATLAB script is a file containing MATLAB commands.
> >
> > MATLAB scripts normally use the extension:
> >
> > `.m`
> >
> > Example:
> >
> > ```text
> > ex1.m
> > ```
> >
> > A script can contain:
> >
> > ```matlab
> > % Calculate squares
> > x = 1:5;
> > y = x.^2;
> > ```
> >
> > The commands are executed sequentially from top to bottom.
>
> > [!abstract]- Creating and Running a Script
> > You can create a script using the MATLAB Editor.
> >
> > Example file:
> >
> > ```text
> > ex1.m
> > ```
> >
> > Put MATLAB commands inside it and save it.
> >
> > Then run the script using the **Run** button.
> >
> > You can also execute a script from the Command Window by typing:
> >
> > ```matlab
> > ex1
> > ```
> >
> > provided MATLAB can locate the file.
>
>---
>
> > [!warning]- Common MATLAB Mistakes
> > - Forgetting `.` in element-wise operations:
> >   ```matlab
> >   x^2
> >   ```
> >   vs
> >   ```matlab
> >   x.^2
> >   ```
> >
> > - Confusing `/` with `./`.
> >
> > - Confusing `*` with `.*`.
> >
> > - Forgetting that MATLAB indexing starts at `1`.
> >
> > - Assuming `log(x)` means $\log_{10}(x)$. In MATLAB, `log(x)` means $\ln(x)$.
> >
> > - Giving degrees to `sin()` or `cos()` without conversion.
> >
> > - Forgetting that vectors are arrays and therefore dimensions matter.
> >
> > - Assuming `start:step:end` guarantees a particular number of points.
> >
> > - Using `n` instead of `n-1` when calculating the spacing for exactly $n$ equally spaced points.
> >
> > - Forgetting that `;` suppresses displayed output.
>
> > [!tip]- Quick Mental Model
> > Think of MATLAB as an environment where you manipulate **arrays**.
> >
> > For scalar calculations:
> >
> > ```matlab
> > x = 5;
> > y = x^2;
> > ```
> >
> > For vector calculations:
> >
> > ```matlab
> > x = [1 2 3 4];
> > y = x.^2;
> > ```
> >
> > The major question to ask is:
> >
> > **"Am I performing a matrix operation or an element-wise operation?"**
> >
> > If you want to operate independently on every element of a vector, you will very often need:
> >
> > ```matlab
> > .*
> > ./
> > .^
> > ```
>
> > [!important]- Core Syntax to Remember
> > ```matlab
> > % Comment
> >
> > x = 5;                 % Assignment
> >
> > x + y                  % Addition
> > x - y                  % Subtraction
> > x * y                  % Matrix multiplication
> > x / y                  % Matrix division
> > x^2                    % Matrix power
> >
> > x .* y                 % Element-wise multiplication
> > x ./ y                 % Element-wise division
> > x .^ 2                 % Element-wise power
> >
> > x(3)                   % Third element
> >
> > [1 2 3 4]              % Row vector
> > [1; 2; 3; 4]           % Column vector
> >
> > 1:5                    % 1,2,3,4,5
> > 1:2:10                 % 1,3,5,7,9
> >
> > sin(x)
> > cos(x)
> > exp(x)
> > log(x)
> > sqrt(x)
> >
> > sum(x)
> > prod(x)
> > ```

> [!important]- MATLAB Matrices
> 
> > [!abstract]- Creating a Matrix
> > MATLAB represents a matrix using square brackets `[ ]`.
> >
> > Elements in the same row are separated by:
> >
> > - spaces
> > - commas
> >
> > Rows are separated using semicolons `;`.
> >
> > Example:
> >
> > ```matlab
> > A = [1 7 3; 4 0 6; 2 5 -1];
> > ```
> >
> > This creates:
> >
> > $$
> > A=
> > \begin{bmatrix}
> > 1&7&3\\
> > 4&0&6\\
> > 2&5&-1
> > \end{bmatrix}
> > $$
> >
> > The same matrix can be written using commas:
> >
> > ```matlab
> > A = [1,7,3; 4,0,6; 2,5,-1];
> > ```
> >
> > MATLAB therefore interprets:
> >
> > ```text
> > space/comma → next column
> > semicolon   → next row
> >```
>
> > [!abstract]- Matrix Dimensions
> > If a matrix has $m$ rows and $n$ columns, its size is:
> >
> > $m\times n$
> >
> > For example:
> >
> > ```matlab
> > A = [1 7 3; 4 0 6; 2 5 -1];
> > ```
> >
> > has:
> >
> > - $3$ rows
> > - $3$ columns
> > - size $3\times3$
> >
> > Check using:
> >
> > ```matlab
> > size(A)
> > ```
> >
> > MATLAB returns:
> >
> > ```text
> > 3     3
> > ```
>
>---
>
> > [!abstract]- Transpose
> > The transpose operator `'` exchanges rows and columns.
> >
> > ```matlab
> > A'
> > ```
> >
> > If:
> >
> > $$
> > A=
> > \begin{bmatrix}
> > 1&2&3\\
> > 4&5&6
> > \end{bmatrix}
> > $$
> >
> > then:
> >
> > $$
> > A'=
> > \begin{bmatrix}
> > 1&4\\
> > 2&5\\
> > 3&6
> > \end{bmatrix}
> > $$
> >
> > Therefore:
> >
> > $$
> > (m\times n)'=n\times m
> > $$
>
> > [!important]- Matrix Multiplication
> > MATLAB uses `*` for matrix multiplication.
> >
> > ```matlab
> > C = A * B;
> > ```
> >
> > Matrix multiplication is possible only when:
> >
> > $$
> > A_{m\times n}B_{n\times p}
> > $$
> >
> > The inner dimensions must match.
> >
> > The result has dimensions:
> >
> > $$
> > (m\times n)(n\times p)=m\times p
> > $$
> >
> > For two $3\times3$ matrices:
> >
> > ```matlab
> > C = A * B;
> > ```
> >
> > gives another $3\times3$ matrix.
> >
> > Important:
> >
> > Matrix multiplication is **not element-wise multiplication**.
>
> > [!important]- Element-wise Matrix Multiplication
> > MATLAB uses `.*` for element-by-element multiplication.
> >
> > ```matlab
> > C = A .* B;
> > ```
> >
> > If:
> >
> > $$
> > A=
> > \begin{bmatrix}
> > a_{11}&a_{12}\\
> > a_{21}&a_{22}
> > \end{bmatrix},
> > \quad
> > B=
> > \begin{bmatrix}
> > b_{11}&b_{12}\\
> > b_{21}&b_{22}
> > \end{bmatrix}
> > $$
> >
> > then:
> >
> > $$
> > A.*B=
> > \begin{bmatrix}
> > a_{11}b_{11}&a_{12}b_{12}\\
> > a_{21}b_{21}&a_{22}b_{22}
> > \end{bmatrix}
> > $$
> >
> > This is different from:
> >
> > ```matlab
> > A * B
> > ```
>
> > [!important]- Matrix Power vs Element-wise Power
> > `^` means matrix power.
> >
> > ```matlab
> > D = B^2;
> > ```
> >
> > means:
> >
> > $$
> > B^2=B B
> > $$
> >
> > It is matrix multiplication of $B$ with itself.
> >
> > On the other hand:
> >
> > ```matlab
> > D = B.^2;
> > ```
> >
> > squares every element independently.
> >
> > Therefore:
> >
> > ```matlab
> > B^2
> > ```
> >
> > and
> >
> > ```matlab
> > B.^2
> > ```
> >
> > generally produce different results.
>
>---
>
> > [!abstract]- Accessing a Single Matrix Element
> > MATLAB uses:
> >
> > ```matlab
> > A(row, column)
> > ```
> >
> > Example:
> >
> > ```matlab
> > A(1,2)
> > ```
> >
> > accesses the element in:
> >
> > - row $1$
> > - column $2$
> >
> > For:
> >
> > ```text
> > A = [1 7 3
> >      4 0 6
> >      2 5 -1]
> > ```
> >
> > ```matlab
> > A(1,2)
> > ```
> >
> > gives:
> >
> > $7$
>
> > [!abstract]- Selecting an Entire Column
> > The colon `:` means "all elements in this dimension".
> >
> > ```matlab
> > A(:,2)
> > ```
> >
> > means:
> >
> > - all rows
> > - column $2$
> >
> > Therefore it extracts the second column.
> >
> > For the example matrix:
> >
> > ```matlab
> > A(:,2)
> > ```
> >
> > gives:
> >
> > $$
> > \begin{bmatrix}
> > 7\\
> > 0\\
> > 5
> > \end{bmatrix}
> > $$
>
> > [!abstract]- Selecting an Entire Row
> > ```matlab
> > A(1,:)
> > ```
> >
> > means:
> >
> > - row $1$
> > - all columns
> >
> > Therefore:
> >
> > ```matlab
> > A(1,:)
> > ```
> >
> > gives:
> >
> > ```text
> > [1 7 3]
> > ```
>
>---
>
> > [!abstract]- Deleting a Row
> > MATLAB allows rows to be deleted by assigning an empty matrix `[]`.
> >
> > ```matlab
> > A(2,:) = [];
> > ```
> >
> > This removes row $2$ from `A`.
> >
> > Similarly:
> >
> > ```matlab
> > A(:,3) = [];
> > ```
> >
> > removes column $3$.
> >
> > General idea:
> >
> > ```matlab
> > A(row,:) = [];
> > ```
> >
> > deletes a row.
> >
> > ```matlab
> > A(:,column) = [];
> > ```
> >
> > deletes a column.
>
> > [!abstract]- `size(A)`
> > ```matlab
> > size(A)
> > ```
> >
> > returns the dimensions of matrix `A`.
> >
> > For a $3\times3$ matrix:
> >
> > ```text
> > 3     3
> > ```
> >
> > You can also extract the dimensions:
> >
> > ```matlab
> > [m,n] = size(A);
> > ```
> >
> > Here:
> >
> > - `m` = number of rows
> > - `n` = number of columns
>
> > [!warning]- MATLAB Is Case-sensitive
> > MATLAB distinguishes between uppercase and lowercase names.
> >
> > These are different variables:
> >
> > ```matlab
> > A
> > a
> > ```
> >
> > For example:
> >
> > ```matlab
> > A = [1 2; 3 4];
> > a = 3;
> > ```
> >
> > Here `A` is a matrix while `a` is a scalar.
> >
> > Therefore:
> >
> > ```matlab
> > a * A
> > ```
> >
> > is scalar multiplication.
> >
> > Be consistent with variable names.
>
>---
>
> > [!abstract]- Determinant
> > The determinant of a square matrix can be calculated using:
> >
> > ```matlab
> > det(A)
> > ```
> >
> > Example:
> >
> > ```matlab
> > d = det(A);
> > ```
> >
> > The determinant is important for determining whether a square matrix is invertible.
> >
> > For a square matrix:
> >
> > $$
> > \det(A)\neq0
> > $$
> >
> > implies that $A$ is invertible.
>
> > [!abstract]- Rank
> > MATLAB computes matrix rank using:
> >
> > ```matlab
> > rank(A)
> > ```
> >
> > Rank represents the number of linearly independent rows or columns.
> >
> > For an $n\times n$ matrix:
> >
> > $$
> > \operatorname{rank}(A)=n
> > $$
> >
> > means the matrix has full rank.
>
> > [!important]- Eigenvalues
> > MATLAB computes eigenvalues using:
> >
> > ```matlab
> > eig(A)
> > ```
> >
> > Example:
> >
> > ```matlab
> > evals = eig(A);
> > ```
> >
> > `evals` contains the eigenvalues of `A`.
> >
> > Mathematically, an eigenvalue $\lambda$ satisfies:
> >
> > $$
> > Av=\lambda v
> > $$
> >
> > for some nonzero vector $v$.
>
> > [!important]- Eigenvectors and Eigenvalue Matrix
> > The command:
> >
> > ```matlab
> > [P,Lambda] = eig(A);
> > ```
> >
> > returns:
> >
> > - `P` → matrix whose columns are eigenvectors
> > - `Lambda` → diagonal matrix containing eigenvalues
> >
> >---
> >
> > When $A$ is diagonalizable:
> >
> > $$
> > A=P\Lambda P^{-1}
> > $$
> >
> > Equivalently:
> >
> > $$
> > AP=P\Lambda
> > $$
> >
> > Each column of `P` is an eigenvector corresponding to the eigenvalue in the same diagonal position of `Lambda`.
>
>---
>
> > [!abstract]- Matrix Inverse
> > MATLAB can compute the inverse of a square matrix using:
> >
> > ```matlab
> > inv(A)
> > ```
> >
> > The inverse exists only when:
> >
> > $$
> > \det(A)\neq0
> > $$
> >
> > and equivalently:
> >
> > $$
> > \operatorname{rank}(A)=n
> > $$
> >
> > for an $n\times n$ matrix.
> >
> > The inverse satisfies:
> >
> > $$
> > AA^{-1}=A^{-1}A=I
> > $$
> >
> > where $I$ is the identity matrix.
>
> > [!warning]- Do Not Prefer `inv(A)` for Solving Linear Systems
> > Although MATLAB provides:
> >
> > ```matlab
> > inv(A)
> > ```
> >
> > explicitly computing the inverse is usually unnecessary when solving:
> >
> > $$
> > Ax=b
> > $$
> >
> > MATLAB provides the backslash operator:
> >
> > ```matlab
> > x = A\b;
> > ```
> >
> > This is generally more efficient and numerically preferable.
> >
> > For this lab, however, `inv(A)` is useful because the exercise explicitly asks you to compute the inverse.
>
> > [!important]- Right Matrix Division `/`
> > MATLAB:
> >
> > ```matlab
> > g / h
> > ```
> >
> > is conceptually related to:
> >
> > ```matlab
> > g * inv(h)
> > ```
> >
> > when the relevant inverse exists.
> >
> > More precisely:
> >
> > $$
> > G/H = G H^{-1}
> > $$
> >
> > MATLAB's matrix division operators are designed to solve matrix equations efficiently rather than simply forming explicit inverses.
>
> > [!important]- Left Matrix Division `\`
> > MATLAB:
> >
> > ```matlab
> > g \ h
> > ```
> >
> > is conceptually related to:
> >
> > ```matlab
> > inv(g) * h
> > ```
> >
> > when the inverse exists.
> >
> > It solves:
> >
> > $$
> > GX=H
> > $$
> >
> > for $X$.
> >
> > Therefore:
> >
> > ```matlab
> > x = A\b;
> > ```
> >
> > means:
> >
> > $$
> > Ax=b
> > $$
> >
> > and asks MATLAB to find $x$.
>
>---
>
> > [!abstract]- Identity Matrix
> > MATLAB uses `eye()` to create an identity matrix.
> >
> > ```matlab
> > eye(4)
> > ```
> >
> > gives:
> >
> > $$
> > I_4=
> > \begin{bmatrix}
> > 1&0&0&0\\
> > 0&1&0&0\\
> > 0&0&1&0\\
> > 0&0&0&1
> > \end{bmatrix}
> > $$
> >
> > You can also write:
> >
> > ```matlab
> > eye(4,4)
> > ```
> >
> > For:
> >
> > ```matlab
> > eye(4,5)
> > ```
> >
> > MATLAB creates a $4\times5$ matrix with ones on the main diagonal and zeros elsewhere.
>
> > [!abstract]- Matrix of Ones
> > ```matlab
> > ones(3,4)
> > ```
> >
> > creates a $3\times4$ matrix containing only ones.
> >
> > ```text
> > 1 1 1 1
> > 1 1 1 1
> > 1 1 1 1
> > ```
>
> > [!abstract]- Matrix of Zeros
> > ```matlab
> > zeros(4,3)
> > ```
> >
> > creates a $4\times3$ matrix containing only zeros.
>
> > [!abstract]- Random Matrix
> > ```matlab
> > rand(5,4)
> > ```
> >
> > creates a $5\times4$ matrix containing random numbers **uniformly** distributed between $0$ and $1$.
> >
> > The values will generally be different each time MATLAB generates them.
>
>---
>
> > [!abstract]- Diagonal Matrix
> > Suppose:
> >
> > ```matlab
> > d = 1:5;
> > ```
> >
> > so:
> >
> > ```text
> > d = [1 2 3 4 5]
> > ```
> >
> > Then:
> >
> > ```matlab
> > main = diag(d);
> > ```
> >
> > creates:
> >
> > $$
> > \begin{bmatrix}
> > 1&0&0&0&0\\
> > 0&2&0&0&0\\
> > 0&0&3&0&0\\
> > 0&0&0&4&0\\
> > 0&0&0&0&5
> > \end{bmatrix}
> > $$
> >
> > `diag(d)` puts the elements of `d` on the **main diagonal**.
>
> > [!abstract]- Superdiagonal
> > ```matlab
> > super = diag(d,1);
> > ```
> >
> > The second argument `1` shifts the diagonal one position above the main diagonal.
> >
> > For:
> >
> > ```matlab
> > d = 1:5;
> > ```
> >
> > the result is:
> >
> > $$
> > \begin{bmatrix}
> > 0&1&0&0&0&0\\
> > 0&0&2&0&0&0\\
> > 0&0&0&3&0&0\\
> > 0&0&0&0&4&0\\
> > 0&0&0&0&0&5
> > \end{bmatrix}
> > $$
> >
> > MATLAB automatically chooses the required dimensions when creating the diagonal from a vector.
>
> > [!abstract]- Subdiagonal
> > ```matlab
> > sub = diag(d,-1);
> > ```
> >
> > The `-1` shifts the diagonal one position below the main diagonal.
> >
> > Conceptually:
> >
> > ```text
> > diag(d,0)   → main diagonal
> > diag(d,1)   → one above
> > diag(d,-1)  → one below
> > ```
>
>---
>
> > [!abstract]- Combining Matrices
> > MATLAB allows matrices to be joined horizontally or vertically.
> >
> > Horizontal concatenation:
> >
> > ```matlab
> > C = [A B];
> > ```
> >
> > requires `A` and `B` to have the same number of rows.
> >
> > Vertical concatenation:
> >
> > ```matlab
> > C = [A; B];
> > ```
> >
> > requires `A` and `B` to have the same number of columns.
> >
> > A vector can also be transposed before concatenation:
> >
> > ```matlab
> > E = [B, [2 5 7]'];
> > ```
> >
> > Here `[2 5 7]'` is a $3\times1$ column vector, so it can be appended as an additional column to a $3\times3$ matrix `B`.
>
> > [!abstract]- Characteristic Polynomial
> > The characteristic polynomial of a matrix $A$ is:
> >
> > $$
> > p(\lambda)=\det(\lambda I-A)
> > $$
> >
> > Its roots are the eigenvalues of $A$.
> >
> > In MATLAB, **symbolic mathematics** can be used to obtain the characteristic polynomial.
> >
> > A typical modern syntax is:
> >
> > ```matlab
> > syms x
> > P = charpoly(sym(A),x);
> > ```
> >
> > `coeffs(P)` can then be used to obtain polynomial coefficients.
> >
> > This part requires the **Symbolic Math Toolbox**.
>
>---
>
> > [!warning]- Common Matrix Mistakes
> > - `*` and `.*` are not the same.
> >
> > - `^` and `.^` are not the same.
> >
> > - `A(1,2)` means row $1$, column $2$.
> >
> > - `A(:,2)` means the entire second column.
> >
> > - `A(1,:)` means the entire first row.
> >
> > - MATLAB indexing starts from $1$.
> >
> > - Matrix multiplication requires compatible dimensions.
> >
> > - `A` and `a` are different variables.
> >
> > - `inv(A)` exists only when $A$ is nonsingular.
> >
> > - Do not confuse `A\b` with `A/b`.
> >
> > - `eye(m,n)` creates an $m\times n$ identity-like matrix, not necessarily a square identity matrix.
>
> > [!important]- Exercise 3 — Concepts Required
> > Exercise 3 asks you to:
> >
> > ```matlab
> > A = [1 7 3; 4 0 6; 2 5 -1];
> > B = [1 7 3; 4 0 6; 2 5 -1];
> > ```
> >
> > and then compute a matrix product involving `A`, `B`, and `C`.
> >
> > Before solving it, you need to understand:
> >
> > - matrix initialization
> > - matrix multiplication `*`
> > - matrix dimensions
> > - determinant `det()`
> > - rank `rank()`
> > - inverse `inv()`
> > - eigenvalues `eig()`
> > - storing results in variables
> > - writing everything inside an `.m` script
>
> > [!tip]- Most Important MATLAB Matrix Rule
> > When working with matrices, always ask:
> >
> > **Do I want a mathematical matrix operation, or do I want to operate independently on each element?**
> >
> > Matrix operations:
> >
> > ```matlab
> > *
> > /
> > ^
> > ```
> >
> > Element-wise operations:
> >
> > ```matlab
> > .*
> > ./
> > .^
> > ```
>
> > [!important]- Quick Reference
> > ```matlab
> > A'              % Transpose
> > A * B           % Matrix multiplication
> > A .* B          % Element-wise multiplication
> > A^2             % Matrix square
> > A.^2            % Element-wise square
> >
> > A(1,2)          % Element at row 1, column 2
> > A(:,2)          % Entire column 2
> > A(1,:)          % Entire row 1
> >
> > A(2,:) = []     % Delete row 2
> > A(:,3) = []     % Delete column 3
> >
> > size(A)         % Dimensions
> > det(A)          % Determinant
> > rank(A)         % Rank
> > eig(A)          % Eigenvalues
> > inv(A)          % Inverse
> >
> > eye(4)          % 4x4 identity matrix
> > ones(3,4)       % 3x4 matrix of ones
> > zeros(4,3)      % 4x3 matrix of zeros
> > rand(5,4)       % 5x4 random matrix
> >
> > diag(d)         % Main diagonal
> > diag(d,1)       % Superdiagonal
> > diag(d,-1)      % Subdiagonal
> >
> > A\b             % Solve AX = b
> > A/b             % Matrix right division
> >```

---

> [!important]- MATLAB Plotting and Visualization
> > [!abstract]- Basic Idea of Plotting
> > MATLAB's `plot()` function is used to create a 2D graph.
> >
> > The basic syntax is:
> >
> > ```matlab
> > plot(x,y)
> > ```
> >
> > Here:
> > - `x` contains the x-coordinates
> > - `y` contains the corresponding y-coordinates
> >
> > MATLAB connects the points $(x_i,y_i)$ to produce the curve.
> >
> > Example:
> >
> > ```matlab
> > x = -pi:0.25:pi;
> > y = sin(x);
> > plot(x,y);
> > ```
> >
> > This plots:
> >
> > $$
> > y=\sin(x)
> > $$
> >
> > over the interval $[-\pi,\pi]$.
>
> > [!important]- Understanding the `x` Vector
> > ```matlab
> > x = -pi:0.25:pi;
> > ```
> >
> > creates:
> >
> > $$
> > -\pi,\;-\pi+0.25,\;-\pi+0.5,\ldots,\pi
> > $$
> >
> > The general form is:
> >
> > ```matlab
> > start:step:end
> > ```
> >
> > Here:
> > - start = `-pi`
> > - step = `0.25`
> > - end = `pi`
> >
> > MATLAB then evaluates the function at every value in `x`.
>
> > [!abstract]- Plotting a Function
> > ```matlab
> > x = -pi:0.25:pi;
> > y = sin(x);
> > plot(x,y);
> > ```
> >
> > The first line creates the x-values.
> >
> > The second line evaluates:
> >
> > $$
> > y_i=\sin(x_i)
> > $$
> >
> > for every element of `x`.
> >
> > The third line plots the corresponding $(x_i,y_i)$ pairs.
>
> > [!abstract]- `grid on`
> > ```matlab
> > grid on
> > ```
> >
> > displays grid lines on the graph.
> >
> > This makes it easier to read approximate coordinates and values.
> >
> > Turn it off using:
> >
> > ```matlab
> > grid off
> > ```
>
> > [!abstract]- `title()`
> > ```matlab
> > title('MY PLOT')
> > ```
> >
> > adds a title to the current figure.
> >
> > Text must be enclosed in quotes:
> >
> > ```matlab
> > title('My Plot')
> > ```
> >
> > Modern MATLAB also supports string syntax such as:
> >
> > ```matlab
> > title("My Plot")
> > ```
> >
> > but single quotes are commonly used in introductory MATLAB code.
>
> > [!important]- Plot Line Styles and Colors
> > MATLAB allows you to specify how a curve should look.
> >
> > A plot specification can contain:
> >
> > - color
> > - line style
> > - marker
> >
> > Common colors:
> >
> > ```text
> > 'r' → red
> > 'g' → green
> > 'b' → blue
> > 'k' → black
> > 'm' → magenta
> > 'c' → cyan
> > 'y' → yellow
> > ```
> >
> > Common line styles:
> >
> > ```text
> > '-'  → solid
> > '--' → dashed
> > ':'  → dotted
> > '-.' → dash-dot
> > ```
> >
> > Common markers:
> >
> > ```text
> > 'o' → circle
> > '*' → star
> > '+' → plus
> > 'x' → x-marker
> > ```
>
> > [!example]- Plot Specification Example
> > ```matlab
> > plot(x,y,'b-')
> > ```
> >
> > means:
> >
> > - blue curve
> > - solid line
> >
> > ```matlab
> > plot(x,y,'go')
> > ```
> >
> > means:
> >
> > - green markers
> > - circle markers
> >
> > You can combine multiple properties:
> >
> > ```matlab
> > plot(x,y,'r--o')
> > ```
> >
> > meaning:
> >
> > - red
> > - dashed
> > - circle markers
>
> > [!important]- Plotting Multiple Curves
> > MATLAB allows multiple curves to be plotted in a single `plot()` command.
> >
> > Example:
> >
> > ```matlab
> > plot(x,sin(x),'b-',x,cos(x),'r-')
> > ```
> >
> > This creates:
> >
> > $$
> > y=\sin(x)
> > $$
> >
> > and
> >
> > $$
> > y=\cos(x)
> > $$
> >
> > on the same figure.
> >
> > The general syntax is:
> >
> > ```matlab
> > plot(x1,y1,style1,x2,y2,style2,...)
> > ```
>
> > [!important]- `hold on` and `hold off`
> > By default, when you create a new plot, MATLAB can replace the existing plot in the current axes.
> >
> > `hold on` tells MATLAB:
> >
> > **Keep the current graph and add subsequent plots to it.**
> >
> > Example:
> >
> > ```matlab
> > plot(x,sin(x),'b-');
> > hold on;
> > plot(x,cos(x),'r-');
> > hold off;
> > ```
> >
> > Both curves remain on the same axes.
> >
> > `hold off` returns MATLAB to its normal behavior.
>
> > [!abstract]- `figure()`
> > The `figure()` command creates or activates a figure window.
> >
> > Example:
> >
> > ```matlab
> > figure(9)
> > ```
> >
> > selects figure window 9.
> >
> > Then:
> >
> > ```matlab
> > plot(x,sin(x))
> > ```
> >
> > draws the graph in that figure.
> >
> > You can use different figure numbers for independent plots:
> >
> > ```matlab
> > figure(1)
> > plot(x,sin(x))
> >
> > figure(2)
> > plot(x,cos(x))
> > ```
> >
> > The sine and cosine plots appear in different figure windows.
>
> > [!abstract]- Different Figures vs Same Figure
> > **Different windows:**
> >
> > ```matlab
> > figure(1)
> > plot(x,sin(x))
> >
> > figure(2)
> > plot(x,cos(x))
> > ```
> >
> > **Same window using one `plot()` command:**
> >
> > ```matlab
> > figure(3)
> > plot(x,sin(x),'b-',x,cos(x),'r-')
> > ```
> >
> > **Same window using `hold on`:**
> >
> > ```matlab
> > figure(3)
> > plot(x,sin(x),'b-');
> > hold on;
> > plot(x,cos(x),'r-');
> > hold off;
> > ```
>
> > [!important]- Vectorized Function Evaluation
> > Suppose:
> >
> > ```matlab
> > x = 0:0.1:1;
> > ```
> >
> > and we want:
> >
> > $$
> > y=e^{-x}\cos(6\pi x)
> > $$
> >
> > We can write:
> >
> > ```matlab
> > y = exp(-x).*cos(6*pi*x);
> > ```
> >
> > Here `exp(-x)` evaluates the exponential element-by-element.
> >
> > `cos(...)` also operates element-by-element.
> >
> > This is an important idea:
> >
> > **MATLAB's mathematical functions can operate on vectors, allowing us to evaluate an entire function at many x-values at once.**
>
> > [!warning]- Common Vectorization Mistake
> > If an operation is intended to be element-wise, use the dot operator.
> >
> > For example:
> >
> > ```matlab
> > y = x.^2;
> > ```
> >
> > not:
> >
> > ```matlab
> > y = x^2;
> > ```
> >
> > Similarly:
> >
> > ```matlab
> > y = x.*exp(-x);
> > ```
> >
> > is element-wise multiplication.
> >
> > This becomes especially important when plotting functions using a vector of x-values.
>
> > [!abstract]- Plotting on a Specified Interval
> > If a function is required over an interval:
> >
> > $$
> > a\le x\le b
> > $$
> >
> > first create the x-values:
> >
> > ```matlab
> > x = a:step:b;
> > ```
> >
> > or, if exactly $n$ points are required:
> >
> > ```matlab
> > x = linspace(a,b,n);
> > ```
> >
> > `linspace()` is often easier when the question specifies a **number of points** rather than a step size.
>
> > [!important]- `linspace`
> > General syntax:
> >
> > ```matlab
> > x = linspace(a,b,n);
> > ```
> >
> > creates exactly $n$ equally spaced points from $a$ to $b$, including both endpoints.
> >
> > Example:
> >
> > ```matlab
> > x = linspace(0,1,100);
> > ```
> >
> > creates exactly $100$ points between $0$ and $1$.
> >
> > This is particularly useful for Exercise 4 because it asks for **100 data points**.
> >
> > The equivalent spacing is:
> >
> > $$
> > \Delta x=\frac{b-a}{n-1}
> > $$
> >
> > but `linspace()` handles this automatically.
>
> > [!important]- Exercise 4 — First Function
> > The first function is:
> >
> > $$
> > f(x)=e^{-x}\cos(6\pi x)
> > $$
> >
> > for $100$ points over:
> >
> > $$
> > 0\le x\le1
> > $$
> >
> > A direct MATLAB implementation will therefore use:
> >
> > ```matlab
> > x = linspace(0,1,100);
> > f = exp(-x).*cos(6*pi*x);
> > ```
> >
> > and then:
> >
> > ```matlab
> > plot(x,f)
> > ```
> >
> > Notice the `.*` because the multiplication must be performed element-wise.
>
> > [!important]- The Three Curves in Exercise 4
> > The exercise involves:
> >
> > $$
> > f(x)=e^{-x}\cos(6\pi x)
> > $$
> >
> > and:
> >
> > $$
> > g(x)=e^{-x}
> > $$
> >
> > and:
> >
> > $$
> > h(x)=-e^{-x}
> > $$
> >
> > In MATLAB:
> >
> > ```matlab
> > f = exp(-x).*cos(6*pi*x);
> > g = exp(-x);
> > h = -exp(-x);
> > ```
>
> > [!important]- Why the First Curve Lies Between the Other Two
> > The key mathematical fact is:
> >
> > $$
> > -1\le\cos(6\pi x)\le1
> > $$
> >
> > Since:
> >
> > $$
> > e^{-x}>0
> > $$
> >
> > multiplying the inequality by $e^{-x}$ gives:
> >
> > $$
> > -e^{-x}\le
> > e^{-x}\cos(6\pi x)
> > \le e^{-x}
> > $$
> >
> > Therefore:
> >
> > $$
> > \boxed{-e^{-x}\le f(x)\le e^{-x}}
> > $$
> >
> > So the oscillating curve is bounded by the upper curve $e^{-x}$ and lower curve $-e^{-x}$.
>
> > [!abstract]- Finding Where Curves Meet
> > To determine where two curves meet, set them equal.
> >
> > For example, to find intersections of:
> >
> > $$
> > f(x)=e^{-x}\cos(6\pi x)
> > $$
> >
> > and:
> >
> > $$
> > g(x)=e^{-x}
> > $$
> >
> > solve:
> >
> > $$
> > e^{-x}\cos(6\pi x)=e^{-x}
> > $$
> >
> > Since $e^{-x}\neq0$:
> >
> > $$
> > \cos(6\pi x)=1
> > $$
> >
> > Similarly, intersections with:
> >
> > $$
> > -e^{-x}
> > $$
> >
> > satisfy:
> >
> > $$
> > \cos(6\pi x)=-1
> > $$
> >
> > This is a useful example of combining MATLAB computation with mathematical analysis.
>
> > [!tip]- Numerical Intersection Idea
> > There are several ways to find intersections computationally.
> >
> > For a simple problem like Exercise 4, the best approach is to first use the mathematical equation to determine the exact intersection points.
> >
> > MATLAB can then be used to verify the result numerically.
> >
> > For more complicated functions, numerical methods such as root finding can be used.
>
> > [!abstract]- Exporting a Figure as PDF
> > MATLAB figures can be exported for use in reports.
> >
> > From the figure window:
> >
> > ```text
> > File → Export To → PDF
> > ```
> >
> > This produces a PDF version of the graph.
> >
> > MATLAB also supports programmatic exporting in newer versions, for example:
> >
> > ```matlab
> > exportgraphics(gcf,'plot.pdf');
> > ```
> >
> > Here:
> >
> > - `gcf` means the current figure
> > - `'plot.pdf'` is the output filename
>
> > [!important]- `meshgrid`
> > `meshgrid()` is used to create a rectangular grid of $(x,y)$ coordinates for evaluating functions of two variables.
> >
> > Syntax:
> >
> > ```matlab
> > [x,y] = meshgrid(x_values,y_values);
> > ```
> >
> > Example:
> >
> > ```matlab
> > [x,y] = meshgrid(-3:0.2:3,-3:0.2:3);
> > ```
> >
> > This creates a grid of points covering:
> >
> > $$
> > -3\le x\le3
> > $$
> >
> > and:
> >
> > $$
> > -3\le y\le3
> > $$
> >
> > The matrices `x` and `y` contain the coordinates of every grid point.
>
> > [!important]- Function of Two Variables
> > Suppose:
> >
> > $$
> > z=f(x,y)
> > $$
> >
> > For the lab example:
> >
> > $$
> > z=(y-0.5)x e^{-x^2-y^2}
> > $$
> >
> > MATLAB:
> >
> > ```matlab
> > z = (y-0.5).*x.*exp(-x.^2-y.^2);
> > ```
> >
> > Notice the element-wise operators:
> >
> > ```matlab
> > .*
> > .^
> > ```
> >
> > because `x` and `y` are matrices containing many coordinate values.
>
> > [!important]- `surf`
> > ```matlab
> > surf(x,y,z)
> > ```
> >
> > creates a 3D surface plot.
> >
> > Conceptually, each grid point:
> >
> > $$
> > (x_{ij},y_{ij})
> > $$
> >
> > gets a corresponding height:
> >
> > $$
> > z_{ij}=f(x_{ij},y_{ij})
> > $$
> >
> > MATLAB then displays the surface:
> >
> > $$
> > z=f(x,y)
> > $$
>
> > [!important]- `contour`
> > ```matlab
> > contour(x(1,:),y(:,1),z,20)
> > ```
> >
> > creates a contour plot containing approximately $20$ contour levels.
> >
> > A contour line represents points where:
> >
> > $$
> > f(x,y)=c
> > $$
> >
> > for a constant $c$.
> >
> > Therefore, contour plots are analogous to topographic maps:
> >
> > - each line represents a constant function value
> > - different lines correspond to different values of $z$
>
> > [!abstract]- Understanding `x(1,:)` and `y(:,1)`
> > Given:
> >
> > ```matlab
> > [x,y] = meshgrid(-3:0.2:3,-3:0.2:3);
> > ```
> >
> > `x` and `y` are matrices.
> >
> > ```matlab
> > x(1,:)
> > ```
> >
> > means:
> >
> > - first row of `x`
> > - all columns
> >
> > ```matlab
> > y(:,1)
> > ```
> >
> > means:
> >
> > - all rows of `y`
> > - first column
> >
> > These provide the coordinate vectors needed by `contour()`.
>
> > [!warning]- Common Plotting Mistakes
> > - Using `x^2` instead of `x.^2` when `x` is a vector.
> >
> > - Using `x*y` instead of `x.*y` when multiplying corresponding elements.
> >
> > - Forgetting that trigonometric functions use radians.
> >
> > - Giving `plot()` x and y vectors with incompatible lengths.
> >
> > - Forgetting `hold on` when adding separate curves sequentially.
> >
> > - Accidentally replacing an existing graph by plotting again without `hold on`.
> >
> > - Forgetting to use `linspace(a,b,n)` when the question specifies an exact number of points.
> >
> > - Confusing `figure()` with `hold on`: `figure()` changes the figure window, while `hold on` allows multiple plots on the same axes.
> >
> > - Using matrix operators instead of element-wise operators when evaluating functions over a grid.
>
> > [!important]- Core Plotting Syntax
> > ```matlab
> > x = linspace(a,b,n);
> > y = f(x);
> > plot(x,y);
> >
> > grid on;
> > grid off;
> >
> > title('My Plot');
> >
> > figure(1);
> >
> > hold on;
> > plot(x,y);
> > hold off;
> >
> > plot(x,y,'b-');
> > plot(x,y,'r--');
> > plot(x,y,'go');
> >
> > [x,y] = meshgrid(x_values,y_values);
> > z = f(x,y);
> >
> > surf(x,y,z);
> > contour(x,y,z,20);
> >
> > exportgraphics(gcf,'plot.pdf');
> > ```

> [!important]- MATLAB Functions in `.m` Files
> > [!abstract]- What Is a MATLAB Function?
> > A MATLAB function is a reusable block of code that:
> >
> > - accepts input values
> > - performs some computation
> > - optionally returns output values
> >
> > General structure:
> >
> > ```matlab
> > function [output1, output2] = functionName(input1, input2)
> >
> > % Function body
> >
> > end
> > ```
> >
> > Example:
> >
> > ```matlab
> > function [f] = fact(n)
> >     f = prod(1:n);
> > end
> > ```
> >
> > Calling:
> >
> > ```matlab
> > fact(4)
> > ```
> >
> > returns:
> >
> > $$
> > 4!=24
> > $$
>
> > [!important]- Function File Name
> > A function is normally stored in a `.m` file.
> >
> > For:
> >
> > ```matlab
> > function [f] = fact(n)
> > ```
> >
> > the file should be:
> >
> > ```text
> > fact.m
> > ```
> >
> > The primary function name and the file name should normally match.
> >
> > This allows MATLAB to find the function when you type:
> >
> > ```matlab
> > fact(4)
> > ```
>
> > [!abstract]- Function Definition Line
> > The first line defines the function's interface.
> >
> > Example:
> >
> > ```matlab
> > function [f] = fact(n)
> > ```
> >
> > This tells MATLAB:
> >
> > - function name = `fact`
> > - input = `n`
> > - output = `f`
> >
> > Think of it as:
> >
> > $$
> > n\longrightarrow\boxed{\text{fact}}\longrightarrow f
> > $$
>
> > [!important]- Input Arguments
> > Input arguments are written inside parentheses.
> >
> > Example:
> >
> > ```matlab
> > function y = square(x)
> >     y = x^2;
> > end
> > ```
> >
> > The function has:
> >
> > - one input: `x`
> > - one output: `y`
> >
> > Call it using:
> >
> > ```matlab
> > square(5)
> > ```
> >
> > giving:
> >
> > $$
> > 25
> > $$
>
> > [!abstract]- Multiple Input Arguments
> > Multiple inputs are separated by commas.
> >
> > ```matlab
> > function y = addNumbers(a,b)
> >     y = a+b;
> > end
> > ```
> >
> > Call:
> >
> > ```matlab
> > addNumbers(3,5)
> > ```
> >
> > Multiple inputs can also be used for more complicated functions:
> >
> > ```matlab
> > function [r1,r2] = secroot(a,b,c)
> > ```
> >
> > Here there are three inputs:
> >
> > $$
> > a,\quad b,\quad c
> > $$
>
> > [!important]- Multiple Output Arguments
> > If a function returns multiple outputs, put them inside square brackets.
> >
> > Example:
> >
> > ```matlab
> > function [sumValue,prodValue] = calculate(a,b)
> >     sumValue = a+b;
> >     prodValue = a*b;
> > end
> > ```
> >
> > Call:
> >
> > ```matlab
> > [s,p] = calculate(3,4);
> > ```
> >
> > Then:
> >
> > ```text
> > s = 7
> > p = 12
> > ```
> >
> > The order matters:
> >
> > ```matlab
> > [s,p] = calculate(...)
> > ```
> >
> > receives the first output in `s` and the second output in `p`.
>
> > [!abstract]- Function with No Output
> > A function does not have to return a value.
> >
> > Example:
> >
> > ```matlab
> > function printresults(x)
> >     disp(x);
> > end
> > ```
> >
> > It can be called as:
> >
> > ```matlab
> > printresults(10)
> > ```
> >
> > An empty output list is also possible:
> >
> > ```matlab
> > function [] = printresults(x)
> >     disp(x);
> > end
> > ```
> >
> > In practice, simply omitting the output variable is cleaner.
>
> > [!abstract]- Function Body
> > The function body contains the actual computation.
> >
> > Example:
> >
> > ```matlab
> > function f = fact(n)
> >     f = prod(1:n);
> > end
> > ```
> >
> > The line:
> >
> > ```matlab
> > f = prod(1:n);
> > ```
> >
> > performs the computation and assigns the result to the output variable `f`.
>
> > [!important]- Local Function Variables
> > Variables inside a function are generally **local to that function**.
> >
> > Example:
> >
> > ```matlab
> > function y = square(x)
> >     temp = x^2;
> >     y = temp;
> > end
> > ```
> >
> > `temp` belongs to the function's workspace.
> >
> > The function receives values through its inputs and returns values through its outputs.
> >
> > This is one reason functions are useful: they isolate computations from the rest of your program.
>
> > [!abstract]- Input Variable Names Do Not Have to Match
> > Suppose the function is:
> >
> > ```matlab
> > function y = square(x)
> >     y = x^2;
> > end
> > ```
> >
> > You can call:
> >
> > ```matlab
> > a = 5;
> > square(a)
> > ```
> >
> > The variable outside the function is called `a`, while the function receives it as `x`.
> >
> > MATLAB passes the value into the function.
> >
> > Therefore, the names do not need to match.
>
> > [!important]- The `if` Statement
> > MATLAB uses `if` for conditional execution.
> >
> > Basic structure:
> >
> > ```matlab
> > if condition
> >     statements
> > end
> > ```
> >
> > Example:
> >
> > ```matlab
> > if x > 0
> >     disp('Positive');
> > end
> > ```
> >
> > The statements execute only if the condition is true.
>
> > [!important]- `if / elseif / else`
> > When there are multiple possible cases:
> >
> > ```matlab
> > if condition1
> >     statements1
> > elseif condition2
> >     statements2
> > else
> >     statements3
> > end
> > ```
> >
> > MATLAB checks the conditions from top to bottom.
> >
> > Once one condition is true, its block executes and the remaining conditions are skipped.
>
> > [!abstract]- Comparison Operators
> > Common MATLAB comparison operators:
> >
> > | Meaning | MATLAB |
> > |---|---|
> > | Equal | `==` |
> > | Not equal | `~=` |
> > | Greater than | `>` |
> > | Less than | `<` |
> > | Greater/equal | `>=` |
> > | Less/equal | `<=` |
> >
> > Important:
> >
> > ```matlab
> > ==
> > ```
> >
> > means **comparison**.
> >
> > ```matlab
> > =
> > ```
> >
> > means **assignment**.
> >
> > Example:
> >
> > ```matlab
> > x = 5;
> > ```
> >
> > assigns $5$ to `x`.
> >
> > ```matlab
> > x == 5
> > ```
> >
> > checks whether `x` equals $5$.
>
> > [!warning]- Common Mistake: `=` vs `==`
> > Wrong:
> >
> > ```matlab
> > if Det = 0
> > ```
> >
> > Correct:
> >
> > ```matlab
> > if Det == 0
> > ```
> >
> > `=` assigns a value.
> >
> > `==` compares two values.
>
> > [!important]- Example: Quadratic Equation
> > Consider:
> >
> > $$
> > ax^2+bx+c=0
> > $$
> >
> > The discriminant is:
> >
> > $$
> > \Delta=b^2-4ac
> > $$
> >
> > Its value determines the type of roots:
> >
> > $$
> > \Delta<0
> > $$
> >
> > → complex conjugate roots
> >
> > $$
> > \Delta=0
> > $$
> >
> > → repeated real root
> >
> > $$
> > \Delta>0
> > $$
> >
> > → two distinct real roots
> >
> > The quadratic formula is:
> >
> > $$
> > x=\frac{-b\pm\sqrt{\Delta}}{2a}
> > $$
>
> > [!important]- `secroot` Function
> > The lab's function implements the quadratic formula:
> >
> > ```matlab
> > function [r1,r2] = secroot(a,b,c)
> >
> >     Det = b^2 - 4*a*c;
> >
> >     if Det < 0
> >         r1 = (-b + 1i*sqrt(-Det))/(2*a);
> >         r2 = (-b - 1i*sqrt(-Det))/(2*a);
> >         disp('The two roots are complex conjugates');
> >
> >     elseif Det == 0
> >         r1 = -b/(2*a);
> >         r2 = -b/(2*a);
> >         disp('There are two repeated roots');
> >
> >     else
> >         r1 = (-b + sqrt(Det))/(2*a);
> >         r2 = (-b - sqrt(Det))/(2*a);
> >         disp('The two roots are real');
> >     end
> >
> > end
> > ```
> >
> > The structure is:
> >
> > ```text
> > Input coefficients
> >        ↓
> > Calculate discriminant
> >        ↓
> > ┌───────────────┐
> > │ Determine sign│
> > └───────────────┘
> >    ↓      ↓      ↓
> >   <0     =0     >0
> >    ↓      ↓      ↓
> > complex repeated real
> >    ↓      ↓      ↓
> >     Calculate roots
> >        ↓
> >      Output
> > ```
>
> > [!abstract]- Complex Numbers in MATLAB
> > MATLAB uses `i` or `j` for the imaginary unit:
> >
> > $$
> > i=\sqrt{-1}
> > $$
> >
> > Example:
> >
> > ```matlab
> > z = 3 + 4i;
> > ```
> >
> > gives the complex number:
> >
> > $$
> > 3+4i
> > $$
> >
> > For a negative discriminant:
> >
> > ```matlab
> > sqrt(-Det)
> > ```
> >
> > would normally involve a complex result.
> >
> > The lab explicitly constructs it as:
> >
> > ```matlab
> > 1i*sqrt(-Det)
> > ```
> >
> > which makes the imaginary component explicit.
>
> > [!warning]- Use `1i` for Safer Complex Arithmetic
> > MATLAB normally defines `i` as $\sqrt{-1}$.
> >
> > However, `i` can be overwritten:
> >
> > ```matlab
> > i = 10;
> > ```
> >
> > After that, `i` no longer represents the imaginary unit.
> >
> > A safer form is:
> >
> > ```matlab
> > 1i
> > ```
> >
> > Therefore:
> >
> > ```matlab
> > 1i*sqrt(-Det)
> > ```
> >
> > is more robust than:
> >
> > ```matlab
> > i*sqrt(-Det)
> > ```
>
> > [!abstract]- `disp()`
> > `disp()` displays text or values in the Command Window.
> >
> > Example:
> >
> > ```matlab
> > disp('The roots are real');
> > ```
> >
> > displays the message.
> >
> > It is useful when a function should tell the user what case occurred.
>
> > [!abstract]- Calling a Function
> > Suppose `secroot.m` contains:
> >
> > ```matlab
> > function [r1,r2] = secroot(a,b,c)
> >     ...
> > end
> > ```
> >
> > Then call it using:
> >
> > ```matlab
> > [r1,r2] = secroot(1,0,-1);
> > ```
> >
> > This corresponds to:
> >
> > $$
> > x^2-1=0
> > $$
> >
> > The three input arguments are:
> >
> > $$
> > a=1,\quad b=0,\quad c=-1
> > $$
> >
> > and the two returned values are stored in `r1` and `r2`.
>
> > [!important]- Function Outputs Can Be Ignored
> > If you only want one output:
> >
> > ```matlab
> > r1 = secroot(1,0,-1);
> > ```
> >
> > MATLAB returns the first output.
> >
> > If you want both:
> >
> > ```matlab
> > [r1,r2] = secroot(1,0,-1);
> > ```
> >
> > use square brackets.
>
> > [!abstract]- MatrixSwap: Problem Structure
> > Exercise 5B asks for a function that:
> >
> > - accepts an $n\times n$ matrix
> > - accepts two row indices `a` and `b`
> > - swaps those two rows
> > - returns the modified matrix
> >
> > The conceptual structure is:
> >
> > ```text
> > Input matrix A
> >       +
> >   row indices a,b
> >       ↓
> > Save row a temporarily
> >       ↓
> > Copy row b into row a
> >       ↓
> > Copy saved row into row b
> >       ↓
> > Return modified matrix
> > ```
>
> > [!important]- Temporary Variable for Swapping
> > To swap two values safely, use a temporary variable.
> >
> > General idea:
> >
> > ```matlab
> > temp = A(a,:);
> > A(a,:) = A(b,:);
> > A(b,:) = temp;
> > ```
> >
> > Why is `temp` necessary?
> >
> > Suppose:
> >
> > ```text
> > A(a,:) = [1 2 3]
> > A(b,:) = [4 5 6]
> > ```
> >
> > If you immediately write:
> >
> > ```matlab
> > A(a,:) = A(b,:);
> > A(b,:) = A(a,:);
> > ```
> >
> > the original row `A(a,:)` has already been overwritten.
> >
> > Both rows would become:
> >
> > ```text
> > [4 5 6]
> > ```
> >
> > The temporary variable preserves the original row.
>
> > [!abstract]- Selecting a Row for MatrixSwap
> > To access an entire row:
> >
> > ```matlab
> > A(a,:)
> > ```
> >
> > means:
> >
> > - row `a`
> > - all columns
> >
> > Therefore:
> >
> > ```matlab
> > temp = A(a,:);
> > ```
> >
> > stores the entire row `a`.
>
> > [!important]- Valid Row Indices
> > The problem specifies:
> >
> > $$
> > 1\le a,b\le n
> > $$
> >
> > Since MATLAB uses 1-based indexing, valid rows of an $n\times n$ matrix are:
> >
> > ```text
> > 1, 2, ..., n
> > ```
> >
> > If `a` or `b` is outside this range, MATLAB will generate an indexing error.
>
> > [!warning]- Common Function Errors
> > - Function file name does not match the primary function name.
> >
> > - Forgetting the `end` statement.
> >
> > - Forgetting to assign values to output variables.
> >
> > - Using `=` instead of `==` inside conditions.
> >
> > - Forgetting commas between function arguments.
> >
> > - Forgetting square brackets when receiving multiple outputs:
> >   ```matlab
> >   [r1,r2] = secroot(a,b,c);
> >   ```
> >
> > - Accidentally overwriting `i` and then using it as the imaginary unit.
> >
> > - Overwriting a row before storing it in a temporary variable during swapping.
> >
> > - Calling a function from a directory that MATLAB cannot find.
>
> > [!tip]- Function vs Script
> > A **script** is mainly a sequence of commands:
> >
> > ```matlab
> > x = 1:10;
> > y = x.^2;
> > plot(x,y);
> > ```
> >
> > A **function** has a defined interface:
> >
> > ```matlab
> > function y = square(x)
> >     y = x.^2;
> > end
> > ```
> >
> > The important difference is:
> >
> > **Script → execute a sequence of commands**
> >
> > **Function → reusable computation with inputs and outputs**
>
> > [!important]- Core Function Syntax
> > ```matlab
> > function output = functionName(input)
> >     % Function body
> >     output = ...;
> > end
> > ```
> >
> > Multiple inputs:
> >
> > ```matlab
> > function output = functionName(input1,input2)
> > ```
> >
> > Multiple outputs:
> >
> > ```matlab
> > function [output1,output2] = functionName(input1,input2)
> > ```
> >
> > Conditional logic:
> >
> > ```matlab
> > if condition
> >     ...
> > elseif condition
> >     ...
> > else
> >     ...
> > end
> > ```
> >
> > Display:
> >
> > ```matlab
> > disp('message')
> > ```
> >
> > Complex number:
> >
> > ```matlab
> > z = a + 1i*b;
> > ```
> >
> > Row:
> >
> > ```matlab
> > A(a,:)
> > ```
> >
> > Swap:
> >
> > ```matlab
> > temp = A(a,:);
> > A(a,:) = A(b,:);
> > A(b,:) = temp;
> > ```

> [!important]- MATLAB Matrix Construction, Loops & Subplots
> > [!important]- Exercise 6: ArrowMatrix
> > The function must take an integer $n$ and return an:
> >
> > $$
> > (n+1)\times(n+1)
> > $$
> >
> > matrix.
> >
> > For $i=1,\ldots,n$:
> >
> > - element $(i,i)$ is $i$
> > - element $(n+1,i)$ is $2i$
> > - element $(i,n+1)$ is $2i$
> > - all other elements are $0$
> >
> > The bottom-right element $(n+1,n+1)$ is also specified separately.
> >
> > The important restriction is:
> >
> > **Do not use loops or `if` statements.**
> >
> > Therefore, the intended solution is based on MATLAB's matrix/vector operations such as:
> >
> > ```matlab
> > diag()
> > zeros()
> > ```
> >
> > and indexing/assignment.
>
> > [!abstract]- Understanding the Arrow Pattern
> > For example, suppose $n=4$.
> >
> > The output has size:
> >
> > $$
> > 5\times5
> > $$
> >
> > The main diagonal contains:
> >
> > $$
> > 1,\;2,\;3,\;4
> > $$
> >
> > The last row contains:
> >
> > $$
> > 2,\;4,\;6,\;8
> > $$
> >
> > in its first $4$ positions.
> >
> > The last column contains the same values.
> >
> > This produces an "arrow-like" structure:
> >
> > ```text
> > * 0 0 0 *
> > 0 * 0 0 *
> > 0 0 * 0 *
> > 0 0 0 * *
> > * * * * *
> > ```
> >
> > where the actual values depend on $i$.
>
> > [!important]- Vectorization
> > **Vectorization** means performing an operation on an entire vector or matrix rather than explicitly writing a loop.
> >
> > Instead of:
> >
> > ```matlab
> > for i = 1:n
> >     ...
> > end
> > ```
> >
> > MATLAB often allows:
> >
> > ```matlab
> > i = 1:n;
> > ```
> >
> > followed by an operation on the entire vector.
> >
> > For example:
> >
> > ```matlab
> > i = 1:n;
> > 2*i
> > ```
> >
> > produces:
> >
> > $$
> > [2,4,6,\ldots,2n]
> > $$
> >
> > This is exactly the type of thinking Exercise 6 is testing.
>
> > [!abstract]- Creating the Required Diagonal
> > ```matlab
> > d = 1:n;
> > A = diag(d);
> > ```
> >
> > creates an $n\times n$ matrix whose main diagonal is:
> >
> > $$
> > 1,2,\ldots,n
> > $$
> >
> > For example, if:
> >
> > ```matlab
> > d = 1:4;
> > ```
> >
> > then:
> >
> > ```matlab
> > diag(d)
> > ```
> >
> > gives:
> >
> > $$
> > \begin{bmatrix}
> > 1&0&0&0\\
> > 0&2&0&0\\
> > 0&0&3&0\\
> > 0&0&0&4
> > \end{bmatrix}
> > $$
>
> > [!important]- Creating a Larger Zero Matrix
> > ```matlab
> > A = zeros(n+1,n+1);
> > ```
> >
> > creates the required output size:
> >
> > $$
> > (n+1)\times(n+1)
> > $$
> >
> > Initially every element is zero.
> >
> > We can then place the required values into specific locations.
>
> > [!abstract]- Assigning a Vector to a Row
> > Suppose:
> >
> > ```matlab
> > v = 2*(1:n);
> > ```
> >
> > Then:
> >
> > ```text
> > v = [2 4 6 ... 2n]
> > ```
> >
> > We can place it into the first $n$ elements of the last row:
> >
> > ```matlab
> > A(n+1,1:n) = v;
> > ```
> >
> > The notation:
> >
> > ```matlab
> > A(n+1,1:n)
> > ```
> >
> > means:
> >
> > - row $n+1$
> > - columns $1$ through $n$
>
> > [!abstract]- Assigning a Vector to a Column
> > Similarly:
> >
> > ```matlab
> > A(1:n,n+1) = v';
> > ```
> >
> > places the values into the last column.
> >
> > The transpose `'` is necessary because:
> >
> > ```matlab
> > v
> > ```
> >
> > is a row vector:
> >
> > $1\times n$
> >
> > while:
> >
> > ```matlab
> > v'
> > ```
> >
> > is a column vector:
> >
> > $n\times1$
> >
> > and the selected matrix portion is also $n\times1$.
>
> > [!important]- Indexing a Range
> > MATLAB allows ranges inside matrix indexing.
> >
> > ```matlab
> > 1:n
> > ```
> >
> > means:
> >
> > ```text
> > 1, 2, 3, ..., n
> > ```
> >
> > Therefore:
> >
> > ```matlab
> > A(1:n,n+1)
> > ```
> >
> > selects the first $n$ rows of the last column.
> >
> > And:
> >
> > ```matlab
> > A(n+1,1:n)
> > ```
> >
> > selects the first $n$ columns of the last row.
>
> > [!important]- Why No Loop Is Needed
> > The exercise explicitly prohibits loops.
> >
> > Instead of:
> >
> > ```matlab
> > for i = 1:n
> >     A(i,i) = i;
> > end
> > ```
> >
> > use:
> >
> > ```matlab
> > A(1:n+1,1:n+1) = ...
> > ```
> >
> > or more appropriately construct the diagonal using:
> >
> > ```matlab
> > diag(...)
> > ```
> >
> > The general lesson is:
> >
> > **When MATLAB can perform an operation on an entire vector/matrix, prefer that over manually looping through elements.**
>
> > [!important]- `for` Loop
> > MATLAB's `for` loop repeats a block of code for each value in a sequence.
> >
> > General syntax:
> >
> > ```matlab
> > for variable = values
> >     statements
> > end
> > ```
> >
> > Example:
> >
> > ```matlab
> > for i = 1:5
> >     i*i
> > end
> > ```
> >
> > The loop executes for:
> >
> > $$
> > i=1,2,3,4,5
> > $$
> >
> > and displays:
> >
> > $$
> > 1,\;4,\;9,\;16,\;25
> > $$
>
> > [!abstract]- Storing Loop Results
> > Instead of merely displaying results:
> >
> > ```matlab
> > for i = 1:5
> >     i*i
> > end
> > ```
> >
> > we can store them:
> >
> > ```matlab
> > a = zeros(1,5);
> >
> > for i = 1:5
> >     a(i) = i*i;
> > end
> > ```
> >
> > This produces:
> >
> > ```text
> > a =
> >      1     4     9    16    25
> > ```
> >
> > The expression:
> >
> > ```matlab
> > a(i)
> > ```
> >
> > accesses the $i$-th element.
>
> > [!important]- Preallocation
> > The command:
> >
> > ```matlab
> > a = zeros(5);
> > ```
> >
> > creates storage before the loop runs.
> >
> > This is called **preallocation**.
> >
> > It is good MATLAB practice because MATLAB does not have to repeatedly resize the array as the loop executes.
> >
> > For a vector of $5$ elements, it is often clearer to use:
> >
> > ```matlab
> > a = zeros(1,5);
> > ```
> >
> > rather than:
> >
> > ```matlab
> > a = zeros(5);
> > ```
> >
> > because `zeros(5)` creates a $5\times5$ matrix.
>
> > [!important]- `for` Loop with a Decreasing Sequence
> > MATLAB sequences can have a negative step.
> >
> > ```matlab
> > for i = 20:-2:2
> >     i*i
> > end
> > ```
> >
> > The values are:
> >
> > $$
> > 20,18,16,14,12,10,8,6,4,2
> > $$
> >
> > Therefore the loop processes the numbers in reverse order.
>
> > [!abstract]- General `for` Loop Pattern
> > ```matlab
> > for i = start:step:end
> >     % statements
> > end
> > ```
> >
> > Examples:
> >
> > ```matlab
> > for i = 1:10
> > ```
> >
> > ```matlab
> > for i = 2:2:20
> > ```
> >
> > ```matlab
> > for i = 20:-2:2
> > ```
>
> > [!important]- `while` Loop
> > A `while` loop repeats as long as a condition is true.
> >
> > General syntax:
> >
> > ```matlab
> > while condition
> >     statements
> > end
> > ```
> >
> > Example:
> >
> > ```matlab
> > i = 1;
> >
> > while i <= 5
> >     disp(i);
> >     i = i + 1;
> > end
> > ```
> >
> > The loop continues while:
> >
> > $$
> > i\le5
> > $$
>
> > [!warning]- Common `while` Loop Mistake
> > Always make sure the condition can eventually become false.
> >
> > For example:
> >
> > ```matlab
> > i = 1;
> > while i <= 5
> >     disp(i);
> > end
> > ```
> >
> > is an infinite loop because `i` never changes.
> >
> > Correct:
> >
> > ```matlab
> > i = 1;
> > while i <= 5
> >     disp(i);
> >     i = i + 1;
> > end
> > ```
>
> > [!abstract]- `subplot`
> > `subplot()` divides one figure window into multiple smaller plotting areas.
> >
> > Syntax:
> >
> > ```matlab
> > subplot(m,n,i)
> > ```
> >
> > where:
> >
> > - `m` = number of rows
> > - `n` = number of columns
> > - `i` = which subplot to activate
> >
> > Example:
> >
> > ```matlab
> > subplot(2,2,1)
> > ```
> >
> > divides the figure into:
> >
> > $$
> > 2\times2=4
> > $$
> >
> > plotting regions and selects the first one.
>
> > [!abstract]- Subplot Numbering
> > For:
> >
> > ```matlab
> > subplot(2,2,i)
> > ```
> >
> > the layout is:
> >
> > ```text
> > +---------+---------+
> > |    1    |    2    |
> > +---------+---------+
> > |    3    |    4    |
> > +---------+---------+
> > ```
> >
> > Therefore:
> >
> > ```matlab
> > subplot(2,2,1)
> > ```
> >
> > selects the upper-left plot.
> >
> > ```matlab
> > subplot(2,2,4)
> > ```
> >
> > selects the lower-right plot.
>
> > [!important]- Example of Multiple Subplots
> > ```matlab
> > t = 0:pi/20:2*pi;
> >
> > subplot(2,2,1)
> > plot(sin(t),cos(t))
> >
> > subplot(2,2,2)
> > z = sin(t);
> > plot(t,z)
> >
> > subplot(2,2,3)
> > z = sin(t).*cos(t);
> > plot(t,z)
> >
> > subplot(2,2,4)
> > z = sin(t).^2-cos(t).^2;
> > plot(t,z)
> > ```
> >
> > Each `subplot()` selects a different region of the same figure.
>
> > [!abstract]- `axis`
> > The `axis()` command controls the visible plotting limits.
> >
> > Example:
> >
> > ```matlab
> > axis([0,2*pi,-2,2])
> > ```
> >
> > means:
> >
> > $$
> > 0\le x\le2\pi
> > $$
> >
> > and:
> >
> > $$
> > -2\le y\le2
> > $$
> >
> > The general syntax is:
> >
> > ```matlab
> > axis([xmin xmax ymin ymax])
> > ```
>
> > [!warning]- Important Difference: `zeros(5)` vs `zeros(1,5)`
> > ```matlab
> > zeros(5)
> > ```
> >
> > creates:
> >
> > $$
> > 5\times5
> > $$
> >
> > while:
> >
> > ```matlab
> > zeros(1,5)
> > ```
> >
> > creates:
> >
> > $$
> > 1\times5
> > $$
> >
> > This matters when preallocating arrays.
>
> > [!warning]- Common Loop Mistakes
> > - Forgetting `end`.
> >
> > - Creating an infinite `while` loop.
> >
> > - Forgetting to update the loop variable in a `while` loop.
> >
> > - Using the wrong starting/ending value.
> >
> > - Using `zeros(n)` when a vector was intended.
> >
> > - Forgetting that MATLAB indexing starts from $1$.
> >
> > - Using a loop when vectorization can perform the operation directly.
>
> > [!tip]- Vectorization vs Loops
> > MATLAB supports both:
> >
> > ```matlab
> > for i = 1:n
> >     a(i) = i^2;
> > end
> > ```
> >
> > and vectorized code:
> >
> > ```matlab
> > i = 1:n;
> > a = i.^2;
> > ```
> >
> > The second approach is called **vectorization**.
> >
> > Exercise 6 specifically tests whether you can construct a matrix using vectorized operations rather than loops.
>
> > [!important]- Core Syntax
> > ```matlab
> > % For loop
> > for i = 1:n
> >     ...
> > end
> >
> > % While loop
> > while condition
> >     ...
> > end
> >
> > % Preallocate
> > A = zeros(m,n);
> >
> > % Subplot
> > subplot(m,n,i)
> >
> > % Set axis limits
> > axis([xmin xmax ymin ymax])
> >
> > % Vectorization
> > x = 1:n;
> > y = x.^2;
> > ```


