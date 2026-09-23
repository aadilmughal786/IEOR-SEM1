
> [!important]-  Statistics, Loops and Histograms - 1
> > [!abstract]- Exercise 1 Overview
> > Exercise 1 asks us to write:
> >
> > ```matlab
> > ex1fun(a)
> > ```
> >
> > where `a` is a column vector containing integers.
> >
> > The function must calculate:
> >
> > - number of elements
> > - minimum value
> > - maximum value
> > - frequency of every integer between minimum and maximum
> > - average
> > - standard deviation
> >
> > Importantly, the exercise says that MATLAB's built-in functions should **not** be used for these calculations, except `size()` for finding the size.
>
> > [!abstract]- `size()` for a Column Vector
> > Suppose:
> >
> > ```matlab
> > a = [4; 7; 2; 7; 5];
> > ```
> >
> > Since `a` is a column vector:
> >
> > ```matlab
> > size(a)
> > ```
> >
> > returns:
> >
> > ```text
> > 5     1
> > ```
> >
> > Therefore:
> >
> > ```matlab
> > [n,m] = size(a);
> > ```
> >
> > gives:
> >
> > - `n` = number of rows = number of elements
> > - `m` = number of columns
> >
> > Since the input is guaranteed to be a column vector:
> >
> > $$
> > m=1
> > $$
> >
> > and:
> >
> > $$
> > n=\text{number of elements}
> > $$
>
> > [!important]- Finding the Minimum Without `min()`
> > The exercise does not allow the built-in `min()` function.
> >
> > Therefore, we can find the minimum manually.
> >
> > Basic idea:
> >
> > ```matlab
> > minimum = a(1);
> >
> > for i = 2:n
> >     if a(i) < minimum
> >         minimum = a(i);
> >     end
> > end
> > ```
> >
> > Start by assuming the first element is the minimum.
> >
> > Then compare every remaining element against the current minimum.
> >
> > If a smaller value is found, update the minimum.
> >
> > Conceptually:
> >
> > $$
> > \text{current minimum}
> > \rightarrow
> > \text{compare next element}
> > \rightarrow
> > \text{update if necessary}
> > $$
>
> > [!important]- Finding the Maximum Without `max()`
> > The same idea works for the maximum.
> >
> > ```matlab
> > maximum = a(1);
> >
> > for i = 2:n
> >     if a(i) > maximum
> >         maximum = a(i);
> >     end
> > end
> > ```
> >
> > Start with:
> >
> > $$
> > \text{maximum}=a_1
> > $$
> >
> > and update whenever a larger value is encountered.
>
> > [!abstract]- Why Initialize With `a(1)`?
> > We should not arbitrarily initialize the minimum to `0`.
> >
> > Suppose:
> >
> > ```text
> > a = [-8; -4; -2]
> > ```
> >
> > If we incorrectly start with:
> >
> > ```matlab
> > minimum = 0;
> > ```
> >
> > then no element is less than $0$? Actually, `-8` is less than $0$, so this example would still update, but arbitrary initialization can create problems depending on the intended comparison.
> >
> > The robust approach is:
> >
> > ```matlab
> > minimum = a(1);
> > maximum = a(1);
> > ```
> >
> > This guarantees that the initial candidate is an actual element of the data.
>
> > [!important]- Counting Frequencies
> > This is the most important part of Exercise 1.
> >
> > Suppose:
> >
> > ```text
> > a = [2; 4; 2; 5; 4; 2]
> > ```
> >
> > Then:
> >
> > $$
> > \min(a)=2
> > $$
> >
> > and:
> >
> > $$
> > \max(a)=5
> > $$
> >
> > We want to determine how many times each value occurs:
> >
> > ```text
> > value   frequency
> >   2         3
> >   3         0
> >   4         2
> >   5         1
> > ```
> >
> > Notice that the value `3` must also be reported even though it does not appear in the vector.
>
> > [!important]- Frequency Counting Logic
> > Because the values are integers, we can examine every integer from the minimum to the maximum.
> >
> > ```matlab
> > for value = minimum:maximum
> >     count = 0;
> >
> >     for i = 1:n
> >         if a(i) == value
> >             count = count + 1;
> >         end
> >     end
> >
> >     disp(count);
> > end
> > ```
> >
> > The logic is:
> >
> > ```text
> > Choose a value
> >       ↓
> > Scan entire vector
> >       ↓
> > Compare each element with that value
> >       ↓
> > Increment count when equal
> >       ↓
> > Move to next value
> > ```
> >
> > This is the logic that Exercise 1(b) specifically asks you to explain in detail. 
>
> > [!abstract]- Nested Loops
> > Frequency counting naturally leads to a **nested loop**.
> >
> > Outer loop:
> >
> > ```matlab
> > for value = minimum:maximum
> > ```
> >
> > chooses which value we are counting.
> >
> > Inner loop:
> >
> > ```matlab
> > for i = 1:n
> > ```
> >
> > scans all elements of `a`.
> >
> > Therefore:
> >
> > ```text
> > Outer loop
> >     ↓
> > choose value
> >     ↓
> > Inner loop
> >     ↓
> > scan all elements
> >     ↓
> > count matches
> > ```
>
> > [!important]- Computing the Mean Manually
> > The mean of $n$ observations is:
> >
> > $$
> > \bar{x}=
> > \frac{1}{n}\sum_{i=1}^{n}x_i
> > $$
> >
> > Without using `mean()`:
> >
> > ```matlab
> > total = 0;
> >
> > for i = 1:n
> >     total = total + a(i);
> > end
> >
> > average = total/n;
> > ```
> >
> > The variable `total` acts as an accumulator.
>
> > [!abstract]- Accumulator Pattern
> > An accumulator repeatedly updates a variable.
> >
> > Example:
> >
> > ```matlab
> > total = 0;
> >
> > for i = 1:n
> >     total = total + a(i);
> > end
> > ```
> >
> > At each iteration:
> >
> > $$
> > \text{new total}
> > =
> > \text{old total}+a_i
> > $$
> >
> > After the loop:
> >
> > $$
> > \text{total}=\sum_{i=1}^{n}a_i
> > $$
> >
> > This pattern is extremely important in MATLAB programming.
>
> > [!important]- Standard Deviation
> > The standard deviation measures the spread of observations around their mean.
> >
> > For the population-style calculation:
> >
> > $$
> > \sigma=
> > \sqrt{
> > \frac{1}{n}
> > \sum_{i=1}^{n}(x_i-\bar{x})^2
> > }
> > $$
> >
> > For the sample standard deviation:
> >
> > $$
> > s=
> > \sqrt{
> > \frac{1}{n-1}
> > \sum_{i=1}^{n}(x_i-\bar{x})^2
> > }
> > $$
> >
> > MATLAB's `std()` has a convention that depends on its normalization argument/version, so when the assignment says to calculate standard deviation manually, we must use the convention specified by the course/instructor if one is given.
> >
> > The Lab 2 PDF does not specify which denominator should be used.
>
> > [!important]- Manual Standard Deviation Using a Loop
> > Once the average has been calculated:
> >
> > ```matlab
> > total = 0;
> >
> > for i = 1:n
> >     total = total + (a(i)-average)^2;
> > end
> >
> > variance = total/n;
> > standardDeviation = sqrt(variance);
> > ```
> >
> > The logic is:
> >
> > ```text
> > Calculate mean
> >      ↓
> > Find deviation from mean
> >      ↓
> > Square deviation
> >      ↓
> > Add all squared deviations
> >      ↓
> > Divide by n
> >      ↓
> > Take square root
> > ```
>
> > [!warning]- Common Standard Deviation Mistake
> > Do not calculate:
> >
> > ```matlab
> > sum(a(i)-average)
> > ```
> >
> > and then take the square root.
> >
> > The deviations must be **squared first**:
> >
> > $$
> > (a_i-\bar a)^2
> > $$
> >
> > Otherwise positive and negative deviations cancel each other.
>
> > [!abstract]- Frequency and Distribution
> > A frequency table tells us how often each value appears.
> >
> > Example:
> >
> > ```text
> > value    frequency
> > 1           3
> > 2           7
> > 3           9
> > 4           6
> > 5           2
> > ```
> >
> > This gives us information about the empirical distribution of the data.
> >
> > Exercise 1 asks you to use three supplied vectors and reason about whether one appears uniformly distributed and what distributions may describe the others.
>
> > [!important]- Histogram
> > A histogram groups numerical observations into intervals called bins and displays their frequencies.
> >
> > MATLAB's lab material specifically introduces:
> >
> > ```matlab
> > hist(a)
> > ```
> >
> > The exact appearance depends on the data and binning.
> >
> > A histogram helps us visually identify patterns such as:
> >
> > - approximately uniform
> > - concentrated around a center
> > - skewed
> > - exponential-like
> > - multimodal
>
> > [!abstract]- Uniform Distribution
> > A continuous uniform distribution on $[a,b]$ gives equal probability density throughout the interval:
> >
> > $$
> > f(x)=\frac{1}{b-a},
> > \qquad a\le x\le b
> > $$
> >
> > A histogram generated from a finite sample will not be perfectly flat.
> >
> > As the sample size increases, the histogram generally gives a clearer picture of the underlying distribution.
>
> > [!important]- Sample Size and Histograms
> > A small sample can produce a noisy-looking histogram even if the underlying distribution is uniform.
> >
> > A larger sample generally gives a more stable estimate of the distribution.
> >
> > Therefore:
> >
> > **Do not conclude that a random sample is non-uniform merely because its histogram is not perfectly flat.**
>
> > [!abstract]- Working With `.m` Data Files
> > The lab provides files such as:
> >
> > ```text
> > ex1a.m
> > ex1b.m
> > ex1c.m
> > ```
> >
> > When you type:
> >
> > ```matlab
> > ex1a
> > ```
> >
> > the commands in that file execute and create a variable called `a`.
> >
> > The same applies to:
> >
> > ```matlab
> > ex1b
> > ```
> >
> > and:
> >
> > ```matlab
> > ex1c
> > ```
> >
> > The lab warns that these files may be large and that loading the next file can overwrite the previous value of `a`.
>
> > [!warning]- Important Data-File Workflow
> > If you run:
> >
> > ```matlab
> > ex1a
> > ```
> >
> > and then:
> >
> > ```matlab
> > ex1b
> > ```
> >
> > both may use the variable name:
> >
> > ```matlab
> > a
> > ```
> >
> > Therefore, the second command can replace the first vector.
> >
> > Correct workflow:
> >
> > ```text
> > Run ex1a
> > ↓
> > Analyze a
> > ↓
> > Record results
> > ↓
> > Run ex1b
> > ↓
> > Analyze a
> > ↓
> > Record results
> > ```
>
> > [!important]- Lab 2 Programming Pattern
> > A large part of Exercise 1 can be understood using four programming patterns:
> >
> > **Traversal**
> >
> > ```matlab
> > for i = 1:n
> > ```
> >
> > visits every element.
> >
> > **Accumulator**
> >
> > ```matlab
> > total = total + a(i);
> > ```
> >
> > builds a sum.
> >
> > **Conditional update**
> >
> > ```matlab
> > if a(i) < minimum
> >     minimum = a(i);
> > end
> > ```
> >
> > updates a value when a condition is satisfied.
> >
> > **Nested traversal**
> >
> > ```matlab
> > for value = minimum:maximum
> >     for i = 1:n
> >         ...
> >     end
> > end
> > ```
> >
> > counts occurrences of each possible integer.
>
> > [!warning]- Exercise 1 Restrictions
> > The assignment specifically says not to use built-in MATLAB functions for the requested calculations, except `size()` for finding the size.
> >
> > Therefore, for Exercise 1 we should **not simply write**:
> >
> > ```matlab
> > min(a)
> > max(a)
> > mean(a)
> > std(a)
> > ```
> >
> > Instead, we should implement the calculations ourselves using loops and arithmetic.
>
> > [!tip]- Key Concepts to Master Before Exercise 1
> > ```text
> > size()
> >     ↓
> > number of elements
> >
> > for loop
> >     ↓
> > visit every element
> >
> > if condition
> >     ↓
> > update minimum/maximum
> >
> > nested for loops
> >     ↓
> > frequency counting
> >
> > accumulator
> >     ↓
> > sum and average
> >
> > deviations from mean
> >     ↓
> > standard deviation
> >
> > hist()
> >     ↓
> > visualize distribution
> > ```

> [!important]- Statistics, Loops and Histograms - 2
>
> > [!abstract]- For Loop
> > A `for` loop repeats a block of code a known number of times.
> >
> > ```matlab
> > for i = 1:n
> >     % statements
> > end
> > ```
> >
> > Example:
> >
> > ```matlab
> > for i = 1:5
> >     disp(i)
> > end
> > ```
> >
> > The loop variable `i` takes the values:
> >
> > $$1,2,3,\ldots,n$$
> >
> > In Lab 2, `for` loops are important because Exercises 1 and 2 require calculations using loops.
>
> > [!abstract]- Looping Through a Vector
> > Suppose:
> >
> > ```matlab
> > a = [4; 7; 2; 9; 5];
> > ```
> >
> > To process every element:
> >
> > ```matlab
> > n = size(a,1);
> >
> > for i = 1:n
> >     x = a(i);
> >     disp(x)
> > end
> > ```
> >
> > Here:
> >
> > - `i` is the position/index.
> > - `a(i)` is the value at that position.
> > - `n` is the number of elements.
> >
> > For a column vector, `a(i)` accesses the $i$-th element.
>
> > [!abstract]- Accumulator Pattern
> > Many calculations in programming use an **accumulator**.
> >
> > Example:
> >
> > ```matlab
> > total = 0;
> >
> > for i = 1:n
> >     total = total + a(i);
> > end
> > ```
> >
> > The accumulator repeatedly stores:
> >
> > $$\text{new total}=\text{old total}+\text{current value}$$
> >
> > This pattern is useful for calculating:
> >
> > - sums
> > - averages
> > - variance
> > - standard deviation
> > - frequencies/counts
>
> > [!warning]- Common Accumulator Mistake
> > Incorrect:
> >
> > ```matlab
> > for i = 1:n
> >     total = a(i);
> > end
> > ```
> >
> > This overwrites `total` on every iteration.
> >
> > Correct:
> >
> > ```matlab
> > total = 0;
> >
> > for i = 1:n
> >     total = total + a(i);
> > end
> > ```
> >
> > The important idea is:
> >
> > ```text
> > old value + new contribution
> > ```
>
> > [!abstract]- Finding the Minimum
> > Exercise 1 does not allow built-in MATLAB calculation functions except `size`. 
> >
> > Therefore, instead of:
> >
> > ```matlab
> > min(a)
> > ```
> >
> > we implement the logic manually.
> >
> > ```matlab
> > minimum = a(1);
> >
> > for i = 2:n
> >     if a(i) < minimum
> >         minimum = a(i);
> >     end
> > end
> > ```
> >
> > Start with the first element as the current minimum.
> >
> > Then compare every remaining element with it.
> >
> > If a smaller value is found, replace the current minimum.
>
> > [!abstract]- Finding the Maximum
> > The same idea works for the maximum.
> >
> > ```matlab
> > maximum = a(1);
> >
> > for i = 2:n
> >     if a(i) > maximum
> >         maximum = a(i);
> >     end
> > end
> > ```
> >
> > The logic is:
> >
> > ```text
> > Start with first value
> >        ↓
> > Compare next value
> >        ↓
> > Is it larger?
> >    ↓         ↓
> >   Yes        No
> >    ↓         ↓
> > Replace    Keep current
> > maximum    maximum
> > ```
>
> > [!abstract]- Frequency Counting
> > Exercise 1 asks for the number of times **each element between the maximum and minimum occurs**. 
> >
> > Suppose:
> >
> > ```text
> > a = [2; 4; 2; 5; 4; 2]
> > ```
> >
> > Then:
> >
> > ```text
> > Value     Frequency
> > 2         3
> > 3         0
> > 4         2
> > 5         1
> > ```
> >
> > The number of occurrences of a value is called its **frequency**.
>
> > [!abstract]- Nested Loops for Frequency Counting
> > To find the frequency of every value, we can use two loops.
> >
> > The outer loop chooses the value whose frequency we want.
> >
> > The inner loop searches through the entire vector.
> >
> > ```matlab
> > for x = minimum:maximum
> >     count = 0;
> >
> >     for i = 1:n
> >         if a(i) == x
> >             count = count + 1;
> >         end
> >     end
> >
> >     disp(count)
> > end
> > ```
> >
> > Conceptually:
> >
> > ```text
> > Choose a value x
> >       ↓
> > Search entire vector
> >       ↓
> > Count matching elements
> >       ↓
> > Display frequency
> >       ↓
> > Choose next x
> > ```
>
> > [!warning]- Resetting the Counter
> > The counter must be reset for every new value.
> >
> > Correct:
> >
> > ```matlab
> > for x = minimum:maximum
> >     count = 0;
> >
> >     for i = 1:n
> >         if a(i) == x
> >             count = count + 1;
> >         end
> >     end
> > end
> > ```
> >
> > If `count = 0` is placed before the outer loop, frequencies from different values will be incorrectly combined.
>
> > [!abstract]- Equality Operator
> > MATLAB uses:
> >
> > ```matlab
> > ==
> > ```
> >
> > to test equality.
> >
> > Example:
> >
> > ```matlab
> > if a(i) == x
> >     count = count + 1;
> > end
> > ```
> >
> > Do not confuse:
> >
> > ```matlab
> > =
> > ```
> >
> > with:
> >
> > ```matlab
> > ==
> > ```
> >
> > `=` means **assignment**.
> >
> > `==` means **comparison**.
>
> > [!abstract]- Mean / Average
> > The arithmetic mean of $n$ observations is:
> >
> > $$\bar{x}=\frac{1}{n}\sum_{i=1}^{n}x_i$$
> >
> > Without using MATLAB's `mean()`:
> >
> > ```matlab
> > total = 0;
> >
> > for i = 1:n
> >     total = total + a(i);
> > end
> >
> > average = total/n;
> > ```
> >
> > The calculation has two basic steps:
> >
> > $$\text{Sum all values} \rightarrow \text{divide by number of values}$$
>
> > [!abstract]- Standard Deviation
> > Standard deviation measures how spread out the observations are around their mean.
> >
> > First calculate the mean:
> >
> > $$\bar{x}=\frac{1}{n}\sum_{i=1}^{n}x_i$$
> >
> > Then calculate each deviation:
> >
> > $$x_i-\bar{x}$$
> >
> > Square it:
> >
> > $$(x_i-\bar{x})^2$$
> >
> > Then add all squared deviations:
> >
> > $$\sum_{i=1}^{n}(x_i-\bar{x})^2$$
> >
> > The PDF does not specify whether the denominator should be $n$ or $n-1$. We should therefore follow the convention expected by your course when implementing Exercise 1. 
>
> > [!abstract]- Standard Deviation in MATLAB
> > Once the mean has been calculated:
> >
> > ```matlab
> > sumsq = 0;
> >
> > for i = 1:n
> >     deviation = a(i) - average;
> >     sumsq = sumsq + deviation^2;
> > end
> > ```
> >
> > After this loop, `sumsq` contains:
> >
> > $$\sum_{i=1}^{n}(a_i-\bar{a})^2$$
> >
> > We then divide according to the required standard-deviation convention and take the square root.
>
> > [!abstract]- Why Square the Deviations?
> > If we simply add deviations:
> >
> > $$\sum_i(x_i-\bar{x})$$
> >
> > positive and negative deviations cancel.
> >
> > For example:
> >
> > $$-2+2=0$$
> >
> > Squaring prevents this cancellation:
> >
> > $$(-2)^2=4,\qquad 2^2=4$$
> >
> > Therefore, squared deviations provide a useful measure of spread.
>
> > [!abstract]- `disp` and `fprintf`
> > `disp()` displays values or text:
> >
> > ```matlab
> > disp(n)
> > disp('Hello')
> > ```
> >
> > `fprintf()` gives more control over formatting:
> >
> > ```matlab
> > fprintf('Number of elements = %d\n', n)
> > ```
> >
> > `%d` is commonly used for integers.
> >
> > `\n` starts a new line.
>
> > [!abstract]- Histogram
> > A histogram groups numerical observations into intervals called **bins** and shows how frequently observations fall into those intervals.
> >
> > Basic MATLAB syntax:
> >
> > ```matlab
> > histogram(a)
> > ```
> >
> > For example:
> >
> > ```matlab
> > a = rand(1000,1);
> > histogram(a)
> > ```
> >
> > A histogram helps us visually understand the distribution of the observed data.
> >
> > Exercise 2 specifically asks you to use `hist()` to comment on the distribution of `b`. 
>
> > [!abstract]- Histogram vs Distribution
> > A **distribution** is the underlying mathematical description of how values occur.
> >
> > A **histogram** is a visualization of observed data.
> >
> > Therefore:
> >
> > ```text
> > Distribution
> >      ↓
> > generates observations
> >      ↓
> > observed data
> >      ↓
> > histogram
> > ```
> >
> > A histogram gives us evidence about the distribution, but the histogram itself is not the probability distribution.
>
> > [!abstract]- Uniform Distribution
> > A continuous random variable is uniformly distributed over an interval when its probability density is constant throughout that interval.
> >
> > It is written as:
> >
> > $$X\sim U(a,b)$$
> >
> > For example:
> >
> > $$X\sim U(20,40)$$
> >
> > means the values lie between $20$ and $40$ with constant density.
> >
> > Exercise 4 states that both demand and supply are uniformly distributed between $20$ and $40$ and are independent.
>
> > [!abstract]- Recognizing a Uniform Histogram
> > For a sufficiently large sample from a uniform distribution, the histogram should be approximately flat across the interval.
> >
> > A small sample can look irregular:
> >
> > ```text
> > Small sample
> > → more random-looking fluctuations
> > ```
> >
> > A large sample generally gives:
> >
> > ```text
> > Large sample
> > → smoother / flatter histogram
> > ```
> >
> > It will generally not be perfectly flat because the observations are random.
>
> > [!abstract]- Effect of Sample Size
> > Consider:
> >
> > ```matlab
> > rand(10,1)
> > ```
> >
> > versus:
> >
> > ```matlab
> > rand(1000000,1)
> > ```
> >
> > The first contains only $10$ observations, while the second contains $1,000,000$ observations.
> >
> > Therefore, the second histogram generally gives a much clearer picture of the underlying distribution.
> >
> > Exercise 5 specifically asks you to compare $n=10$, $1000$, and $1,000,000$.
>
> > [!abstract]- Loading the Exercise Data
> > Exercise 1 provides files such as:
> >
> > ```text
> > ex1a.m
> > ex1b.m
> > ex1c.m
> > ```
> >
> > Running:
> >
> > ```matlab
> > ex1a
> > ```
> >
> > creates a variable `a`.
> >
> > Then:
> >
> > ```matlab
> > ex1fun(a)
> > ```
> >
> > runs your function on that data.
> >
> > The lab warns that loading the next dataset can overwrite `a`, so analyze one dataset before loading another.
>
> > [!important]- Core Programming Patterns
> > The main patterns used throughout Lab 2 are:
> >
> > **Traversal**
> >
> > ```matlab
> > for i = 1:n
> >     % process a(i)
> > end
> > ```
> >
> > **Accumulator**
> >
> > ```matlab
> > total = total + a(i);
> > ```
> >
> > **Conditional update**
> >
> > ```matlab
> > if a(i) < minimum
> >     minimum = a(i);
> > end
> > ```
> >
> > **Frequency counting**
> >
> > ```matlab
> > if a(i) == x
> >     count = count + 1;
> > end
> > ```
> >
> > **Nested traversal**
> >
> > ```matlab
> > for x = minimum:maximum
> >     for i = 1:n
> >         % process a(i)
> >     end
> > end
> > ```
> >
> > Exercise 1 is essentially a combination of these programming patterns.
>
> > [!important]- Exercise 1 — Required Skills
> > According to the lab, `ex1fun(a)` must display:
> >
> > - number of elements
> > - minimum
> > - maximum
> > - frequency of every integer from minimum to maximum
> > - average
> > - standard deviation
> >
> > Built-in MATLAB functions cannot be used for the calculations, except `size`. 
> >
> > So before solving Exercise 1, you should understand:
> >
> > ```text
> > size()
> > indexing
> > for loop
> > nested for loop
> > if
> > ==
> > accumulator
> > conditional update
> > frequency counting
> > mean
> > standard deviation
> > display/output
> > ```

> [!important]- MATLAB Lab 2 — Block Averaging and Data Reduction
>
> > [!abstract]- Block Averaging
> > Block averaging means dividing a vector into consecutive groups, where each group contains $m$ elements, and replacing each group by its average.
> >
> > Suppose:
> >
> > ```matlab
> > a = [2; 4; 6; 8; 10; 12];
> > ```
> >
> > and:
> >
> > ```matlab
> > m = 2;
> > ```
> >
> > Divide the data into blocks:
> >
> > ```text
> > [2,  4]   → average = 3
> > [6,  8]   → average = 7
> > [10, 12]  → average = 11
> > ```
> >
> > Therefore:
> >
> > ```text
> > b = [3; 7; 11]
> > ```
> >
> > Mathematically, if a block contains
> >
> > $$a_i,a_{i+1},\ldots,a_{i+m-1}$$
> >
> > its average is
> >
> > $$b_j=\frac{1}{m}\sum_{k=1}^{m}a_{(j-1)m+k}$$
>
> > [!abstract]- Why Block Averaging Is Used
> > Block averaging reduces the number of observations.
> >
> > Original:
> >
> > ```text
> > a = [a₁ a₂ a₃ a₄ a₅ a₆ a₇ a₈]
> > ```
> >
> > With $m=2$:
> >
> > ```text
> > [a₁ a₂] → b₁
> > [a₃ a₄] → b₂
> > [a₅ a₆] → b₃
> > [a₇ a₈] → b₄
> > ```
> >
> > So:
> >
> > $$8\text{ observations}\rightarrow4\text{ observations}$$
> >
> > More generally:
> >
> > $$n\rightarrow\left\lfloor\frac{n}{m}\right\rfloor$$
> >
> > complete blocks are produced.
>
> > [!abstract]- Number of Elements in b
> > Suppose `a` has $n$ elements and each block has $m$ elements.
> >
> > The number of **complete** blocks is:
> >
> > $$\left\lfloor\frac{n}{m}\right\rfloor$$
> >
> > Therefore:
> >
> > $$\text{length}(b)=\left\lfloor\frac{n}{m}\right\rfloor$$
> >
> > The floor operation means we keep only complete blocks.
> >
> > For example:
> >
> > $$n=10,\qquad m=3$$
> >
> > Then:
> >
> > $$\left\lfloor\frac{10}{3}\right\rfloor=3$$
> >
> > So only $9$ values are used.
> >
> > One value remains unused.
>
> > [!warning]- Incomplete Final Block
> > Exercise 2 explicitly says that if fewer than $m$ elements remain, those elements are **discarded**. 
> >
> > Example:
> >
> > ```text
> > a = [2; 4; 6; 8; 10]
> > m = 2
> > ```
> >
> > Blocks:
> >
> > ```text
> > [2;4]   → 3
> > [6;8]   → 7
> > [10]    → discarded
> > ```
> >
> > Therefore:
> >
> > ```text
> > b = [3;7]
> > ```
> >
> > We do **not** calculate an average using the incomplete block.
>
> > [!abstract]- Finding the Start and End of a Block
> > Suppose the block number is `j` and the block size is `m`.
> >
> > The first element of block `j` is:
> >
> > $$\text{start}=(j-1)m+1$$
> >
> > The last element is:
> >
> > $$\text{end}=jm$$
> >
> > Example:
> >
> > ```text
> > m = 3
> > ```
> >
> > For block $j=1$:
> >
> > $$\text{start}=1,\qquad\text{end}=3$$
> >
> > For block $j=2$:
> >
> > $$\text{start}=4,\qquad\text{end}=6$$
> >
> > For block $j=3$:
> >
> > $$\text{start}=7,\qquad\text{end}=9$$
>
> > [!abstract]- MATLAB Indexing for a Block
> > MATLAB allows us to access a consecutive section of a vector using:
> >
> > ```matlab
> > a(start:end)
> > ```
> >
> > Example:
> >
> > ```matlab
> > a(4:6)
> > ```
> >
> > accesses:
> >
> > ```text
> > a(4), a(5), a(6)
> > ```
> >
> > Therefore, one block average can be calculated using:
> >
> > ```matlab
> > total = 0;
> >
> > for i = start:end
> >     total = total + a(i);
> > end
> >
> > average = total/m;
> > ```
>
> > [!abstract]- Block Averaging with a Loop
> > The overall structure is:
> >
> > ```matlab
> > n = size(a,1);
> > nb = floor(n/m);
> >
> > for j = 1:nb
> >     start = (j-1)*m + 1;
> >     finish = j*m;
> >
> >     total = 0;
> >
> >     for i = start:finish
> >         total = total + a(i);
> >     end
> >
> >     b(j) = total/m;
> > end
> > ```
> >
> > Here:
> >
> > - `j` identifies the block.
> > - `start` identifies the first element.
> > - `finish` identifies the last element.
> > - `i` moves through the elements inside the block.
> > - `total` accumulates the block sum.
> > - `b(j)` stores the block average.
>
> > [!abstract]- Two Different Loop Variables
> > It is important to understand why two indices are used.
> >
> > ```matlab
> > for j = 1:nb
> > ```
> >
> > chooses **which block** we are processing.
> >
> > ```matlab
> > for i = start:finish
> > ```
> >
> > chooses **which element inside that block** we are processing.
> >
> > So:
> >
> > ```text
> > j → block
> > i → element
> > ```
>
> > [!abstract]- Preallocating the Output
> > We know the number of complete blocks beforehand:
> >
> > $$nb=\left\lfloor\frac{n}{m}\right\rfloor$$
> >
> > We can therefore create the output vector before the loop:
> >
> > ```matlab
> > b = zeros(nb,1);
> > ```
> >
> > Then:
> >
> > ```matlab
> > b(j) = total/m;
> > ```
> >
> > stores each result in its correct position.
> >
> > This is generally cleaner than repeatedly growing a vector inside a loop.
>
> > [!abstract]- Minimum and Maximum of b
> > Exercise 2 asks for the minimum and maximum of the resulting vector `b`.
> >
> > The same manual minimum/maximum logic from Exercise 1 can be reused.
> >
> > For example:
> >
> > ```matlab
> > minimum = b(1);
> >
> > for i = 2:nb
> >     if b(i) < minimum
> >         minimum = b(i);
> >     end
> > end
> > ```
> >
> > The maximum is calculated similarly.
>
> > [!abstract]- Average of b
> > Once `b` has been created, its average is:
> >
> > $$\bar{b}=\frac{1}{N_b}\sum_{j=1}^{N_b}b_j$$
> >
> > where:
> >
> > $$N_b=\left\lfloor\frac{n}{m}\right\rfloor$$
> >
> > In MATLAB:
> >
> > ```matlab
> > total = 0;
> >
> > for j = 1:nb
> >     total = total + b(j);
> > end
> >
> > average = total/nb;
> > ```
>
> > [!abstract]- Standard Deviation of b
> > After calculating the average of `b`, calculate:
> >
> > $$\sum_{j=1}^{N_b}(b_j-\bar{b})^2$$
> >
> > using a loop:
> >
> > ```matlab
> > sumsq = 0;
> >
> > for j = 1:nb
> >     deviation = b(j) - average;
> >     sumsq = sumsq + deviation^2;
> > end
> > ```
> >
> > Then apply the standard-deviation convention expected by the course.
>
> > [!abstract]- What Happens When m Changes?
> > Exercise 2 asks you to vary `m` and observe how the five reported quantities change. 
> >
> > The five quantities are:
> >
> > ```text
> > number of elements in b
> > minimum
> > maximum
> > average
> > standard deviation
> > ```
> >
> > As $m$ increases:
> >
> > $$\text{larger blocks}\rightarrow\text{fewer block averages}$$
> >
> > Therefore:
> >
> > $$m\uparrow\quad\Rightarrow\quad |b|\downarrow$$
>
> > [!abstract]- Why Averaging Reduces Variation
> > Suppose a block contains values:
> >
> > ```text
> > 2, 4, 6, 8
> > ```
> >
> > Its average is:
> >
> > $$\frac{2+4+6+8}{4}=5$$
> >
> > The extreme values $2$ and $8$ have been replaced by the central value $5$.
> >
> > Averaging tends to smooth out fluctuations.
> >
> > Therefore, when larger blocks are averaged, the resulting values often show less variation than the original observations.
>
> > [!abstract]- Intuition Behind Larger m
> > Think of $m$ as the amount of data being combined into one observation.
> >
> > Small $m$:
> >
> > ```text
> > few observations → each average retains more variation
> > ```
> >
> > Large $m$:
> >
> > ```text
> > many observations → fluctuations tend to cancel
> > ```
> >
> > Therefore, increasing $m$ generally produces smoother block averages.
>
> > [!abstract]- Histogram of b
> > Exercise 2 asks you to use a histogram to comment on the distribution of `b`. 
> >
> > Basic syntax:
> >
> > ```matlab
> > histogram(b)
> > ```
> >
> > Depending on the data and value of $m$, the histogram can change because the individual observations have been replaced by averages of groups of observations.
>
> > [!abstract]- Important Distinction
> > `a` contains the **original observations**.
> >
> > `b` contains **block averages**.
> >
> > Therefore:
> >
> > $$a\rightarrow\text{grouping}\rightarrow\text{averaging}\rightarrow b$$
> >
> > `b` is not simply a subset of `a`.
> >
> > Each element of `b` represents several observations from `a`.
>
> > [!warning]- Common Mistakes
> > Avoid these mistakes when implementing `ex2fun(a,m)`:
> >
> > ```text
> > Using an incomplete final block
> > ```
> >
> > The lab says to discard it.
> >
> > ```text
> > Dividing by the wrong number
> > ```
> >
> > Each complete block contains exactly $m$ elements, so its average is divided by $m$.
> >
> > ```text
> > Confusing block index with element index
> > ```
> >
> > `j` can represent the block and `i` can represent the element.
> >
> > ```text
> > Forgetting to reset total
> > ```
> >
> > `total = 0` must be done for every new block.
> >
> > ```text
> > Accidentally modifying a
> > ```
> >
> > The purpose is to create a new vector `b`.
>
> > [!important]- Exercise 2 — What You Should Now Understand
> > Before solving Exercise 2, you should understand:
> >
> > ```text
> > block
> > block size m
> > complete block
> > incomplete block
> > floor(n/m)
> > nested loops
> > block indexing
> > element indexing
> > accumulator
> > block average
> > data reduction
> > effect of averaging on variation
> > histogram of block averages
> > ```
> >
> > The exercise asks you to create `ex2fun(a,m)`, calculate the requested statistics of `b`, use `m=4` with `ex2a.m`, examine its distribution, and vary `m` to observe how the statistics change.

---

> [!important]- Exercise 1 — ex1fun(a)
>
> > [!abstract]- Understand the Problem
> > We need to write a MATLAB function:
> >
> > ```matlab
> > ex1fun(a)
> > ```
> >
> > where `a` is a **column vector of integers**.
> >
> > The function must display:
> >
> > ```text
> > number of elements
> > minimum
> > maximum
> > frequency of every integer from minimum to maximum
> > average
> > standard deviation
> > ```
> >
> > The lab specifically says that built-in MATLAB functions must not be used for calculations, except `size`.
>
> > [!abstract]- Overall Strategy
> > We can divide the problem into independent tasks:
> >
> > ```text
> > Input a
> >    ↓
> > Find number of elements
> >    ↓
> > Find minimum
> >    ↓
> > Find maximum
> >    ↓
> > Find frequency of every integer
> >    ↓
> > Calculate average
> >    ↓
> > Calculate standard deviation
> >    ↓
> > Display results
> > ```
> >
> > This is much easier than trying to write everything at once.
>
> > [!abstract]- Create the Function
> > A MATLAB function is defined using:
> >
> > ```matlab
> > function ex1fun(a)
> > ```
> >
> > followed by the function body and:
> >
> > ```matlab
> > end
> > ```
> >
> > So the basic structure is:
> >
> > ```matlab
> > function ex1fun(a)
> >
> >     % calculations
> >
> > end
> > ```
> >
> > Save this in a file named:
> >
> > ```text
> > ex1fun.m
> > ```
> >
> > The function name and file name should match.
>
> > [!abstract]- Find the Number of Elements
> > The lab allows `size`, so we can use:
> >
> > ```matlab
> > n = size(a,1);
> > ```
> >
> > Since `a` is a column vector:
> >
> > ```text
> > size(a,1)
> > ```
> >
> > gives the number of rows, which is also the number of elements.
> >
> > For example:
> >
> > ```matlab
> > a = [5; 2; 8; 2; 4];
> > ```
> >
> > gives:
> >
> > ```text
> > n = 5
> > ```
>
> > [!abstract]- Why We Need n
> > We will use `n` repeatedly.
> >
> > For example:
> >
> > ```matlab
> > for i = 1:n
> > ```
> >
> > means:
> >
> > ```text
> > visit a(1)
> > visit a(2)
> > visit a(3)
> > ...
> > visit a(n)
> > ```
> >
> > So calculating `n` once makes the rest of the program easier.
>
> > [!abstract]- Find the Minimum
> > We cannot use:
> >
> > ```matlab
> > min(a)
> > ```
> >
> > because Exercise 1 prohibits built-in calculation functions.
> >
> > Instead, use the first element as the initial candidate:
> >
> > ```matlab
> > minimum = a(1);
> > ```
> >
> > Then examine the remaining elements:
> >
> > ```matlab
> > for i = 2:n
> >     if a(i) < minimum
> >         minimum = a(i);
> >     end
> > end
> > ```
> >
> > Example:
> >
> > ```text
> > a = [5; 2; 8; 2; 4]
> > ```
> >
> > Start:
> >
> > ```text
> > minimum = 5
> > ```
> >
> > Compare with `2`:
> >
> > ```text
> > 2 < 5 → minimum = 2
> > ```
> >
> > Compare with `8`:
> >
> > ```text
> > 8 < 2 → false
> > ```
> >
> > Compare with `2`:
> >
> > ```text
> > 2 < 2 → false
> > ```
> >
> > Compare with `4`:
> >
> > ```text
> > 4 < 2 → false
> > ```
> >
> > Final:
> >
> > ```text
> > minimum = 2
> > ```
>
> > [!abstract]- Find the Maximum
> > The same approach works for the maximum.
> >
> > Start with:
> >
> > ```matlab
> > maximum = a(1);
> > ```
> >
> > Then:
> >
> > ```matlab
> > for i = 2:n
> >     if a(i) > maximum
> >         maximum = a(i);
> >     end
> > end
> > ```
> >
> > We are maintaining a **current best candidate**.
> >
> > For minimum:
> >
> > $$\text{replace if current value}<\text{current minimum}$$
> >
> > For maximum:
> >
> > $$\text{replace if current value}>\text{current maximum}$$
>
> > [!abstract]- Find the Frequency of Each Integer
> > This is the most important part of Exercise 1.
> >
> > Suppose:
> >
> > ```text
> > a = [2; 4; 2; 5; 4; 2]
> > ```
> >
> > We first know:
> >
> > ```text
> > minimum = 2
> > maximum = 5
> > ```
> >
> > Therefore, we need to check:
> >
> > ```text
> > 2
> > 3
> > 4
> > 5
> > ```
> >
> > For each value, count how many times it appears in `a`.
>
> > [!abstract]- Outer Loop for Possible Values
> > We can generate every integer from minimum to maximum using:
> >
> > ```matlab
> > for x = minimum:maximum
> > ```
> >
> > If:
> >
> > ```text
> > minimum = 2
> > maximum = 5
> > ```
> >
> > then:
> >
> > ```matlab
> > minimum:maximum
> > ```
> >
> > produces:
> >
> > ```text
> > 2  3  4  5
> > ```
> >
> > So `x` represents the value whose frequency we are currently calculating.
>
> > [!abstract]- Inner Loop for Searching
> > Once we choose a value `x`, we need to search the entire vector.
> >
> > ```matlab
> > for i = 1:n
> > ```
> >
> > Inside this loop, compare:
> >
> > ```matlab
> > a(i) == x
> > ```
> >
> > If they are equal, we found one occurrence.
> >
> > ```matlab
> > if a(i) == x
> >     count = count + 1;
> > end
> > ```
>
> > [!abstract]- Complete Frequency Logic
> > Combining the two loops:
> >
> > ```matlab
> > for x = minimum:maximum
> >     count = 0;
> >
> >     for i = 1:n
> >         if a(i) == x
> >             count = count + 1;
> >         end
> >     end
> >
> >     disp(count)
> > end
> > ```
> >
> > The outer loop asks:
> >
> > ```text
> > "How many times does x occur?"
> > ```
> >
> > The inner loop searches every element to answer that question.
>
> > [!important]- Why count = 0 Must Be Inside the Outer Loop
> > Suppose:
> >
> > ```text
> > a = [2; 4; 2; 5; 4; 2]
> > ```
> >
> > For `x = 2`, the answer is:
> >
> > ```text
> > count = 3
> > ```
> >
> > When we move to `x = 3`, we must start counting from zero again.
> >
> > Therefore:
> >
> > ```matlab
> > for x = minimum:maximum
> >     count = 0;
> > ```
> >
> > is essential.
> >
> > Otherwise the count from the previous value would carry over.
>
> > [!abstract]- Calculate the Average
> > The average is:
> >
> > $$\bar{x}=\frac{x_1+x_2+\cdots+x_n}{n}$$
> >
> > First calculate the sum:
> >
> > ```matlab
> > total = 0;
> >
> > for i = 1:n
> >     total = total + a(i);
> > end
> > ```
> >
> > Then:
> >
> > ```matlab
> > average = total/n;
> > ```
> >
> > We cannot use:
> >
> > ```matlab
> > mean(a)
> > ```
> >
> > because of the Exercise 1 restriction.
>
> > [!abstract]- Calculate Standard Deviation
> > Once the average is known, calculate the squared deviations:
> >
> > $$\left(a_i-\bar{x}\right)^2$$
> >
> > using:
> >
> > ```matlab
> > sumsq = 0;
> >
> > for i = 1:n
> >     deviation = a(i) - average;
> >     sumsq = sumsq + deviation^2;
> > end
> > ```
> >
> > At this point:
> >
> > $$\text{sumsq}=\sum_{i=1}^{n}(a_i-\bar{x})^2$$
> >
> > The PDF does not specify whether to divide by $n$ or $n-1$, so we should use the convention expected by your instructor/course.
>
> > [!abstract]- Displaying the Results
> > We can use `disp()`:
> >
> > ```matlab
> > disp(n)
> > disp(minimum)
> > disp(maximum)
> > ```
> >
> > But for a readable report, `fprintf()` is better:
> >
> > ```matlab
> > fprintf('Number of elements = %d\n', n);
> > fprintf('Minimum = %d\n', minimum);
> > fprintf('Maximum = %d\n', maximum);
> > ```
> >
> > For frequencies:
> >
> > ```matlab
> > fprintf('Value = %d, Frequency = %d\n', x, count);
> > ```
>
> > [!important]- The Logic of the Complete Function
> > At this point, the complete logical flow is:
> >
> > ```text
> > a
> > ↓
> > size(a)
> > ↓
> > n
> > ↓
> > ┌───────────────┐
> > │ Find minimum  │
> > └───────────────┘
> > ↓
> > ┌───────────────┐
> > │ Find maximum  │
> > └───────────────┘
> > ↓
> > ┌──────────────────────┐
> > │ minimum → maximum    │
> > │        ↓             │
> > │ search entire vector │
> > │        ↓             │
> > │ count occurrences    │
> > └──────────────────────┘
> > ↓
> > ┌────────────────┐
> > │ Calculate mean │
> > └────────────────┘
> > ↓
> > ┌─────────────────────────┐
> > │ Calculate standard      │
> > │ deviation               │
> > └─────────────────────────┘
> > ↓
> > Display everything
> > ```
>
> > [!example]- Small Example to Trace by Hand
> > Take:
> >
> > ```matlab
> > a = [3; 1; 3; 2; 1];
> > ```
> >
> > Number of elements:
> >
> > $$n=5$$
> >
> > Minimum:
> >
> > $$1$$
> >
> > Maximum:
> >
> > $$3$$
> >
> > Frequencies:
> >
> > ```text
> > 1 → 2
> > 2 → 1
> > 3 → 2
> > ```
> >
> > Mean:
> >
> > $$\bar{x}=\frac{3+1+3+2+1}{5}=2$$
> >
> > The deviations are:
> >
> > ```text
> > 3 - 2 =  1
> > 1 - 2 = -1
> > 3 - 2 =  1
> > 2 - 2 =  0
> > 1 - 2 = -1
> > ```
> >
> > Squared deviations:
> >
> > ```text
> > 1, 1, 1, 0, 1
> > ```
> >
> > This small example is useful for checking whether our MATLAB implementation is behaving correctly.
>
> > [!warning]- Common Mistakes in Exercise 1
> > ```text
> > Using min(a), max(a), mean(a), std(a)
> > ```
> >
> > These violate the stated restriction on built-in calculation functions.
> >
> > ```text
> > Using = instead of ==
> > ```
> >
> > Equality comparison requires `==`.
> >
> > ```text
> > Forgetting to reset count
> > ```
> >
> > `count = 0` must be inside the outer frequency loop.
> >
> > ```text
> > Forgetting to reset total
> > ```
> >
> > Each independent accumulation needs its own initialization.
> >
> > ```text
> > Starting minimum/maximum from 0
> > ```
> >
> > This can fail if all values are positive or all values are negative. Using `a(1)` is safer.
> >
> > ```text
> > Starting the minimum/maximum loop at 1
> > ```
> >
> > It is cleaner to initialize using `a(1)` and then compare from `i = 2:n`.
>
> > [!important]- Next Step
> > We now have all the logic needed to write `ex1fun(a)`.
> >
> > The next step is to combine these pieces into the **actual MATLAB function**, then test it manually using a small vector before applying it to `ex1a`, `ex1b`, and `ex1c`.

> [!important]- Exercise 1 — Implementing ex1fun(a)
>
> > [!abstract]- Function Skeleton
> > Create a file named:
> >
> > ```text
> > ex1fun.m
> > ```
> >
> > Start with:
> >
> > ```matlab
> > function ex1fun(a)
> >
> > end
> > ```
> >
> > The function receives `a` as its input.
>
> > [!abstract]- Number of Elements
> > Since `a` is a column vector:
> >
> > ```matlab
> > n = size(a,1);
> > ```
> >
> > We can immediately display it:
> >
> > ```matlab
> > fprintf('Number of elements = %d\n', n);
> > ```
>
> > [!abstract]- Minimum and Maximum
> > Add the manual minimum calculation:
> >
> > ```matlab
> > minimum = a(1);
> >
> > for i = 2:n
> >     if a(i) < minimum
> >         minimum = a(i);
> >     end
> > end
> > ```
> >
> > Then the maximum:
> >
> > ```matlab
> > maximum = a(1);
> >
> > for i = 2:n
> >     if a(i) > maximum
> >         maximum = a(i);
> >     end
> > end
> > ```
> >
> > At this point we know:
> >
> > ```text
> > n
> > minimum
> > maximum
> > ```
>
> > [!abstract]- Frequency Calculation
> > Now use the minimum and maximum to determine which integers need to be checked:
> >
> > ```matlab
> > for x = minimum:maximum
> >     count = 0;
> >
> >     for i = 1:n
> >         if a(i) == x
> >             count = count + 1;
> >         end
> >     end
> >
> >     fprintf('Value = %d, Frequency = %d\n', x, count);
> > end
> > ```
> >
> > Notice the two loops have different jobs:
> >
> > ```text
> > x → which value are we counting?
> > i → which element of a are we checking?
> > ```
>
> > [!abstract]- Average Calculation
> > First calculate the sum:
> >
> > ```matlab
> > total = 0;
> >
> > for i = 1:n
> >     total = total + a(i);
> > end
> > ```
> >
> > Then:
> >
> > ```matlab
> > average = total/n;
> > ```
> >
> > Display it:
> >
> > ```matlab
> > fprintf('Average = %f\n', average);
> > ```
>
> > [!abstract]- Standard Deviation Calculation
> > First calculate the sum of squared deviations:
> >
> > ```matlab
> > sumsq = 0;
> >
> > for i = 1:n
> >     deviation = a(i) - average;
> >     sumsq = sumsq + deviation^2;
> > end
> > ```
> >
> > The PDF does not specify whether the course expects division by $n$ or $n-1$. Therefore, that convention must come from the course/instructor; it should not be assumed from the lab statement alone.
> >
> > For example, if the course uses the population definition:
> >
> > ```matlab
> > standard_deviation = sqrt(sumsq/n);
> > ```
> >
> > If it uses the sample definition:
> >
> > ```matlab
> > standard_deviation = sqrt(sumsq/(n-1));
> > ```
> >
> > Do not use `std(a)` because the exercise prohibits built-in calculation functions.
>
> > [!important]- Complete Function
> > Putting everything together:
> >
> > ```matlab
> > function ex1fun(a)
> >
> >     % Number of elements
> >     n = size(a,1);
> >
> >     fprintf('Number of elements = %d\n', n);
> >
> >     % Minimum
> >     minimum = a(1);
> >
> >     for i = 2:n
> >         if a(i) < minimum
> >             minimum = a(i);
> >         end
> >     end
> >
> >     fprintf('Minimum = %d\n', minimum);
> >
> >     % Maximum
> >     maximum = a(1);
> >
> >     for i = 2:n
> >         if a(i) > maximum
> >             maximum = a(i);
> >         end
> >     end
> >
> >     fprintf('Maximum = %d\n', maximum);
> >
> >     % Frequency
> >     for x = minimum:maximum
> >         count = 0;
> >
> >         for i = 1:n
> >             if a(i) == x
> >                 count = count + 1;
> >             end
> >         end
> >
> >         fprintf('Value = %d, Frequency = %d\n', x, count);
> >     end
> >
> >     % Average
> >     total = 0;
> >
> >     for i = 1:n
> >         total = total + a(i);
> >     end
> >
> >     average = total/n;
> >
> >     fprintf('Average = %f\n', average);
> >
> >     % Standard deviation
> >     sumsq = 0;
> >
> >     for i = 1:n
> >         deviation = a(i) - average;
> >         sumsq = sumsq + deviation^2;
> >     end
> >
> >     % Choose the convention specified by your course
> >     standard_deviation = sqrt(sumsq/n);
> >
> >     fprintf('Standard deviation = %f\n', standard_deviation);
> >
> > end
> > ```
>
> > [!example]- Test With a Small Vector
> > Before using the large Moodle datasets, test the function with:
> >
> > ```matlab
> > a = [3; 1; 3; 2; 1];
> > ex1fun(a)
> > ```
> >
> > We already know the expected basic results:
> >
> > ```text
> > Number of elements = 5
> > Minimum = 1
> > Maximum = 3
> > ```
> >
> > Frequencies:
> >
> > ```text
> > 1 → 2
> > 2 → 1
> > 3 → 2
> > ```
> >
> > Average:
> >
> > $$\bar{x}=2$$
> >
> > Squared deviations:
> >
> > $$1+1+1+0+1=4$$
> >
> > Therefore, with the population convention:
> >
> > $$\sigma=\sqrt{\frac{4}{5}}\approx0.8944$$
>
> > [!abstract]- Test the Function Step by Step
> > A good debugging approach is to temporarily test each part separately.
> >
> > First:
> >
> > ```matlab
> > a = [3; 1; 3; 2; 1];
> > n = size(a,1)
> > ```
> >
> > Check that:
> >
> > ```text
> > n = 5
> > ```
> >
> > Then test minimum and maximum.
> >
> > Then test frequency counting.
> >
> > Then test average.
> >
> > Finally test standard deviation.
> >
> > This makes it easier to identify exactly where an error occurs.
>
> > [!warning]- Important Edge Case
> > The function assumes that `a` contains at least one element because we use:
> >
> > ```matlab
> > a(1)
> > ```
> >
> > If `a` were empty, `a(1)` would produce an indexing error.
> >
> > The lab describes `a` as a column vector of integers but does not explicitly discuss an empty input, so we do not need to add extra handling unless your instructor expects it.
>
> > [!important]- Apply It to ex1a, ex1b and ex1c
> > The lab provides `ex1a`, `ex1b`, and `ex1c` files. Running one creates the variable `a`.
> >
> > For example:
> >
> > ```matlab
> > ex1a
> > ex1fun(a)
> > ```
> >
> > After finishing the analysis of `ex1a`, you can load:
> >
> > ```matlab
> > ex1b
> > ex1fun(a)
> > ```
> >
> > Then:
> >
> > ```matlab
> > ex1c
> > ex1fun(a)
> > ```
> >
> > Be careful: loading the next file may overwrite the existing variable `a`. The lab explicitly warns about this.
>
> > [!abstract]- Exercise 1 Report Questions
> > After running the three datasets, the lab also asks you to reason about their distributions:
> >
> > ```text
> > Which vector seems uniformly distributed?
> > Why?
> >
> > What are the likely distributions of ex1b and ex1c?
> > ```
> >
> > These questions should be answered using the observed data and the histograms/statistics rather than guessing beforehand.

> [!important]- Exercise 2 — Implementing ex2fun(a,m)
>
> > [!abstract]- Function Requirement
> > We need to create:
> >
> >     function ex2fun(a,m)
> >
> > where `a` is a column vector and `m` is a positive integer.
> >
> > The function must create a new vector `b`.
> >
> > Each element of `b` is the average of the next `m` elements of `a`.
> >
> > If fewer than `m` elements remain, those elements are discarded.
>
> > [!example]- Simple Example
> > Suppose:
> >
> >     a = [2; 4; 6; 8; 10; 12; 14];
> >     m = 3;
> >
> > Divide `a` into complete blocks:
> >
> >     [2,  4,  6]  → 4
> >     [8, 10, 12]  → 10
> >     [14]         → discarded
> >
> > Therefore:
> >
> >     b = [4; 10]
> >
> > The last element is discarded because it does not form a complete block of size $3$.
>
> > [!abstract]- Number of Complete Blocks
> > Let:
> >
> > $$n=\text{number of elements in }a$$
> >
> > The number of complete blocks is:
> >
> > $$n_b=\left\lfloor\frac{n}{m}\right\rfloor$$
> >
> > In MATLAB:
> >
> >     n = size(a,1);
> >     nb = floor(n/m);
> >
> > For example, if:
> >
> > $$n=7,\qquad m=3$$
> >
> > then:
> >
> > $$n_b=\left\lfloor\frac{7}{3}\right\rfloor=2$$
> >
> > Therefore, only two complete blocks are used.
>
> > [!abstract]- Create the Output Vector
> > Since `b` contains one value for every complete block:
> >
> >     b = zeros(nb,1);
> >
> > If there are two complete blocks:
> >
> >     b =
> >          0
> >          0
> >
> > These values will later be replaced by the calculated block averages.
>
> > [!abstract]- Finding the Start and End of a Block
> > Let `j` represent the block number.
> >
> > The first element of block `j` is:
> >
> > $$\text{start}=(j-1)m+1$$
> >
> > The last element is:
> >
> > $$\text{finish}=jm$$
> >
> > In MATLAB:
> >
> >     start = (j-1)*m + 1;
> >     finish = j*m;
> >
> > For $m=3$:
> >
> >     j = 1 → start = 1, finish = 3
> >     j = 2 → start = 4, finish = 6
> >     j = 3 → start = 7, finish = 9
>
> > [!abstract]- Calculate One Block Average
> > Once we know the beginning and end of a block, we add its elements.
> >
> >     total = 0;
> >
> >     for i = start:finish
> >         total = total + a(i);
> >     end
> >
> >     block_average = total/m;
> >
> > The inner loop processes exactly `m` elements.
> >
> > Therefore:
> >
> > $$\text{block average}=\frac{\text{sum of block}}{m}$$
>
> > [!abstract]- Store the Block Average
> > The average of block `j` is stored in `b(j)`:
> >
> >     b(j) = block_average;
> >
> > Therefore, the overall block-processing structure is:
> >
> >     for j = 1:nb
> >         start = (j-1)*m + 1;
> >         finish = j*m;
> >
> >         total = 0;
> >
> >         for i = start:finish
> >             total = total + a(i);
> >         end
> >
> >         b(j) = total/m;
> >     end
>
> > [!important]- Complete Block-Averaging Code
> > The complete section for creating `b` is:
> >
> >     n = size(a,1);
> >     nb = floor(n/m);
> >
> >     b = zeros(nb,1);
> >
> >     for j = 1:nb
> >         start = (j-1)*m + 1;
> >         finish = j*m;
> >
> >         total = 0;
> >
> >         for i = start:finish
> >             total = total + a(i);
> >         end
> >
> >         b(j) = total/m;
> >     end
> >
> > The roles of the variables are:
> >
> >     j     → block number
> >     i     → element inside the block
> >     total → sum of the current block
> >     b(j)  → average of the current block
>
> > [!abstract]- Calculate Minimum of b
> > We can reuse the minimum logic from Exercise 1:
> >
> >     minimum = b(1);
> >
> >     for i = 2:nb
> >         if b(i) < minimum
> >             minimum = b(i);
> >         end
> >     end
>
> > [!abstract]- Calculate Maximum of b
> > Similarly:
> >
> >     maximum = b(1);
> >
> >     for i = 2:nb
> >         if b(i) > maximum
> >             maximum = b(i);
> >         end
> >     end
>
> > [!abstract]- Calculate Average of b
> > The average of `b` is:
> >
> > $$\bar{b}=\frac{1}{n_b}\sum_{j=1}^{n_b}b_j$$
> >
> > MATLAB implementation:
> >
> >     total = 0;
> >
> >     for j = 1:nb
> >         total = total + b(j);
> >     end
> >
> >     average = total/nb;
>
> > [!abstract]- Calculate Standard Deviation of b
> > First calculate the squared deviations:
> >
> >     sumsq = 0;
> >
> >     for j = 1:nb
> >         deviation = b(j) - average;
> >         sumsq = sumsq + deviation^2;
> >     end
> >
> > Then apply the standard-deviation convention required by the course.
> >
> > The Lab 2 PDF does not specify whether the denominator should be $n_b$ or $n_b-1$.
>
> > [!abstract]- Display the Results
> > The exercise asks for:
> >
> >     number of elements in b
> >     minimum
> >     maximum
> >     average
> >     standard deviation
> >
> > We can use `fprintf()`:
> >
> >     fprintf('Number of elements in b = %d\n', nb);
> >     fprintf('Minimum = %f\n', minimum);
> >     fprintf('Maximum = %f\n', maximum);
> >     fprintf('Average = %f\n', average);
> >     fprintf('Standard deviation = %f\n', standard_deviation);
>
> > [!important]- Complete ex2fun(a,m)
> > Combining the above sections:
> >
> >     function ex2fun(a,m)
> >
> >         n = size(a,1);
> >         nb = floor(n/m);
> >
> >         b = zeros(nb,1);
> >
> >         % Calculate block averages
> >         for j = 1:nb
> >             start = (j-1)*m + 1;
> >             finish = j*m;
> >
> >             total = 0;
> >
> >             for i = start:finish
> >                 total = total + a(i);
> >             end
> >
> >             b(j) = total/m;
> >         end
> >
> >         % Minimum
> >         minimum = b(1);
> >
> >         for i = 2:nb
> >             if b(i) < minimum
> >                 minimum = b(i);
> >             end
> >         end
> >
> >         % Maximum
> >         maximum = b(1);
> >
> >         for i = 2:nb
> >             if b(i) > maximum
> >                 maximum = b(i);
> >             end
> >         end
> >
> >         % Average
> >         total = 0;
> >
> >         for j = 1:nb
> >             total = total + b(j);
> >         end
> >
> >         average = total/nb;
> >
> >         % Standard deviation
> >         sumsq = 0;
> >
> >         for j = 1:nb
> >             deviation = b(j) - average;
> >             sumsq = sumsq + deviation^2;
> >         end
> >
> >         standard_deviation = sqrt(sumsq/nb);
> >
> >         % Display
> >         fprintf('Number of elements in b = %d\n', nb);
> >         fprintf('Minimum = %f\n', minimum);
> >         fprintf('Maximum = %f\n', maximum);
> >         fprintf('Average = %f\n', average);
> >         fprintf('Standard deviation = %f\n', standard_deviation);
> >
> >     end
> >
> > The standard-deviation denominator above uses $n_b$ as an example. Confirm the convention expected by your course before submitting.
>
> > [!example]- Test With a Small Vector
> > Use:
> >
> >     a = [2; 4; 6; 8; 10; 12; 14];
> >     ex2fun(a,3)
> >
> > The blocks are:
> >
> >     [2, 4, 6]   → 4
> >     [8, 10, 12] → 10
> >     [14]        → discarded
> >
> > Therefore:
> >
> >     b = [4; 10]
> >
> > So:
> >
> > $$\min(b)=4$$
> >
> > $$\max(b)=10$$
> >
> > $$\bar b=7$$
>
> > [!abstract]- Run ex2a
> > The lab specifically asks you to use `ex2a.m` with:
> >
> >     m = 4;
> >
> > After running `ex2a.m` and obtaining `a`, run:
> >
> >     ex2fun(a,4)
> >
> > Record the five requested statistics.
>
> > [!abstract]- Histogram of b
> > The lab asks you to use `hist()` to comment on the distribution of `b`.
> >
> >     hist(b)
> >
> > The histogram allows us to visually examine how the block averages are distributed.
> >
> > When describing it, look for features such as:
> >
> >     concentrated
> >     spread out
> >     approximately symmetric
> >     skewed
> >     approximately uniform
> >
> > The conclusion should be based on the actual histogram produced from `ex2a`.
>
> > [!abstract]- Varying m
> > The lab asks you to vary `m` and comment on how the five quantities change.
> >
> > For example:
> >
> >     ex2fun(a,2)
> >     ex2fun(a,4)
> >     ex2fun(a,8)
> >     ex2fun(a,16)
> >
> > For each value of `m`, record:
> >
> >     number of elements in b
> >     minimum
> >     maximum
> >     average
> >     standard deviation
>
> > [!abstract]- Effect of Increasing m
> > The number of complete blocks is:
> >
> > $$n_b=\left\lfloor\frac{n}{m}\right\rfloor$$
> >
> > Therefore:
> >
> > $$m\uparrow\quad\Rightarrow\quad n_b\downarrow$$
> >
> > In other words, increasing the block size produces fewer output observations.
> >
> > Each output observation also represents more original observations, so block averaging tends to smooth fluctuations.
>
> > [!warning]- Common Mistakes
> > Avoid:
> >
> >     nb = n/m
> >
> > when `n/m` is not an integer.
> >
> > Use:
> >
> >     nb = floor(n/m);
> >
> > Also avoid:
> >
> >     b(j) = total/(number of remaining elements)
> >
> > because the final incomplete block must be discarded. Every block that is actually averaged contains exactly `m` elements.
> >
> > Remember to reset:
> >
> >     total = 0;
> >
> > at the beginning of every block.
>
> > [!important]- Exercise 2 Checklist
> > Before considering Exercise 2 complete:
> >
> >     ex2fun(a,m) created
> >     b created correctly
> >     incomplete block discarded
> >     number of elements in b calculated
> >     minimum calculated
> >     maximum calculated
> >     average calculated
> >     standard deviation calculated
> >     ex2a tested with m = 4
> >     histogram created
> >     different values of m tested
> >     observations recorded for the report

---

> [!important]- Exercise 3 — Milk Shop Profit and Inventory
>
> > [!abstract]- Problem Setup
> > Bindu buys milk at:
> >
> > $$₹30/\text{litre}$$
> >
> > She sells milk to customers at:
> >
> > $$₹35/\text{litre}$$
> >
> > If demand is greater than supply, the unsatisfied demand is a lost sale.
> >
> > If supply is greater than demand, the excess milk is sold to a confectioner at:
> >
> > $$₹23/\text{litre}$$
> >
> > No milk remains at the end of the day in the first part of the exercise.
>
> > [!abstract]- Demand and Supply
> > The lab provides two data files:
> >
> >     demand.m
> >     supply.m
> >
> > Running them creates:
> >
> >     dem
> >     supp
> >
> > The data contains demand and supply information for:
> >
> > $$730\text{ days}$$
> >
> > Therefore, we need to calculate one profit value for each day.
> >
> > The final profit array should therefore contain:
> >
> > $$730\text{ values}$$
>
> > [!abstract]- Meaning of Demand and Supply
> > For a particular day:
> >
> > `dem(i)` represents the customer demand.
> >
> > `supp(i)` represents the amount of milk supplied/available.
> >
> > We compare:
> >
> > $$\text{demand}\quad\text{vs.}\quad\text{supply}$$
> >
> > This comparison determines what happens to the milk that day.
>
> > [!abstract]- The Three Important Quantities
> > For each litre of milk, we need to distinguish:
> >
> > **Purchase cost**
> >
> > $$₹30$$
> >
> > **Customer selling price**
> >
> > $$₹35$$
> >
> > **Confectioner selling price**
> >
> > $$₹23$$
> >
> > The customer price is higher than the purchase cost:
> >
> > $$35-30=₹5$$
> >
> > So every litre sold to a customer produces:
> >
> > $$₹5$$
> >
> > of profit.
>
> > [!abstract]- Case When Demand Is Greater Than Supply
> > Suppose:
> >
> > $$D>S$$
> >
> > where:
> >
> > $$D=\text{demand}$$
> >
> > $$S=\text{supply}$$
> >
> > Since there is not enough milk to satisfy all customers, all available milk can be sold to customers.
> >
> > Therefore:
> >
> > $$\text{customer sales}=S$$
> >
> > Revenue:
> >
> > $$35S$$
> >
> > Purchase cost:
> >
> > $$30S$$
> >
> > Therefore:
> >
> > $$\text{profit}=35S-30S$$
> >
> > $$\boxed{\text{profit}=5S}$$
> >
> > The remaining demand is lost.
>
> > [!abstract]- Case When Supply Is Greater Than Demand
> > Suppose:
> >
> > $$S>D$$
> >
> > All demand can be satisfied.
> >
> > Customer sales:
> >
> > $$D$$
> >
> > Excess milk:
> >
> > $$S-D$$
> >
> > The excess is sold to the confectioner at ₹23/litre.
> >
> > Customer revenue:
> >
> > $$35D$$
> >
> > Confectioner revenue:
> >
> > $$23(S-D)$$
> >
> > Purchase cost:
> >
> > $$30S$$
> >
> > Therefore:
> >
> > $$\text{profit}=35D+23(S-D)-30S$$
> >
> > This can also be simplified:
> >
> > $$\text{profit}=35D+23S-23D-30S$$
> >
> > $$\boxed{\text{profit}=12D-7S}$$
>
> > [!abstract]- Case When Demand Equals Supply
> > If:
> >
> > $$D=S$$
> >
> > all supplied milk is sold to customers.
> >
> > Profit is:
> >
> > $$35D-30D$$
> >
> > Therefore:
> >
> > $$\boxed{\text{profit}=5D}$$
> >
> > This is consistent with the demand-greater-than-supply formula when $D=S$.
>
> > [!important]- Daily Profit Formula
> > Combining the cases:
> >
> > If:
> >
> > $$D\geq S$$
> >
> > then:
> >
> > $$\text{profit}=5S$$
> >
> > If:
> >
> > $$S>D$$
> >
> > then:
> >
> > $$\text{profit}=35D+23(S-D)-30S$$
> >
> > or:
> >
> > $$\text{profit}=12D-7S$$
> >
> > Therefore, the MATLAB logic can be written as:
> >
> >     if dem(i) >= supp(i)
> >         profit(i) = 5*supp(i);
> >     else
> >         profit(i) = 35*dem(i) + 23*(supp(i)-dem(i)) - 30*supp(i);
> >     end
>
> > [!abstract]- Why We Need an if Statement
> > The profit formula changes depending on the relationship between demand and supply.
> >
> > This is exactly the kind of situation where `if/else` is useful:
> >
> >     if condition
> >         % first situation
> >     else
> >         % second situation
> >     end
> >
> > Here the condition is:
> >
> >     dem(i) >= supp(i)
>
> > [!abstract]- Daily Profit Array
> > Since there are 730 days, we need to calculate:
> >
> >     profit(1)
> >     profit(2)
> >     ...
> >     profit(730)
> >
> > A `for` loop is therefore appropriate:
> >
> >     for i = 1:730
> >         % calculate profit for day i
> >     end
> >
> > A better approach is to determine the number of observations from the data rather than hard-code `730`.
> >
> > For example:
> >
> >     n = size(dem,1);
> >
> > Then:
> >
> >     profit = zeros(n,1);
> >
> > and:
> >
> >     for i = 1:n
> >         ...
> >     end
>
> > [!important]- Basic MATLAB Structure
> > After loading the data:
> >
> >     demand
> >     supply
> >
> > or according to the actual file behavior provided by the lab, the variables `dem` and `supp` should be available.
> >
> > Then:
> >
> >     n = size(dem,1);
> >     profit = zeros(n,1);
> >
> >     for i = 1:n
> >         if dem(i) >= supp(i)
> >             profit(i) = 5*supp(i);
> >         else
> >             profit(i) = 35*dem(i) + 23*(supp(i)-dem(i)) - 30*supp(i);
> >         end
> >     end
>
> > [!abstract]- Why Preallocate profit
> > We know that one profit value is needed for every day.
> >
> > Therefore:
> >
> >     profit = zeros(n,1);
> >
> > creates space for all daily profits before the loop.
> >
> > Then each iteration fills one position:
> >
> >     profit(i) = ...
> >
> > This is preferable to repeatedly expanding the vector.
>
> > [!example]- Manually Check One Day
> > Suppose:
> >
> > $$D=40,\qquad S=30$$
> >
> > Demand is greater than supply.
> >
> > Therefore all $30$ litres are sold to customers.
> >
> > Profit:
> >
> > $$5(30)=₹150$$
> >
> > So:
> >
> >     profit(i) = 150;
>
> > [!example]- Another Day
> > Suppose:
> >
> > $$D=30,\qquad S=40$$
> >
> > Customer sales:
> >
> > $$30\text{ litres}$$
> >
> > Excess:
> >
> > $$40-30=10\text{ litres}$$
> >
> > Customer revenue:
> >
> > $$35(30)=1050$$
> >
> > Confectioner revenue:
> >
> > $$23(10)=230$$
> >
> > Purchase cost:
> >
> > $$30(40)=1200$$
> >
> > Therefore:
> >
> > $$\text{profit}=1050+230-1200$$
> >
> > $$\boxed{₹80}$$
>
> > [!abstract]- Important Observation About Excess Milk
> > Selling excess milk to the confectioner is not profitable on the excess litres because:
> >
> > $$23-30=-₹7$$
> >
> > So every excess litre sold to the confectioner produces a loss of:
> >
> > $$₹7$$
> >
> > However, selling the milk to customers produces:
> >
> > $$35-30=₹5$$
> >
> > profit per litre.
> >
> > This distinction is important when interpreting the results.
>
> > [!abstract]- Statistical Analysis of Profit
> > The lab asks you to calculate important statistical measures and make observations about the daily profit.
> >
> > Depending on what has been covered in your course, useful measures may include:
> >
> >     mean
> >     minimum
> >     maximum
> >     standard deviation
> >
> > Since the exercise asks for statistical measures but does not specify an exact list in the PDF, use the measures expected by your instructor/course.
>
> > [!abstract]- Histogram of Daily Profit
> > A histogram can help visualize how daily profit is distributed.
> >
> >     histogram(profit)
> >
> > Possible observations include:
> >
> >     where most profits are concentrated
> >     whether there are unusually high or low profits
> >     whether the distribution appears symmetric
> >     whether the distribution appears skewed
> >
> > The actual observations should come from the supplied 730-day data.
>
> > [!important]- Two-Day Storage
> > The second part changes the assumption.
> >
> > Previously:
> >
> > ```text
> > no milk remains at the end of the day
> > ```
> >
> > Now:
> >
> > ```text
> > milk can be stored for 2 days
> > ```
> >
> > Any milk still unsold after 2 days is sold to the confectioner at ₹23/litre.
> >
> > This changes the problem because today's excess supply can potentially satisfy tomorrow's demand.
>
> > [!abstract]- Inventory Becomes Important
> > Without storage, the only milk available today is today's supply:
> >
> > $$\text{available today}=\text{today's supply}$$
> >
> > With storage:
> >
> > $$\text{available today}=\text{today's supply}+\text{stored milk}$$
> >
> > Therefore, we now need an additional variable representing inventory.
> >
> > For example:
> >
> >     inventory
> >
> > represents milk carried from previous days.
>
> > [!abstract]- Why Storage Changes the Logic
> > Suppose:
> >
> > ```text
> > Day 1:
> > supply > demand
> > ```
> >
> > Some milk remains after serving customers.
> >
> > Instead of immediately selling all of it to the confectioner, some can be carried into the next day.
> >
> > Then on Day 2:
> >
> >     available milk = Day 2 supply + stored milk
> >
> > This can reduce lost sales when Day 2 demand is high.
>
> > [!abstract]- Inventory Flow
> > Conceptually:
> >
> >     Previous inventory
> >            +
> >     Today's supply
> >            ↓
> >     Available milk
> >            ↓
> >     Satisfy today's demand
> >            ↓
> >     Remaining milk
> >            ↓
> >     Store or sell to confectioner
> >
> > This is different from the first part because the current day's decision depends on previous days.
>
> > [!warning]- Storage Requires Careful Interpretation
> > The PDF says milk can be stored for 2 days and unsold milk after 2 days is sold at ₹23.
> >
> > However, the exact intended inventory-aging implementation is not fully specified in the excerpt.
> >
> > Before coding this part, we should determine precisely how your instructor expects the two-day storage to be represented:
> >
> >     one inventory variable
> >
> > or:
> >
> >     separate inventory for milk with different remaining shelf lives
> >
> > We should not silently assume a particular aging convention if the course material has not specified it.
>
> > [!important]- Exercise 3 Core Programming Skills
> > This exercise combines:
> >
> >     vectors
> >     indexing
> >     for loops
> >     if/else
> >     preallocation
> >     arithmetic modeling
> >     daily profit calculation
> >     statistical analysis
> >     histograms
> >     inventory/state tracking
> >
> > The first part is straightforward once the profit cases are translated into equations.
>
> > [!important]- Exercise 3 — First Part Checklist
> > Before moving to the storage version:
> >
> >     load dem and supp
> >     determine number of days
> >     create profit vector
> >     process every day
> >     compare demand and supply
> >     calculate daily profit
> >     store profit(i)
> >     calculate required statistics
> >     create a histogram if useful
> >     write observations for the report

> [!important]- Exercise 3 — Implementing Daily Profit
>
> > [!abstract]- Load the Data
> > The lab provides:
> >
> >     demand.m
> >     supply.m
> >
> > These create the variables:
> >
> >     dem
> >     supp
> >
> > The data represents 730 days.
> >
> > After loading the data, check the number of observations:
> >
> >     n = size(dem,1);
> >
> > We can then create the profit vector:
> >
> >     profit = zeros(n,1);
>
> > [!abstract]- The Decision for Each Day
> > For each day `i`, compare:
> >
> >     dem(i)
> >
> > with:
> >
> >     supp(i)
> >
> > There are two cases:
> >
> >     dem(i) >= supp(i)
> >
> > and:
> >
> >     dem(i) < supp(i)
> >
> > The profit formula is different in these two cases.
>
> > [!abstract]- Case: Demand Greater Than or Equal to Supply
> > When:
> >
> >     dem(i) >= supp(i)
> >
> > there is not enough milk to satisfy all the demand.
> >
> > Therefore, all available milk is sold to customers:
> >
> > $$\text{customer sales}=\text{supp}(i)$$
> >
> > Each litre produces:
> >
> > $$35-30=₹5$$
> >
> > Therefore:
> >
> > $$\text{profit}=5\times\text{supp}(i)$$
> >
> > MATLAB:
> >
> >     if dem(i) >= supp(i)
> >         profit(i) = 5*supp(i);
> >     end
>
> > [!example]- Demand Greater Than Supply
> > Suppose:
> >
> >     dem(i) = 40
> >     supp(i) = 30
> >
> > All 30 litres can be sold to customers.
> >
> > Profit per litre:
> >
> > $$35-30=₹5$$
> >
> > Therefore:
> >
> > $$\text{profit}=30\times5=₹150$$
> >
> > The remaining 10 litres of demand are simply lost sales.
>
> > [!abstract]- Case: Supply Greater Than Demand
> > When:
> >
> >     dem(i) < supp(i)
> >
> > all customer demand can be satisfied.
> >
> > Customer sales:
> >
> > $$D=\text{dem}(i)$$
> >
> > Excess milk:
> >
> > $$S-D=\text{supp}(i)-\text{dem}(i)$$
> >
> > The excess is sold to the confectioner at ₹23/litre.
> >
> > Therefore:
> >
> > $$\text{revenue}=35D+23(S-D)$$
> >
> > Purchase cost:
> >
> > $$30S$$
> >
> > Hence:
> >
> > $$\text{profit}=35D+23(S-D)-30S$$
>
> > [!abstract]- Simplifying the Second Case
> > Starting with:
> >
> > $$35D+23(S-D)-30S$$
> >
> > Expand:
> >
> > $$35D+23S-23D-30S$$
> >
> > Combine similar terms:
> >
> > $$12D-7S$$
> >
> > Therefore:
> >
> > $$\boxed{\text{profit}=12D-7S}$$
> >
> > MATLAB can use either form:
> >
> >     profit(i) = 35*dem(i) ...
> >              + 23*(supp(i)-dem(i)) ...
> >              - 30*supp(i);
> >
> > or the simplified form:
> >
> >     profit(i) = 12*dem(i) - 7*supp(i);
> >
> > The first form is often easier to relate directly to the business problem.
>
> > [!example]- Supply Greater Than Demand
> > Suppose:
> >
> >     dem(i) = 30
> >     supp(i) = 40
> >
> > Customer revenue:
> >
> > $$35(30)=1050$$
> >
> > Excess:
> >
> > $$40-30=10$$
> >
> > Confectioner revenue:
> >
> > $$23(10)=230$$
> >
> > Purchase cost:
> >
> > $$30(40)=1200$$
> >
> > Therefore:
> >
> > $$\text{profit}=1050+230-1200$$
> >
> > $$\boxed{₹80}$$
>
> > [!abstract]- Translate the Cases into if/else
> > The two cases combine naturally into:
> >
> >     if dem(i) >= supp(i)
> >         profit(i) = 5*supp(i);
> >     else
> >         profit(i) = 35*dem(i) ...
> >                  + 23*(supp(i)-dem(i)) ...
> >                  - 30*supp(i);
> >     end
> >
> > This is the central logic of the first part.
>
> > [!abstract]- Put the Logic Inside a Loop
> > We need one profit value for every day.
> >
> > Therefore:
> >
> >     for i = 1:n
> >         if dem(i) >= supp(i)
> >             profit(i) = 5*supp(i);
> >         else
> >             profit(i) = 35*dem(i) ...
> >                      + 23*(supp(i)-dem(i)) ...
> >                      - 30*supp(i);
> >         end
> >     end
> >
> > Each iteration represents one day.
> >
> >     i = 1 → Day 1
> >     i = 2 → Day 2
> >     i = 3 → Day 3
> >     ...
> >     i = n → Day n
>
> > [!important]- Complete First-Part Code
> > A straightforward implementation is:
> >
> >     demand
> >     supply
> >
> >     n = size(dem,1);
> >     profit = zeros(n,1);
> >
> >     for i = 1:n
> >         if dem(i) >= supp(i)
> >             profit(i) = 5*supp(i);
> >         else
> >             profit(i) = 35*dem(i) ...
> >                      + 23*(supp(i)-dem(i)) ...
> >                      - 30*supp(i);
> >         end
> >     end
> >
> > This produces the required daily profit array.
>
> > [!abstract]- Why We Use profit(i)
> > We don't want just one profit value because each day has different demand and supply.
> >
> > Therefore:
> >
> >     profit(1)
> >
> > stores Day 1 profit,
> >
> >     profit(2)
> >
> > stores Day 2 profit,
> >
> > and so on.
> >
> > The final array represents the complete 730-day history.
>
> > [!abstract]- Verify the Array
> > After running the program, you can inspect:
> >
> >     profit
> >
> > You can also check its size:
> >
> >     size(profit)
> >
> > According to the lab, the data covers 730 days, so the expected profit array should contain 730 daily values.
>
> > [!abstract]- Calculate the Mean Profit
> > If we want the average daily profit manually:
> >
> >     total = 0;
> >
> >     for i = 1:n
> >         total = total + profit(i);
> >     end
> >
> >     average_profit = total/n;
> >
> > Mathematically:
> >
> > $$\bar P=\frac{1}{n}\sum_{i=1}^{n}P_i$$
> >
> > where $P_i$ is the profit on day $i$.
>
> > [!abstract]- Find Minimum and Maximum Profit
> > We can reuse the same logic from Exercise 1.
> >
> > Minimum:
> >
> >     minimum_profit = profit(1);
> >
> >     for i = 2:n
> >         if profit(i) < minimum_profit
> >             minimum_profit = profit(i);
> >         end
> >     end
> >
> > Maximum:
> >
> >     maximum_profit = profit(1);
> >
> >     for i = 2:n
> >         if profit(i) > maximum_profit
> >             maximum_profit = profit(i);
> >         end
> >     end
>
> > [!abstract]- Standard Deviation of Profit
> > First calculate the average profit.
> >
> > Then:
> >
> >     sumsq = 0;
> >
> >     for i = 1:n
> >         deviation = profit(i) - average_profit;
> >         sumsq = sumsq + deviation^2;
> >     end
> >
> > Then apply the standard-deviation convention expected by your course.
> >
> > As before, the PDF does not specify the denominator convention for standard deviation.
>
> > [!abstract]- Histogram of Profit
> > A histogram can help us see the distribution of daily profits.
> >
> >     hist(profit)
> >
> > A useful plot should have appropriate labels and a title because the general Lab 2 instructions require proper axis labels, legends, and plot titles for figures.
> >
> > For example:
> >
> >     xlabel('Daily Profit')
> >     ylabel('Frequency')
> >     title('Distribution of Daily Profit')
>
> > [!abstract]- What to Observe
> > The lab asks for important statistical measures and observations.
> >
> > After calculating the statistics and viewing the histogram, examine:
> >
> >     average daily profit
> >     minimum daily profit
> >     maximum daily profit
> >     spread of profits
> >     unusually high or low days
> >     shape of the profit distribution
> >
> > The observations should be based on the actual 730-day data.
>
> > [!warning]- Common Modeling Mistakes
> > **Using demand instead of supply when demand exceeds supply**
> >
> > If:
> >
> >     dem(i) > supp(i)
> >
> > only `supp(i)` litres can actually be sold.
> >
> > So:
> >
> >     profit(i) = 5*supp(i);
> >
> > **Forgetting the confectioner**
> >
> > When supply exceeds demand, the excess milk is still sold at ₹23/litre.
> >
> > **Charging ₹35 for excess milk**
> >
> > Excess milk is sold to the confectioner at ₹23, not ₹35.
> >
> > **Forgetting purchase cost**
> >
> > Profit is revenue minus the cost of all milk purchased:
> >
> > $$\text{profit}=\text{revenue}-30S$$
> >
> > **Using the same formula for both cases**
> >
> > The revenue structure changes depending on whether demand or supply is larger.
>
> > [!important]- First Part — Final Logic
> > The complete reasoning is:
> >
> >     For each day
> >          ↓
> >     Read demand D
> >          ↓
> >     Read supply S
> >          ↓
> >     Is D >= S?
> >        ↓              ↓
> >       Yes             No
> >        ↓              ↓
> >     Sell S to       Sell D to
> >     customers       customers
> >                       +
> >                     sell S-D
> >                     to confectioner
> >        ↓              ↓
> >     Profit = 5S    Profit = 35D + 23(S-D) - 30S
> >        ↓              ↓
> >        └───────┬──────┘
> >                ↓
> >         Store profit(i)
> >                ↓
> >          Next day

> [!important]- Exercise 3 — Two-Day Milk Storage
>
> > [!abstract]- What Changes?
> > In the first part, no milk remains at the end of a day.
> >
> > Therefore:
> >
> >     Today's supply
> >             ↓
> >     Today's demand
> >             ↓
> >     Remaining milk → confectioner
> >
> > With storage, this is no longer true.
> >
> > Some unsold milk can be carried into future days.
> >
> > The new flow becomes:
> >
> >     Previous inventory
> >            +
> >     Today's supply
> >            ↓
> >     Available milk
> >            ↓
> >     Today's demand
> >            ↓
> >     Remaining milk
> >            ↓
> >     Store / sell to confectioner
>
> > [!abstract]- Why Inventory Is Needed
> > Suppose on one day:
> >
> > $$S>D$$
> >
> > There is excess milk:
> >
> > $$S-D$$
> >
> > In the original problem, this excess is sold to the confectioner immediately.
> >
> > With storage, some of this milk can be carried forward.
> >
> > Therefore, tomorrow's available milk can include milk from today.
> >
> > This means today's decision affects tomorrow's profit.
>
> > [!abstract]- State Variable
> > We need some variable that remembers milk carried from previous days.
> >
> > Conceptually:
> >
> >     inventory
> >
> > represents milk available from previous days.
> >
> > On day $i$:
> >
> > $$\text{available milk}
> > =
> > \text{today's supply}
> > +
> > \text{previous inventory}$$
> >
> > This is the key difference from the first part.
>
> > [!abstract]- Daily Processing
> > For each day, the conceptual sequence is:
> >
> >     Previous inventory
> >            +
> >     Today's supply
> >            ↓
> >     Total available milk
> >            ↓
> >     Compare with demand
> >
> > If available milk is at least the demand:
> >
> >     satisfy all demand
> >
> > If available milk is less than demand:
> >
> >     sell all available milk
> >     remaining demand is lost
> >
> > After satisfying demand, some milk may remain.
>
> > [!abstract]- When Demand Can Be Fully Satisfied
> > Let:
> >
> > $$A=\text{available milk}$$
> >
> > and:
> >
> > $$D=\text{demand}$$
> >
> > If:
> >
> > $$A\geq D$$
> >
> > then all demand can be satisfied.
> >
> > Customer sales:
> >
> > $$D$$
> >
> > Remaining milk:
> >
> > $$A-D$$
> >
> > The remaining milk is the amount that may be stored for future use, subject to the two-day storage rule.
>
> > [!abstract]- When Demand Exceeds Available Milk
> > If:
> >
> > $$D>A$$
> >
> > all available milk can be sold to customers.
> >
> > Customer sales:
> >
> > $$A$$
> >
> > Lost demand:
> >
> > $$D-A$$
> >
> > No milk remains from that day's available inventory.
> >
> > Therefore:
> >
> >     inventory after sales = 0
> >
> > subject to any other inventory-ageing rule required by the course.
>
> > [!abstract]- Profit of Customer Sales
> > Milk sold to customers generates:
> >
> > $$35-30=₹5$$
> >
> > per litre relative to the purchase cost of newly supplied milk.
> >
> > However, with storage there is an important modeling issue: the PDF does not explicitly state how the cost of stored milk should be accounted for when it is sold on a later day.
> >
> > The supplied lab statement tells us the selling prices and storage rule, but does not provide a detailed accounting convention for inventory carried between days.
>
> > [!warning]- Do Not Assume the Missing Inventory Convention
> > The PDF says:
> >
> >     milk can be stored for 2 days
> >
> > and:
> >
> >     unsold after 2 days is sold at Rs 23
> >
> > But the excerpt does not specify all details needed to uniquely determine the implementation, such as:
> >
> >     whether FIFO must be used
> >     exactly when the two-day age expires
> >     how the purchase cost of carried milk is accounted for
> >     whether today's fresh supply is used before older inventory
> >
> > Therefore, we should **not invent these rules**.
> >
> > The correct implementation should follow the convention given in your lecture, instructor's notes, or any additional Exercise 3 instructions.
>
> > [!abstract]- Why FIFO May Matter
> > If milk from different days has different remaining storage time, we may need to know which milk is being used first.
> >
> > For example:
> >
> >     Day 1 inventory → older
> >     Day 2 inventory → newer
> >
> > If Day 3 demand occurs, using the older milk first would prevent it from expiring before the newer milk.
> >
> > This is the basic idea behind **first-in, first-out (FIFO)** inventory handling.
> >
> > However, the Lab 2 PDF does not explicitly state FIFO, so this should not be assumed unless your course material specifies it.
>
> > [!abstract]- Inventory Age
> > A two-day storage rule means that age can matter.
> >
> > Conceptually, we could distinguish:
> >
> >     fresh inventory
> >
> > and:
> >
> >     one-day-old inventory
> >
> > After another day passes, the older inventory reaches its storage limit.
> >
> > This means a simple single variable:
> >
> >     inventory
> >
> > may not be sufficient if the exact age of the milk needs to be tracked.
>
> > [!abstract]- Possible State Representation
> > If the course specifies age tracking, the state could conceptually contain:
> >
> >     inventory_today
> >     inventory_one_day_old
> >
> > At the end of a day:
> >
> >     today's leftover
> >             ↓
> >     becomes stored inventory
> >
> > and:
> >
> >     previous stored inventory
> >             ↓
> >     becomes older
> >
> > Once milk reaches the two-day limit, it is sold to the confectioner according to the lab statement.
>
> > [!abstract]- General Inventory Algorithm
> > Once the instructor's exact storage convention is known, the program will follow this general structure:
> >
> >     Initialize inventory
> >
> >     for each day
> >
> >         read today's supply
> >         read today's demand
> >
> >         determine available milk
> >
> >         satisfy demand as much as possible
> >
> >         calculate revenue
> >
> >         determine remaining milk
> >
> >         update inventory age
> >
> >         sell expired milk to confectioner
> >
> >         store the remaining eligible milk
> >
> >     end
>
> > [!abstract]- Difference From the First Part
> > First part:
> >
> >     profit(i) depends only on
> >     dem(i) and supp(i)
> >
> > Storage version:
> >
> >     profit(i) depends on
> >     dem(i)
> >     supp(i)
> >     previous inventory
> >     inventory age
> >
> > Therefore:
> >
> > $$\text{storage introduces memory into the system}$$
> >
> > This is the main programming concept introduced by the second part.
>
> > [!abstract]- Comparing the Two Models
> > Without storage:
> >
> > $$\text{Day }i\text{ is largely independent of previous inventory}$$
> >
> > With storage:
> >
> > $$\text{Day }i\text{ depends on the inventory carried from previous days}$$
> >
> > Therefore, storage can change:
> >
> >     average profit
> >     minimum profit
> >     maximum profit
> >     standard deviation
> >
> > The lab asks you to compare the statistical results of the two cases.
>
> > [!important]- What We Can Code From the PDF
> > The first part can be implemented completely from the supplied statement because its profit rules are explicit.
> >
> > For the two-day-storage part, the PDF gives the storage duration and final confectioner sale rule, but does not fully specify the inventory-accounting convention.
> >
> > Therefore, before writing the final storage code, we should use any additional lecture material or instructions from your instructor if they contain the missing convention.
>
> > [!important]- Exercise 3 — Key Concepts
> > By the end of Exercise 3, you should understand:
> >
> >     demand
> >     supply
> >     revenue
> >     purchase cost
> >     profit
> >     lost sales
> >     excess inventory
> >     conditional logic
> >     daily profit array
> >     inventory
> >     inventory age
> >     storage limit
> >     state-dependent calculations
> >     comparison of statistical results

---

> [!important]- Exercise 4 — Simulation with `rand()`
>
> > [!abstract]- Simulation
> >
> > Simulation means using a computer to imitate a random process repeatedly.
> >
> > In this exercise, we simulate demand and supply for 2000 days instead of using actual observed data.
> >
> > Given:
> >
> > - Demand and supply are independent.
> > - Both are uniformly distributed between 20 and 40.
> > - MATLAB `rand()` is used to generate the random values.
>
> > [!abstract]- `rand()`
> >
> > `rand()` generates a random number between $0$ and $1$.
> >
> >     x = rand();
> >
> > For example:
> >
> >     x = 0.3748;
> >
> > Every call generates another random value.
> >
> >     x1 = rand();
> >     x2 = rand();
> >     x3 = rand();
> >
> > The generated values follow the uniform distribution on $[0,1]$.
>
> > [!abstract]- Generating Uniform Values Between 20 and 40
> >
> > `rand()` gives a value between $0$ and $1$.
> >
> > To transform it to the interval $[20,40]$:
> >
> > $$
> > X = 20 + (40-20)U
> > $$
> >
> > where
> >
> > $$
> > U \sim U(0,1)
> > $$
> >
> > Therefore:
> >
> > $$
> > X = 20 + 20U
> > $$
> >
> > In MATLAB:
> >
> >     x = 20 + 20*rand();
> >
> > Therefore, demand and supply can be generated as:
> >
> >     demand = 20 + 20*rand();
> >     supply = 20 + 20*rand();
>
> > [!abstract]- Independence
> >
> > The exercise states that demand and supply are independent.
> >
> > Mathematically:
> >
> > $$
> > D \perp S
> > $$
> >
> > Therefore, they can be generated independently:
> >
> >     D = 20 + 20*rand();
> >     S = 20 + 20*rand();
>
> > [!abstract]- Daily Revenue
> >
> > For each simulated day, revenue depends on demand and supply.
> >
> > From Exercise 3:
> >
> > If
> >
> > $$
> > D \geq S
> > $$
> >
> > all supplied milk is sold to customers.
> >
> > Customer selling price:
> >
> > $$
> > ₹35/\text{litre}
> > $$
> >
> > Therefore:
> >
> > $$
> > R = 35S
> > $$
> >
> > If
> >
> > $$
> > S>D
> > $$
> >
> > then:
> >
> > - $D$ litres are sold to customers.
> > - $S-D$ litres are sold to the confectioner.
> >
> > Therefore:
> >
> > $$
> > R = 35D + 23(S-D)
> > $$
> >
> > **Important:** Exercise 4 asks for average **revenue**, not average profit.
>
> > [!abstract]- Running Average
> >
> > Suppose the daily revenues are:
> >
> > $$
> > R_1,R_2,\ldots,R_n
> > $$
> >
> > The average after $n$ days is:
> >
> > $$
> > A_n =
> > \frac{R_1+R_2+\cdots+R_n}{n}
> > $$
> >
> > We can update this average using the previous average instead of storing every revenue.
> >
> > Previous average:
> >
> > $$
> > A_{n-1}
> > =
> > \frac{R_1+\cdots+R_{n-1}}{n-1}
> > $$
> >
> > Therefore:
> >
> > $$
> > (n-1)A_{n-1}
> > =
> > R_1+\cdots+R_{n-1}
> > $$
> >
> > After observing today's revenue $R_n$:
> >
> > $$
> > A_n
> > =
> > \frac{(n-1)A_{n-1}+R_n}{n}
> > $$
> >
> > Hence:
> >
> > $$
> > \boxed{
> > A_n =
> > \frac{(n-1)A_{n-1}+R_n}{n}
> > }
> > $$
>
> > [!abstract]- Printing Every 50 Days
> >
> > The exercise asks for the average at:
> >
> > $$
> > 50,100,150,\ldots,2000
> > $$
> >
> > We can check whether the current day is a multiple of 50 using:
> >
> >     if mod(day,50) == 0
> >
> > `mod(a,b)` gives the remainder when $a$ is divided by $b$.
> >
> > For example:
> >
> >     mod(100,50) = 0
> >     mod(150,50) = 0
> >     mod(127,50) = 27
>
> > [!abstract]- `fprintf`
> >
> > The required output is similar to:
> >
> >     Day = 50 Average till now = 23.56
> >
> > MATLAB:
> >
> >     fprintf('Day = %d Average till now = %.2f\n', day, average);
> >
> > Here:
> >
> > - `%d` → integer
> > - `%.2f` → 2 digits after the decimal point
> > - `\n` → new line
>
> > [!abstract]- Storing Values for the Plot
> >
> > The exercise asks us to plot average revenue against the day.
> >
> > Therefore, we need values representing:
> >
> >     days
> >     averages
> >
> > For example, whenever we calculate the current average:
> >
> >     days(day) = day;
> >     averages(day) = average;
> >
> > Then:
> >
> >     plot(days, averages)
> >     xlabel('Day')
> >     ylabel('Average Revenue')
> >     title('Running Average Revenue')
> >
> > The lab instructions also require proper axis labels, legends where applicable, titles, and saving the figures. 
>
> > [!abstract]- Why the Running Average Stabilizes
> >
> > At the beginning, the average can change significantly because it is based on only a few observations.
> >
> > For example:
> >
> > $$
> > A_{10}
> > $$
> >
> > is based on only 10 days, while
> >
> > $$
> > A_{2000}
> > $$
> >
> > is based on 2000 days.
> >
> > As the number of observations increases, the effect of any single day's random revenue becomes smaller.
> >
> > Therefore, the running average generally becomes more stable as the number of simulated days increases.
>
> > [!abstract]- One-Day Storage
> >
> > The exercise then asks us to assume that milk can be stored for one day.
> >
> > Without storage:
> >
> > $$
> > \text{Available milk}
> > =
> > \text{Today's supply}
> > $$
> >
> > With one-day storage:
> >
> > $$
> > \text{Available milk}
> > =
> > \text{Today's supply}
> > +
> > \text{Previous leftover}
> > $$
> >
> > Therefore, the current day's calculation depends on the previous day's leftover milk.
> >
> > This introduces a **state variable** into the simulation.
> >
> > The PDF does not specify the complete inventory-accounting convention for the stored milk, so we should not assume additional rules that are not given.
>
> > [!abstract]- Overall Programming Pattern
> >
> > The simulation follows this structure:
> >
> >     for day = 1:2000
> >
> >         % Generate demand
> >         % Generate supply
> >
> >         % Calculate today's revenue
> >
> >         % Update running average
> >
> >         % Store day and average
> >
> >         % Print every 50 days
> >
> >     end
> >
> > The overall idea is:
> >
> > $$
> > \boxed{
> > \text{Generate}
> > \rightarrow
> > \text{Calculate}
> > \rightarrow
> > \text{Update}
> > \rightarrow
> > \text{Record}
> > \rightarrow
> > \text{Plot}
> > }
> > $$
>
> > [!abstract]- Common Mistakes
> >
> > - Using `rand()` directly as demand instead of transforming it to $[20,40]$.
> > - Forgetting that demand and supply are independent.
> > - Calculating the average using only today's revenue.
> > - Confusing revenue with profit.
> > - Printing the result every day instead of every 50 days.
> > - Forgetting axis labels and title.
> > - Forgetting to save the figure.
> > - Adding assumptions about one-day storage that are not specified in the question.
>
> > [!abstract]- Takeaway
> >
> > The main transformation is:
> >
> > $$
> > U\sim U(0,1)
> > \quad\Rightarrow\quad
> > X=20+20U
> > $$
> >
> > The running-average update is:
> >
> > $$
> > \boxed{
> > A_n =
> > \frac{(n-1)A_{n-1}+R_n}{n}
> > }
> > $$
> >
> > The complete simulation pattern is:
> >
> > $$
> > \boxed{
> > \text{Generate}
> > \rightarrow
> > \text{Calculate}
> > \rightarrow
> > \text{Update}
> > \rightarrow
> > \text{Record}
> > \rightarrow
> > \text{Plot}
> > }
> > $$

> [!important]- Exercise 5 — `rand()` and `exprnd()`
>
> > [!abstract]- Purpose
> >
> > Exercise 5 is mainly about understanding the behavior of random-number generators by:
> >
> > - generating random values using `rand()`
> > - observing their distribution using a histogram
> > - repeating the experiment for different sample sizes
> > - generating values using `exprnd()`
> > - comparing the resulting distributions
> > - discarding exponential values below $0.5$
> >
> > The exercise asks for plots, proper labels/title/legend, and comments on the observed distributions.
>
> > [!abstract]- Testing `rand()`
> >
> > MATLAB's `rand()` generates random values between $0$ and $1$.
> >
> > To investigate whether the generated values appear uniformly distributed, we generate many values and examine their histogram.
> >
> > For example:
> >
> >     x = rand(1000,1);
> >     hist(x)
> >
> > The histogram shows how frequently values fall into different intervals.
>
> > [!abstract]- `testrand(n)`
> >
> > The exercise asks you to write:
> >
> >     testrand(n)
> >
> > where `n` is the number of times `rand()` is called.
> >
> > The experiment must be performed for:
> >
> >     n = 10
> >     n = 1000
> >     n = 1000000
> >
> > The purpose is to observe how the histogram changes as the sample size increases.
>
> > [!abstract]- Sample Size and Histogram
> >
> > With a small sample:
> >
> > $$
> > n=10
> > $$
> >
> > there are very few observations, so the histogram may look irregular.
> >
> > With a larger sample:
> >
> > $$
> > n=1000
> > $$
> >
> > the histogram should give a clearer picture of the underlying distribution.
> >
> > With:
> >
> > $$
> > n=1,000,000
> > $$
> >
> > the histogram should provide a much more stable picture.
> >
> > The important idea is that increasing the sample size gives more information about the distribution of the random generator.
>
> > [!abstract]- Histogram
> >
> > A histogram groups numerical observations into intervals called bins and shows how many observations fall into each interval.
> >
> > For random-number experiments, the histogram is useful for visually examining the distribution of generated values.
> >
> > In MATLAB:
> >
> >     hist(x)
> >
> > The exercise specifically asks you to use histograms and comment on uniformity.
>
> > [!abstract]- Uniform Distribution
> >
> > For `rand()`, the generated values lie between $0$ and $1$.
> >
> > The relevant distribution is the uniform distribution on:
> >
> > $$
> > [0,1]
> > $$
> >
> > Conceptually, values throughout this interval are generated according to the same uniform distribution.
> >
> > Therefore, with a sufficiently large sample, the histogram should become approximately flat.
>
> > [!abstract]- Testing `exprnd()`
> >
> > The exercise then asks you to repeat the experiment using MATLAB's:
> >
> >     exprnd()
> >
> > The purpose is to observe how the histogram differs from the histogram obtained using `rand()`.
> >
> > Unlike `rand()`, `exprnd()` generates values according to an exponential distribution.
> >
> > Therefore, its histogram is not expected to be flat.
>
> > [!abstract]- Comparing `rand()` and `exprnd()`
> >
> > The important visual difference is:
> >
> > **`rand()`**
> >
> > Values are generated over a bounded interval:
> >
> > $$
> > 0\leq X\leq1
> > $$
> >
> > Its histogram should become approximately flat as $n$ increases.
> >
> > **`exprnd()`**
> >
> > Generates exponentially distributed values.
> >
> > Its histogram has a different shape and is concentrated more heavily near smaller values.
> >
> > The exercise asks you to explain these differences based on the observed plots.
>
> > [!abstract]- Discarding Values Below 0.5
> >
> > The final part asks you to:
> >
> > - generate $n$ values using `exprnd()`
> > - discard values less than $0.5$
> > - subtract $0.5$ from every retained value
> >
> > If the generated value is $X$, retain it only when:
> >
> > $$
> > X\geq0.5
> > $$
> >
> > For every retained value, calculate:
> >
> > $$
> > Y=X-0.5
> > $$
> >
> > So the transformation is:
> >
> > $$
> > \boxed{
> > Y=X-0.5,\qquad X\geq0.5
> > }
> > $$
>
> > [!abstract]- Fraction Discarded
> >
> > The exercise specifically asks for:
> >
> > $$
> > n=50000
> > $$
> >
> > and asks you to report the fraction of generated values that were discarded.
> >
> > If:
> >
> > - total generated values = $n$
> > - discarded values = $k$
> >
> > then:
> >
> > $$
> > \text{Fraction discarded}
> > =
> > \frac{k}{n}
> > $$
> >
> > Percentage discarded:
> >
> > $$
> > \text{Percentage discarded}
> > =
> > \frac{k}{n}\times100
> > $$
>
> > [!abstract]- Retained Values
> >
> > Suppose the generated values are:
> >
> >     x = [0.2 0.7 1.4 0.4 2.1]
> >
> > Values below $0.5$ are discarded:
> >
> >     0.2
> >     0.4
> >
> > Retained values:
> >
> >     0.7
> >     1.4
> >     2.1
> >
> > Then subtract $0.5$:
> >
> >     0.2
> >     0.9
> >     1.6
> >
> > These transformed values are what should be plotted in the final histogram.
>
> > [!abstract]- Logical Structure
> >
> > The filtering operation can be thought of as:
> >
> >     Generate X
> >         ↓
> >     Check X >= 0.5
> >         ↓
> >     Keep only retained values
> >         ↓
> >     Subtract 0.5
> >         ↓
> >     Plot histogram
> >
> > In mathematical form:
> >
> > $$
> > X\geq0.5
> > \quad\Rightarrow\quad
> > Y=X-0.5
> > $$
>
> > [!abstract]- MATLAB Logical Indexing
> >
> > MATLAB provides a convenient way to select values satisfying a condition.
> >
> > Suppose:
> >
> >     x = exprnd(1,50000,1);
> >
> > Then:
> >
> >     retained = x(x >= 0.5);
> >
> > selects only the values satisfying:
> >
> > $$
> > X\geq0.5
> > $$
> >
> > The transformed values can then be obtained using:
> >
> >     retained = retained - 0.5;
> >
> > This is a useful MATLAB technique for filtering data.
>
> > [!abstract]- Plotting the Final Histogram
> >
> > After transforming the retained values:
> >
> >     hist(retained)
> >
> > Appropriate labels should be added:
> >
> >     xlabel('Value')
> >     ylabel('Frequency')
> >     title('Histogram of Retained Values')
> >
> > The lab instructions require proper plot labels and titles, and the exercise asks you to upload the plots.
>
> > [!abstract]- What You Should Comment On
> >
> > For the `rand()` experiment, comment on whether the histogram appears uniform for each sample size.
> >
> > For the `exprnd()` experiment, comment on how its histogram differs from the uniform histogram.
> >
> > For the final experiment, comment on the distribution of the retained and shifted values and use appropriate statistical/distribution terminology, as requested by the exercise.
>
> > [!abstract]- Common Mistakes
> >
> > - Confusing `rand()` with `exprnd()`.
> > - Expecting the exponential histogram to be flat.
> > - Using too few samples to judge the overall distribution.
> > - Forgetting to count discarded values.
> > - Subtracting $0.5$ from values before filtering.
> > - Plotting the original exponential values instead of the retained and shifted values.
> > - Forgetting labels and titles.
>
> > [!abstract]- Takeaway
> >
> > Exercise 5 connects random-number generation with empirical distributions.
> >
> > The main sequence is:
> >
> > $$
> > \boxed{
> > \text{Generate}
> > \rightarrow
> > \text{Histogram}
> > \rightarrow
> > \text{Observe}
> > \rightarrow
> > \text{Compare}
> > }
> > $$
> >
> > For the final part:
> >
> > $$
> > \boxed{
> > X\sim\text{Exponential}
> > \rightarrow
> > X\geq0.5
> > \rightarrow
> > Y=X-0.5
> > }
> > $$



















