
> [!abstract]- Exercise 3 — Milk Vending and Storage
>
> > [!info]- Question 1 — Daily Profit with 1-Day Storage
> >
> > **Problem Statement**
> >
> > Bindu buys milk from the supplier at **₹30/L**.
> >
> > She sells milk to customers at **₹35/L**.
> >
> > If demand is greater than supply, she can sell only the available milk and the remaining demand is lost.
> >
> > If supply is greater than demand, the leftover milk is sold to a confectioner at **₹23/L**.
> >
> > Using the demand array `dem` and supply array `supp` for 730 days, calculate the **daily profit** for all 730 days.
> >
> > **Pseudocode**
> >
> > ```text
> > Load demand and supply data
> >
> > For each day:
> >     Find milk sold to customers
> >     Find leftover milk
> >     Calculate revenue from customers
> >     Calculate revenue from confectioner
> >     Calculate cost of all supplied milk
> >     Calculate daily profit
> >
> > Store the profit for each day
> > ```
> >
> > **MATLAB Code**
> >
> > ```matlab
> > % Load demand and supply data
> > demand
> > supply
> >
> > % Milk sold to customers
> > customerSales = min(dem, supp);
> >
> > % Milk left after satisfying customer demand
> > leftover = max(supp - dem, 0);
> >
> > % Calculate daily profit
> > profit = 35*customerSales + 23*leftover - 30*supp;
> > ```
> >
> > **Flowchart**
> >
> > ```mermaid
> > flowchart TD
> >     A([Start]) --> B[Load dem and supp]
> >     B --> C[Customer Sales = min dem, supp]
> >     C --> D[Leftover = max supp - dem, 0]
> >     D --> E[Customer Revenue = 35 × Customer Sales]
> >     E --> F[Confectioner Revenue = 23 × Leftover]
> >     F --> G[Cost = 30 × Supply]
> >     G --> H[Profit = Customer Revenue + Confectioner Revenue - Cost]
> >     H --> I[Store daily profit]
> >     I --> J([End])
> > ```
>
> > [!info]- Question 3 — Daily Profit with 2-Day Storage
> >
> > **Problem Statement**
> >
> > Milk can now be stored for **two days**.
> >
> > Therefore, leftover milk from yesterday can be used to satisfy today's demand.
> >
> > Old milk should be used **before** today's fresh milk.
> >
> > Any old milk that remains unsold after its storage period is sold to the confectioner at **₹23/L**.
> >
> > Using the demand array `dem` and supply array `supp`, calculate the **daily profit** for all 730 days under this new storage assumption.
> >
> > **Pseudocode**
> >
> > ```text
> > Load demand and supply data
> > Set oldMilk = 0
> >
> > For each day:
> >     Get today's fresh milk
> >
> >     Use old milk first
> >     Calculate remaining demand
> >
> >     Use today's fresh milk for remaining demand
> >     Calculate total customer sales
> >
> >     Find old milk that remains unsold
> >     Find fresh milk that remains
> >
> >     Calculate customer revenue
> >     Calculate confectioner revenue
> >     Calculate cost of today's fresh milk
> >     Calculate daily profit
> >
> >     Carry today's fresh leftover to tomorrow
> > ```
> >
> > **MATLAB Code**
> >
> > ```matlab
> > % Load data
> > demand
> > supply
> >
> > % Number of days
> > n = length(dem);
> >
> > % Array to store daily profit
> > profit2 = zeros(size(dem));
> >
> > % Milk carried from previous day
> > oldMilk = 0;
> >
> > for i = 1:n
> >
> >     % Today's fresh milk
> >     freshMilk = supp(i);
> >
> >     % First use yesterday's leftover milk
> >     oldUsed = min(dem(i), oldMilk);
> >
> >     % Demand still remaining after using old milk
> >     remainingDemand = dem(i) - oldUsed;
> >
> >     % Use today's fresh milk for the remaining demand
> >     freshUsed = min(remainingDemand, freshMilk);
> >
> >     % Total milk sold to customers
> >     customerSales = oldUsed + freshUsed;
> >
> >     % Old milk that was not sold today expires
> >     expiredMilk = oldMilk - oldUsed;
> >
> >     % Fresh milk remaining can be stored for tomorrow
> >     newInventory = freshMilk - freshUsed;
> >
> >     % Revenue
> >     customerRevenue = 35 * customerSales;
> >     confectionerRevenue = 23 * expiredMilk;
> >
> >     % Cost of today's fresh supply
> >     cost = 30 * freshMilk;
> >
> >     % Today's profit
> >     profit2(i) = customerRevenue + confectionerRevenue - cost;
> >
> >     % Carry today's leftover fresh milk to tomorrow
> >     oldMilk = newInventory;
> >
> > end
> > ```
> >
> > **Flowchart**
> >
> > ```mermaid
> > flowchart TD
> >     A([Start]) --> B[Load dem and supp]
> >     B --> C[Set oldMilk = 0]
> >     C --> D{For each day i}
> >     D --> E[Get freshMilk = supp i]
> >     E --> F[oldUsed = min demand, oldMilk]
> >     F --> G[remainingDemand = demand - oldUsed]
> >     G --> H[freshUsed = min remainingDemand, freshMilk]
> >     H --> I[Customer Sales = oldUsed + freshUsed]
> >     I --> J[Expired old milk = oldMilk - oldUsed]
> >     J --> K[New Inventory = freshMilk - freshUsed]
> >     K --> L[Calculate customer revenue]
> >     L --> M[Calculate confectioner revenue]
> >     M --> N[Calculate today's cost]
> >     N --> O[Calculate daily profit]
> >     O --> P[oldMilk = newInventory]
> >     P --> D
> >     D -->|All 730 days complete| Q([End])
> > ```

> [!abstract]- Exercise 4 — Vending Milk: Simulation
>
> > [!info]- Problem Statement
> >
> > The actual demand and supply data is not available.
> >
> > However, we know that:
> >
> > - Demand is uniformly distributed between 20 and 40 litres.
> > - Supply is uniformly distributed between 20 and 40 litres.
> > - Demand and supply are independent.
> > - Milk can be stored for only one day.
> >
> > Therefore, for each day, we generate a random demand and supply using MATLAB's `rand()` function.
> >
> > For every day, calculate the **revenue** generated by Bindu.
> >
> > Instead of storing all 2000 daily revenues, store only the **running average revenue**.
> >
> > Print the running average after every 50 days:
> >
> > ```text
> > Day = 50   Average till now = ...
> > Day = 100  Average till now = ...
> > Day = 150  Average till now = ...
> > ...
> > Day = 2000 Average till now = ...
> > ```
> >
> > Finally, plot:
> >
> > ```text
> > Running Average Revenue vs Day
> > ```
>
> > [!example]- Pseudocode
> >
> > ```text
> > Set average = 0
> >
> > For day = 1 to 2000
> >
> >     Generate random demand between 20 and 40
> >     Generate random supply between 20 and 40
> >
> >     Find milk sold to customers
> >     Find leftover milk
> >
> >     Calculate today's revenue
> >
> >     Update running average revenue
> >
> >     If day is divisible by 50
> >         Print day and current average
> >     End
> >
> > End
> >
> > Plot running average against day
> > ```
>
> > [!example]- Important MATLAB Idea — `rand()`
> >
> > `rand()` generates a random number uniformly between `0` and `1`.
> >
> > ```matlab
> > r = rand();
> > ```
> >
> > gives:
> >
> > ```text
> > 0 ≤ r < 1
> > ```
> >
> > To convert this into a uniform random number between `20` and `40`:
> >
> > ```matlab
> > x = 20 + (40-20)*rand();
> > ```
> >
> > Therefore:
> >
> > ```matlab
> > demand = 20 + 20*rand();
> > supply = 20 + 20*rand();
> > ```
> >
> > These two calls generate independent random values.
>
> > [!example]- MATLAB Code
> >
> > ```matlab
> > % Number of days
> > n = 2000;
> >
> > % Array to store running averages
> > averageRevenue = zeros(1,n);
> >
> > % Running total revenue
> > totalRevenue = 0;
> >
> > for day = 1:n
> >
> >     % Generate demand and supply
> >     demand = 20 + 20*rand();
> >     supply = 20 + 20*rand();
> >
> >     % Milk sold to customers
> >     customerSales = min(demand, supply);
> >
> >     % Leftover milk
> >     leftover = max(supply - demand, 0);
> >
> >     % Today's revenue
> >     revenue = 35*customerSales + 23*leftover;
> >
> >     % Add today's revenue to total revenue
> >     totalRevenue = totalRevenue + revenue;
> >
> >     % Running average revenue
> >     averageRevenue(day) = totalRevenue/day;
> >
> >     % Print average every 50 days
> >     if mod(day,50) == 0
> >         fprintf('Day = %d Average till now = %.2f\n', ...
> >                 day, averageRevenue(day));
> >     end
> >
> > end
> >
> > % Plot running average
> > figure;
> > plot(1:n, averageRevenue, 'LineWidth', 1.5);
> > xlabel('Day');
> > ylabel('Average Revenue');
> > title('Running Average Revenue vs Day');
> > grid on;
> > ```
>
> > [!abstract]- Running Average
> >
> > We don't need to store all the revenues.
> >
> > Suppose the revenues are:
> >
> > ```text
> > Day 1 → ₹1000
> > Day 2 → ₹1200
> > Day 3 → ₹900
> > ```
> >
> > The average after Day 3 is:
> >
> > $$\text{Average} =
> > \frac{1000+1200+900}{3}
> > = 1033.33$$
> >
> > Instead of storing every revenue, maintain:
> >
> > ```matlab
> > totalRevenue
> > ```
> >
> > and calculate:
> >
> > ```matlab
> > averageRevenue(day) = totalRevenue/day;
> > ```
> >
> > So:
> >
> > ```text
> > Previous total
> >       +
> > Today's revenue
> >       ↓
> > New total
> >       ↓
> > Divide by number of days
> >       ↓
> > Running average
> > ```
>
> > [!abstract]- Flowchart
> >
> > ```mermaid
> > flowchart TD
> >     A([Start]) --> B[Set n = 2000]
> >     B --> C[Set totalRevenue = 0]
> >     C --> D[Start day = 1]
> >     D --> E[Generate demand = 20 + 20×rand]
> >     E --> F[Generate supply = 20 + 20×rand]
> >     F --> G[Customer Sales = min demand, supply]
> >     G --> H[Leftover = max supply - demand, 0]
> >     H --> I[Revenue = 35×Sales + 23×Leftover]
> >     I --> J[totalRevenue = totalRevenue + Revenue]
> >     J --> K[Average = totalRevenue / day]
> >     K --> L{day divisible by 50?}
> >     L -->|Yes| M[Print Day and Average]
> >     L -->|No| N{day = 2000?}
> >     M --> N
> >     N -->|No| O[day = day + 1]
> >     O --> E
> >     N -->|Yes| P[Plot running average]
> >     P --> Q([End])
> > ```
>
> > [!note]- Important Observation
> >
> > The running average will generally fluctuate a lot during the first few days because we have very few observations.
> >
> > As the number of simulated days increases, the running average should generally become more stable.
> >
> > ```text
> > Few observations
> >       ↓
> > Large fluctuations
> >
> > More observations
> >       ↓
> > Smaller fluctuations
> >       ↓
> > Running average stabilizes
> > ```
>>
>>---
>>
> > The exact values will be different each time you run the program because `rand()` generates different random realizations.
>>
>>**One important point:** the question asks for **average revenue**, not average profit. Therefore, unlike Exercise 3, the ₹30/L purchase cost is **not subtracted** in this exercise.

> [!abstract]- Exercise 5 — Random Sample
>
> > [!info]- Problem Statement
> >
> > MATLAB's `rand()` function generates random numbers between `0` and `1`.
> >
> > We want to investigate whether these generated numbers actually behave like samples from a **Uniform(0,1)** distribution.
> >
> > We will:
> >
> > - Generate random samples using `rand()`.
> > - Plot their histograms.
> > - Repeat this for different sample sizes.
> > - Compare the observed histogram with what we expect from a uniform distribution.
> >
> > We will then perform a similar experiment using MATLAB's `exprnd()` function, which generates samples from an **exponential distribution**.
>
> > [!abstract]- Part (a) — Testing `rand()`
> >
> > **Task:**
> >
> > Write a MATLAB function:
> >
> > ```matlab
> > testrand(n)
> > ```
> >
> > which:
> >
> > - Takes a positive integer `n`.
> > - Calls `rand()` exactly `n` times.
> > - Stores the generated values.
> > - Plots their histogram.
> >
> > Generate plots for:
> >
> > ```text
> > n = 10
> > n = 1000
> > n = 1000000
> > ```
> >
> > ### Pseudocode
> >
> > ```text
> > Function testrand(n)
> >
> >     Create an empty array
> >
> >     Repeat n times:
> >         Generate a random number using rand()
> >         Store the number
> >
> >     Plot histogram of the generated numbers
> >     Add title, x-label and y-label
> >
> > End
> > ```
>
> > [!example]- MATLAB Code
> >
> > ```matlab
> > function testrand(n)
> >
> >     % Array to store random values
> >     x = zeros(1,n);
> >
> >     % Generate n random values
> >     for i = 1:n
> >         x(i) = rand();
> >     end
> >
> >     % Plot histogram
> >     histogram(x);
> >
> >     xlabel('Random Value');
> >     ylabel('Frequency');
> >     title(['Histogram of ', num2str(n), ' rand() samples']);
> >     legend('rand() samples');
> >
> > end
> > ```
>
> > [!example]- Running the Function
> >
> > ```matlab
> > testrand(10)
> > ```
> >
> > ```matlab
> > testrand(1000)
> > ```
> >
> > ```matlab
> > testrand(1000000)
> > ```
>
> > [!note]- Expected Observation
> >
> > The theoretical distribution is:
> >
> > $$X \sim U(0,1)$$
> >
> > Therefore, every interval of the same width should have approximately the same probability.
> >
> > For example:
> >
> > ```text
> > 0.0 – 0.1  → approximately 10%
> > 0.1 – 0.2  → approximately 10%
> > 0.2 – 0.3  → approximately 10%
> > ...
> > 0.9 – 1.0  → approximately 10%
> > ```
> >
> > For `n = 10`, the histogram can look very irregular because there are very few observations.
> >
> > For `n = 1000`, the histogram should look much more approximately flat.
> >
> > For `n = 1000000`, it should look very close to a flat/uniform shape.
> >
> > This is an example of the **Law of Large Numbers**: as the number of observations increases, the empirical distribution tends to resemble the theoretical distribution more closely.
>
>---
>
> > [!abstract]- Part (b) — Testing `exprnd()`
>>
> > `exprnd()` generates random values from an **exponential distribution**.
> >
> > Unlike the uniform distribution, an exponential distribution is not flat.
> >
> > It has:
> >
> > - Many observations close to `0`.
> > - Fewer observations as the value increases.
> > - A long right tail.
> >
> > ### Pseudocode
> >
> > ```text
> > Generate n exponential random values
> >
> > Plot their histogram
> >
> > Add title, labels and legend
> >
> > Repeat for different values of n
> > ```
>
> > [!example]- MATLAB Code
> >
> > ```matlab
> > function testexprnd(n)
> >
> >     % Generate n exponential random values
> >     x = exprnd(1,1,n);  % exprnd(mean, rows, columns)
> >
> >     % Plot histogram
> >     histogram(x);
> >
> >     xlabel('Random Value');
> >     ylabel('Frequency');
> >     title(['Histogram of ', num2str(n), ' exprnd() samples']);
> >     legend('exprnd() samples');
> >
> > end
> > ```
>>
> > Run:
> >
> > ```matlab
> > testexprnd(10)
> > testexprnd(1000)
> > testexprnd(1000000)
> > ```
>
> > [!note]- Difference Between `rand()` and `exprnd()`
> >
> > `rand()` generates values from a **uniform distribution**, so its histogram should become approximately flat as `n` increases.
> >
> > `exprnd()` generates values from an **exponential distribution**, so its histogram should have a high frequency near zero and decrease as the value increases, producing a right-skewed shape.
>
>---
>
> > [!abstract]- Part (c) — Discard Values Below 0.5
>>
> > Generate `n = 50000` exponential random values.
> >
> > Discard every value smaller than `0.5`.
> >
> > For every remaining value, subtract `0.5`.
> >
> > Then:
> >
> > - Calculate the fraction of values discarded.
> > - Plot the histogram of the remaining values after subtracting `0.5`.
>
> > [!example]- Pseudocode
> >
> > ```text
> > Set n = 50000
> >
> > Generate n exponential random values
> >
> > Find values greater than or equal to 0.5
> >
> > Count how many values were discarded
> >
> > Calculate:
> >     fraction discarded = discarded / n
> >
> > Keep only values >= 0.5
> >
> > Subtract 0.5 from every considered value
> >
> > Plot histogram of the resulting values
> > ```
>
> > [!example]- MATLAB Code
> >
> > ```matlab
> > % Number of samples
> > n = 50000;
> >
> > % Generate exponential random values
> > x = exprnd(1,1,n);
> >
> > % Select values greater than or equal to 0.5
> > considered = x >= 0.5;
> >
> > % Number of discarded values
> > discarded = sum(~considered);
> >
> > % Fraction of values discarded
> > fractionDiscarded = discarded / n;
> >
> > % Display result
> > fprintf('Fraction discarded = %.4f\n', fractionDiscarded);
> >
> > % Keep only values >= 0.5
> > xConsidered = x(considered);
> >
> > % Subtract 0.5
> > xConsidered = xConsidered - 0.5;
> >
> > % Plot histogram
> > figure;
> > histogram(xConsidered);
> >
> > xlabel('Value after subtracting 0.5');
> > ylabel('Frequency');
> > title('Exponential Samples after Discarding Values < 0.5');
> > legend('Considered values');
> > ```
>
> > [!note]- Important MATLAB Idea
> >
> > ```matlab
> > considered = x >= 0.5;
> > ```
> >
> > creates a logical array:
> >
> > ```text
> > x >= 0.5
> > ```
> >
> > gives `true` for values we keep and `false` for values we discard.
> >
> > Then:
> >
> > ```matlab
> > x(considered)
> > ```
> >
> > extracts only the values that satisfy the condition.
>
> > [!abstract]- Flowchart — Part (a)
> >
> > ```mermaid
> > flowchart TD
> >     A([Start]) --> B[Input n]
> >     B --> C[Initialize array]
> >     C --> D[Generate rand value]
> >     D --> E[Store value]
> >     E --> F{n values generated?}
> >     F -->|No| D
> >     F -->|Yes| G[Plot histogram]
> >     G --> H[Add labels and title]
> >     H --> I([End])
> > ```
>
> > [!abstract]- Flowchart — Part (c)
> >
> > ```mermaid
> > flowchart TD
> >     A([Start]) --> B[Set n = 50000]
> >     B --> C[Generate exponential samples]
> >     C --> D[Check x >= 0.5]
> >     D --> E[Count discarded values]
> >     E --> F[Calculate fraction discarded]
> >     F --> G[Keep values >= 0.5]
> >     G --> H[Subtract 0.5]
> >     H --> I[Plot histogram]
> >     I --> J([End])
> > ```

---

> [!abstract]- Exercise 1 — Exponential Random Variables
>
> > [!info]- Problem Statement
> >
> > Generate a random sample of size $n$ of random variables
> >
> > $$
> > Y_k = \min\{X_{k,1},X_{k,2}\}, \qquad k\leq n
> > $$
> >
> > where
> >
> > $$
> > X_{k,1}\sim\operatorname{Exp}(\lambda_1)
> > $$
> >
> > and
> >
> > $$
> > X_{k,2}\sim\operatorname{Exp}(\lambda_2)
> > $$
> >
> > and all random variables are independent.
> >
> > Write a program that takes $(n,\lambda_1,\lambda_2)$ as inputs, generates the sample $Y$, and plots its histogram.
> >
> > Use $n=50000$ for the following two cases:
> >
> > - Case 1: $\lambda_1=1,\lambda_2=1$
> > - Case 2: $\lambda_1=1,\lambda_2=2$
> >
> > **Pseudocode**
> >
> > ```text
> > Input n, lambda1, lambda2
> >
> > Generate n samples from Exp(lambda1)
> > Generate n samples from Exp(lambda2)
> >
> > For each k:
> >     Y(k) = minimum of X1(k) and X2(k)
> >
> > Plot histogram of Y
> > ```
> >
> > **MATLAB Code**
> >
> > ```matlab
> > function generateY(n, lambda1, lambda2)
> >
> >     % Generate exponential random variables
> >     X1 = exprnd(1/lambda1, 1, n);
> >     X2 = exprnd(1/lambda2, 1, n);
> >
> >     % Take the minimum for each sample
> >     Y = min(X1, X2);
> >
> >     % Plot histogram
> >     histogram(Y);
> >
> >     xlabel('Y');
> >     ylabel('Frequency');
> >     title(['Histogram of Y, \lambda_1 = ', num2str(lambda1), ...
> >            ', \lambda_2 = ', num2str(lambda2)]);
> >     grid on;
> >
> > end
> > ```
> >
> > **Run the program**
> >
> > ```matlab
> > n = 50000;
> >
> > % Case 1
> > generateY(n, 1, 1);
> >
> > % Case 2
> > generateY(n, 1, 2);
> > ```
> >
> > **Flowchart**
> >
> > ```mermaid
> > flowchart TD
> >     A([Start]) --> B[Input n, lambda1, lambda2]
> >     B --> C[Generate X1 ~ Exp lambda1]
> >     C --> D[Generate X2 ~ Exp lambda2]
> >     D --> E[Y = min X1, X2]
> >     E --> F[Plot histogram of Y]
> >     F --> G([End])
> > ```
>
> > [!example]- Theoretical Result
> >
> > The minimum of two independent exponential random variables is also exponential.
> >
> > $$
> > Y=\min(X_1,X_2)
> > $$
> >
> > has parameter
> >
> > $$
> > \lambda_Y=\lambda_1+\lambda_2
> > $$
> >
> > Therefore:
> >
> > **Case 1**
> >
> > $$
> > \lambda_1=1,\quad\lambda_2=1
> > $$
> >
> > so
> >
> > $$
> > Y\sim\operatorname{Exp}(2)
> > $$
> >
> > **Case 2**
> >
> > $$
> > \lambda_1=1,\quad\lambda_2=2
> > $$
> >
> > so
> >
> > $$
> > Y\sim\operatorname{Exp}(3)
> > $$
> >
> > Since the second case has a larger rate, its samples tend to be **smaller**, so its histogram should decay more rapidly toward zero.
>
> > [!example]- Comment on the Plots
> >
> > For $\lambda_1=\lambda_2=1$, the histogram should have an exponential shape with parameter $2$.
> >
> > For $\lambda_1=1,\lambda_2=2$, the histogram should decay faster because the resulting rate is $3$.
> >
> > In both cases, most observations are close to $0$, and the frequency decreases as $Y$ increases. With $n=50000$, the histograms should closely resemble the theoretical exponential distributions.

> [!abstract]- Exercise 2 — Exponential Random Variables
>
> > [!info]- Problem Statement
> >
> > Generate the random sequence recursively using independent exponential random variables $X_k$ with parameter $\lambda$:
> >
> > $$
> > Y_1=X_1
> > $$
> >
> > $$
> > Y_2=Y_1+X_2
> > $$
> >
> > and in general,
> >
> > $$
> > Y_k=Y_{k-1}+X_k
> > $$
> >
> > Define
> >
> > $$
> > Z_k=\frac{Y_k}{k}.
> > $$
> >
> > Write a program that takes $(n,\lambda)$ as inputs, generates the sequence, and plots the histogram of $Z_k$ for
> >
> > $$
> > k=n-2000,\ldots,n.
> > $$
> >
> > Use the following cases:
> >
> > - Case 1: $\lambda=2,\ n=2024$
> > - Case 2: $\lambda=4,\ n=30000$
> >
> > **Pseudocode**
> >
> > ```text
> > Input n and lambda
> >
> > Generate X1 ~ Exponential(lambda)
> >
> > Set Y1 = X1
> >
> > For k = 2 to n:
> >     Generate Xk ~ Exponential(lambda)
> >     Yk = Y(k-1) + Xk
> >
> > For k = 1 to n:
> >     Zk = Yk / k
> >
> > Select Z values from k = n-2000 to n
> >
> > Plot histogram of selected Z values
> > ```
>
> > [!example]- MATLAB Code
> >
> > ```matlab
> > function generateZ(n, lambda)
> >
> >     % Generate exponential random variables
> >     X = exprnd(1/lambda, 1, n);
> >
> >     % Array for Y
> >     Y = zeros(1, n);
> >
> >     % First value
> >     Y(1) = X(1);
> >
> >     % Generate Y recursively
> >     for k = 2:n
> >         Y(k) = Y(k-1) + X(k);
> >     end
> >
> >     % Calculate Zk = Yk / k
> >     k = 1:n;
> >     Z = Y ./ k;
> >
> >     % Select the last 2001 values
> >     start = n - 2000;
> >     Zplot = Z(start:n);
> >
> >     % Plot histogram
> >     histogram(Zplot);
> >
> >     xlabel('Z_k');
> >     ylabel('Frequency');
> >     title(['Histogram of Z_k, \lambda = ', num2str(lambda), ...
> >            ', n = ', num2str(n)]);
> >     grid on;
> >
> > end
> > ```
>
> > [!example]- Run the Two Cases
> >
> > ```matlab
> > % Case 1
> > figure(1);
> > generateZ(2024, 2);
> >
> > % Case 2
> > figure(2);
> > generateZ(30000, 4);
> > ```
>
> > [!abstract]- Flowchart
> >
> > ```mermaid
> > flowchart TD
> >     A([Start]) --> B[Input n and lambda]
> >     B --> C[Generate X1,...,Xn ~ Exp lambda]
> >     C --> D[Set Y1 = X1]
> >     D --> E{For k = 2 to n}
> >     E --> F[Yk = Yk-1 + Xk]
> >     F --> E
> >     E -->|Complete| G[Calculate Zk = Yk / k]
> >     G --> H[Select k = n-2000 to n]
> >     H --> I[Plot histogram of Zk]
> >     I --> J([End])
> > ```
>
> > [!info]- Question 2 — Comment on the Plots
> >
> > Since
> >
> > $$
> > X_k\sim\operatorname{Exp}(\lambda)
> > $$
> >
> > we have
> >
> > $$
> > E[X_k]=\frac{1}{\lambda}.
> > $$
> >
> > Now
> >
> > $$
> > Y_k=X_1+X_2+\cdots+X_k.
> > $$
> >
> > Therefore,
> >
> > $$
> > Z_k=\frac{Y_k}{k}
> > =\frac{X_1+\cdots+X_k}{k}.
> > $$
> >
> > So $Z_k$ is the **sample average** of the exponential random variables.
> >
> > By the Law of Large Numbers,
> >
> > $$
> > Z_k\rightarrow E[X_k]=\frac{1}{\lambda}.
> > $$
> >
> > Therefore:
> >
> > **Case 1: $\lambda=2$**
> >
> > $$
> > \frac{1}{\lambda}=\frac12=0.5
> > $$
> >
> > The histogram should be concentrated around $0.5$.
> >
> > **Case 2: $\lambda=4$**
> >
> > $$
> > \frac{1}{\lambda}=\frac14=0.25
> > $$
> >
> > The histogram should be concentrated around $0.25$.
> >
> > The second plot should be narrower because the larger sample size $n=30000$ makes $Z_k$ more stable around its expected value.
>
> > [!example]- Question 3 — Plot $Z_k$ Versus $k$
> >
> > Generate five independent sequences and plot all five curves on the same figure.
> >
> > ```matlab
> > figure(2);
> > hold on;
> >
> > n = 400;
> > lambda = 2;
> >
> > for j = 1:5
> >
> >     % Generate exponential random variables
> >     X = exprnd(1/lambda, 1, n);
> >
> >     % Generate Y recursively
> >     Y = zeros(1, n);
> >     Y(1) = X(1);
> >
> >     for k = 2:n
> >         Y(k) = Y(k-1) + X(k);
> >     end
> >
> >     % Calculate Zk
> >     k = 1:n;
> >     Z = Y ./ k;
> >
> >     % Plot Zk against k
> >     plot(k, Z, 'LineWidth', 1.2);
> >
> > end
> >
> > xlabel('k');
> > ylabel('Z_k');
> > title('Z_k versus k for 5 Independent Sequences');
> > legend('Sequence 1', 'Sequence 2', 'Sequence 3', ...
> >        'Sequence 4', 'Sequence 5');
> > grid on;
> > hold off;
> > ```
>
> > [!info]- Observation for Question 3
> >
> > Each curve starts with considerable variation because only a few exponential random variables contribute to the average.
> >
> > As $k$ increases,
> >
> > $$
> > Z_k=\frac{X_1+\cdots+X_k}{k}
> > $$
> >
> > becomes more stable.
> >
> > For $\lambda=2$, all five curves should gradually move toward
> >
> > $$
> > \frac{1}{\lambda}=0.5.
> > $$
> >
> > This illustrates the **Law of Large Numbers**: the average of many independent observations approaches their expected value.

> [!abstract]- Exercise 3 — Exponential Random Variables Continued
>
> > [!info]- Problem Statement
> >
> > Take $(T,\lambda,n)$ as inputs.
> >
> > Generate exponential random variables
> >
> > $$
> > X_i\sim\operatorname{Exp}(\lambda)
> > $$
> >
> > and recursively generate arrival times:
> >
> > $$
> > Y_k=\sum_{i=1}^{k}X_i
> > $$
> >
> > or equivalently,
> >
> > $$
> > Y_k=Y_{k-1}+X_k.
> > $$
> >
> > The number of arrivals before time $T$ is
> >
> > $$
> > Z_1=\inf\{i:Y_i\geq T\}-1.
> > $$
> >
> > In simple terms:
> >
> > - $X_i$ = time gap between two consecutive arrivals
> > - $Y_i$ = time at which the $i$-th arrival occurs
> > - $T$ = observation time
> > - $Z$ = number of arrivals that occur **before $T$**
> >
> > Repeat the same procedure $n$ times using fresh independent exponential random variables each time to generate the random sample
> >
> > $$
> > \{Z_1,Z_2,\ldots,Z_n\}.
> > $$
> >
> > **Pseudocode**
> >
> > ```text
> > Input T, lambda, n
> >
> > For j = 1 to n:
> >     Set Y = 0
> >     Set count = 0
> >
> >     While Y < T:
> >         Generate X ~ Exponential(lambda)
> >         Y = Y + X
> >
> >         If Y < T:
> >             count = count + 1
> >
> >     Z(j) = count
> >
> > Plot histogram of Z
> > Calculate mean of Z
> > ```
>
> > [!example]- MATLAB Code
> >
> > ```matlab
> > function [Z, sampleMean] = generateZ(T, lambda, n)
> >
> >     % Array to store the random sample
> >     Z = zeros(1, n);
> >
> >     % Repeat the experiment n times
> >     for j = 1:n
> >
> >         % Start at time 0
> >         Y = 0;
> >
> >         % Number of arrivals before T
> >         count = 0;
> >
> >         % Generate arrivals until time reaches/exceeds T
> >         while Y < T
> >
> >             % Generate exponential inter-arrival time
> >             X = exprnd(1/lambda);
> >
> >             % Update arrival time
> >             Y = Y + X;
> >
> >             % Count arrival only if it occurs before T
> >             if Y < T
> >                 count = count + 1;
> >             end
> >
> >         end
> >
> >         % Store number of arrivals
> >         Z(j) = count;
> >
> >     end
> >
> >     % Calculate sample mean
> >     sampleMean = mean(Z);
> >
> >     % Display mean
> >     fprintf('Sample mean = %.4f\n', sampleMean);
> >
> >     % Plot histogram
> >     figure;
> >     histogram(Z);
> >
> >     xlabel('Number of arrivals');
> >     ylabel('Frequency');
> >     title(['Histogram of Z, T = ', num2str(T), ...
> >            ', \lambda = ', num2str(lambda), ...
> >            ', n = ', num2str(n)]);
> >     grid on;
> >
> > end
> > ```
>
> > [!example]- Example Run
> >
> > For example, if
> >
> > ```matlab
> > T = 10;
> > lambda = 2;
> > n = 50000;
> >
> > [Z, sampleMean] = generateZ(T, lambda, n);
> > ```
> >
> > the expected number of arrivals is
> >
> > $$
> > E[Z]=\lambda T.
> > $$
> >
> > Therefore,
> >
> > $$
> > E[Z]=2(10)=20.
> > $$
> >
> > The simulated sample mean should be close to $20$ when $n$ is large.
>
> > [!abstract]- Flowchart
> >
> > ```mermaid
> > flowchart TD
> >     A([Start]) --> B[Input T, lambda, n]
> >     B --> C[Create array Z]
> >     C --> D[Set j = 1]
> >     D --> E[Set Y = 0 and count = 0]
> >     E --> F[Generate X ~ Exp lambda]
> >     F --> G[Y = Y + X]
> >     G --> H{Is Y < T?}
> >     H -->|Yes| I[count = count + 1]
> >     I --> F
> >     H -->|No| J[Store Z j = count]
> >     J --> K{j < n?}
> >     K -->|Yes| L[j = j + 1]
> >     L --> E
> >     K -->|No| M[Calculate mean of Z]
> >     M --> N[Plot histogram]
> >     N --> O([End])
> > ```
>
> > [!info]- Algorithm for Report
> >
> > ```text
> > Algorithm: Generate Number of Arrivals Before T
> >
> > Input: T, lambda, n
> > Output: Random sample Z of size n
> >
> > For j = 1 to n:
> >
> >     Y = 0
> >     count = 0
> >
> >     While Y < T:
> >         Generate X from Exponential(lambda)
> >         Y = Y + X
> >
> >         If Y < T:
> >             count = count + 1
> >         End If
> >     End While
> >
> >     Z(j) = count
> >
> > End For
> >
> > Return Z
> > ```
>
> > [!example]- Question 3(c) — Comment on the Results
> >
> > The random variable $Z$ represents the **number of arrivals before time $T$**.
> >
> > Since the inter-arrival times are independent exponential random variables with rate $\lambda$, the arrivals form a Poisson process.
> >
> > Therefore,
> >
> > $$
> > Z\sim\operatorname{Poisson}(\lambda T).
> > $$
> >
> > Hence,
> >
> > $$
> > E[Z]=\lambda T
> > $$
> >
> > and
> >
> > $$
> > \operatorname{Var}(Z)=\lambda T.
> > $$
> >
> > The histogram should therefore have a shape similar to a **Poisson distribution** centered approximately around $\lambda T$.
> >
> > For a sufficiently large $n$, the simulated mean should be close to the theoretical mean:
> >
> > $$
> > \boxed{E[Z]=\lambda T}
> > $$
> >
> > Increasing $n$ gives a more reliable estimate of the theoretical distribution and mean.

> [!abstract]- Exercise 4 — Jobs Completed Before One Poisson Arrival
>
> > [!info]- Problem Statement
> >
> > A bank has $x=100$ jobs waiting to be served.
> >
> > Each job requires an independent exponentially distributed completion time:
> >
> > $$
> > X_i\sim\operatorname{Exp}(\mu)
> > $$
> >
> > The next job arrival occurs after an independent exponential amount of time:
> >
> > $$
> > A\sim\operatorname{Exp}(\lambda)
> > $$
> >
> > We need to find the number of jobs that are completed **before the next arrival**.
> >
> > Since there are only $x$ jobs waiting,
> >
> > $$
> > 0\leq Z\leq x.
> > $$
> >
> > The program `JobsDoneInOneArrival` should take $(\lambda,\mu,x)$ as inputs and return the number of completed jobs.
> >
> > The program is then called **10000 times**, using fresh independent random variables on every call.
>
> > [!example]- Pseudocode
> >
> > ```text
> > Input lambda, mu, x
> >
> > Generate the random arrival time A ~ Exponential(lambda)
> >
> > Set currentTime = 0
> > Set jobsDone = 0
> >
> > For each of the x jobs:
> >     Generate completion time X ~ Exponential(mu)
> >     currentTime = currentTime + X
> >
> >     If currentTime < A:
> >         jobsDone = jobsDone + 1
> >     Else:
> >         Stop
> >
> > Return jobsDone
> > ```
>
> > [!example]- MATLAB Function
> >
> > ```matlab
> > function jobsDone = JobsDoneInOneArrival(lambda, mu, x)
> >
> >     % Generate time until next arrival
> >     arrivalTime = exprnd(1/lambda);
> >
> >     % Current time
> >     currentTime = 0;
> >
> >     % Number of completed jobs
> >     jobsDone = 0;
> >
> >     % Process jobs one by one
> >     for i = 1:x
> >
> >         % Generate completion time of current job
> >         completionTime = exprnd(1/mu);
> >
> >         % Update current time
> >         currentTime = currentTime + completionTime;
> >
> >         % Check whether job finishes before next arrival
> >         if currentTime < arrivalTime
> >             jobsDone = jobsDone + 1;
> >         else
> >             break;
> >         end
> >
> >     end
> >
> > end
> > ```
>
> > [!example]- Generate 10000 Samples
> >
> > ```matlab
> > lambda = 1;
> > mu = 0.1;
> > x = 100;
> >
> > n = 10000;
> > jobs = zeros(1,n);
> >
> > for i = 1:n
> >     jobs(i) = JobsDoneInOneArrival(lambda, mu, x);
> > end
> >
> > % Mean number of jobs completed
> > meanJobs = mean(jobs);
> >
> > fprintf('Mean number of jobs completed = %.4f\n', meanJobs);
> >
> > % Plot histogram
> > figure;
> > histogram(jobs);
> >
> > xlabel('Number of Jobs Completed');
> > ylabel('Frequency');
> > title('Jobs Completed Before One Arrival');
> > grid on;
> > ```
>
> > [!example]- Case 1 — $\lambda=1,\ \mu=0.1$
> >
> > ```matlab
> > lambda = 1;
> > mu = 0.1;
> > x = 100;
> >
> > n = 10000;
> > jobs = zeros(1,n);
> >
> > for i = 1:n
> >     jobs(i) = JobsDoneInOneArrival(lambda, mu, x);
> > end
> >
> > fprintf('Mean jobs completed = %.4f\n', mean(jobs));
> >
> > figure;
> > histogram(jobs);
> > xlabel('Number of Jobs Completed');
> > ylabel('Frequency');
> > title('\lambda = 1, \mu = 0.1');
> > grid on;
> > ```
>>
> > Here:
> >
> > $$
> > E[\text{arrival time}]=\frac{1}{\lambda}=1
> > $$
> >
> > while
> >
> > $$
> > E[\text{job completion time}]
> > =\frac{1}{\mu}=10.
> > $$
> >
> > So jobs take relatively long to complete, while the next arrival occurs relatively quickly.
> >
> > Therefore, **usually only a small number of jobs will be completed** before the next arrival.
>
> > [!example]- Case 2 — $\lambda=1,\ \mu=30$
> >
> > ```matlab
> > lambda = 1;
> > mu = 30;
> > x = 100;
> >
> > n = 10000;
> > jobs = zeros(1,n);
> >
> > for i = 1:n
> >     jobs(i) = JobsDoneInOneArrival(lambda, mu, x);
> > end
> >
> > fprintf('Mean jobs completed = %.4f\n', mean(jobs));
> >
> > figure;
> > histogram(jobs);
> > xlabel('Number of Jobs Completed');
> > ylabel('Frequency');
> > title('\lambda = 1, \mu = 30');
> > grid on;
> > ```
>>
> > Here:
> >
> > $$
> > E[\text{arrival time}]=\frac{1}{1}=1
> > $$
> >
> > while
> >
> > $$
> > E[\text{job completion time}]
> > =\frac{1}{30}\approx0.0333.
> > $$
> >
> > Therefore jobs are completed much faster than the next arrival occurs.
> >
> > Hence, **many jobs can be completed before the next arrival**.
>
> > [!abstract]- Flowchart
> >
> > ```mermaid
> > flowchart TD
> >     A([Start]) --> B[Input lambda, mu, x]
> >     B --> C[Generate arrival time A ~ Exp lambda]
> >     C --> D[Set currentTime = 0]
> >     D --> E[Set jobsDone = 0]
> >     E --> F{More jobs available?}
> >     F -->|Yes| G[Generate completion time X ~ Exp mu]
> >     G --> H[currentTime = currentTime + X]
> >     H --> I{currentTime < arrivalTime?}
> >     I -->|Yes| J[jobsDone = jobsDone + 1]
> >     J --> F
> >     I -->|No| K[Stop]
> >     F -->|No| K
> >     K --> L[Return jobsDone]
> >     L --> M([End])
> > ```
>
> > [!info]- Question 4 — Comparison
> >
> > The key difference is the relationship between the two rates.
> >
> > For $\lambda=1,\mu=0.1$:
> >
> > $$
> > \frac{1}{\lambda}=1,\qquad
> > \frac{1}{\mu}=10
> > $$
> >
> > The average job takes much longer than the average time until the next arrival, so relatively few jobs are completed.
> >
> > For $\lambda=1,\mu=30$:
> >
> > $$
> > \frac{1}{\lambda}=1,\qquad
> > \frac{1}{\mu}\approx0.0333
> > $$
> >
> > The average job takes much less time than the average time until the next arrival, so many more jobs are completed.
> >
> > Therefore:
> >
> > $$
> > \boxed{\text{larger }\mu\Rightarrow\text{faster job completion}}
> > $$
> >
> > and, with $\lambda$ fixed,
> >
> > $$
> > \boxed{\text{more jobs completed before the next arrival}}
> > $$

---

> [!abstract]- Exercise 1 — Jobs in System After 2 More Poisson Arrivals
>
> > [!info]- Problem Statement
> >
> > Consider the same setting as the previous exercise.
> >
> > Let
> >
> > $$
> > X_0=x
> > $$
> >
> > represent the initial number of jobs in the system.
> >
> > The function `JobsDoneInOneArrival(lambda, mu, X0)` returns $J_1$, the number of jobs completed before the first new arrival.
> >
> > After the first arrival:
> >
> > $$
> > X_1=(X_0-J_1)+1
> > $$
> >
> > where:
> >
> > - $X_0$ = jobs initially in the system
> > - $J_1$ = jobs completed before first arrival
> > - $+1$ = the new arriving job
> >
> > Now use $X_1$ as the input to `JobsDoneInOneArrival` again.
> >
> > This gives $J_2$, the number of jobs completed before the second arrival.
> >
> > Therefore:
> >
> > $$
> > X_2=(X_1-J_2)+1
> > $$
> >
> > The function `JobsDoneInTwoArrivals(lambda, mu, X0)` should return $X_2$.
>
> > [!example]- Pseudocode
> >
> > ```text
> > Input lambda, mu, X0
> >
> > Call JobsDoneInOneArrival(lambda, mu, X0)
> >     Get J1
> >
> > Calculate:
> >     X1 = (X0 - J1) + 1
> >
> > Call JobsDoneInOneArrival(lambda, mu, X1)
> >     Get J2
> >
> > Calculate:
> >     X2 = (X1 - J2) + 1
> >
> > Return X2
> > ```
>
> > [!example]- MATLAB Function
> >
> > ```matlab
> > function X2 = JobsDoneInTwoArrivals(lambda, mu, X0)
> >
> >     % Number of jobs completed before first arrival
> >     J1 = JobsDoneInOneArrival(lambda, mu, X0);
> >
> >     % Number of jobs immediately after first arrival
> >     X1 = (X0 - J1) + 1;
> >
> >     % Number of jobs completed before second arrival
> >     J2 = JobsDoneInOneArrival(lambda, mu, X1);
> >
> >     % Number of jobs immediately after second arrival
> >     X2 = (X1 - J2) + 1;
> >
> > end
> > ```
>
> > [!info]- Important Independence
> >
> > Every call to `JobsDoneInOneArrival` must generate **fresh independent random variables**.
> >
> > Therefore:
> >
> > ```matlab
> > J1 = JobsDoneInOneArrival(lambda, mu, X0);
> > J2 = JobsDoneInOneArrival(lambda, mu, X1);
> > ```
> >
> > uses a new independent arrival time and new independent job completion times for the second call.
>
> > [!example]- Question (i) — $\lambda=1,\ \mu=10,\ X_0=100$
> >
> > Generate 10000 independent copies of $X_2$.
> >
> > ```matlab
> > lambda = 1;
> > mu = 10;
> > X0 = 100;
> >
> > n = 10000;
> > X2 = zeros(1,n);
> >
> > for i = 1:n
> >     X2(i) = JobsDoneInTwoArrivals(lambda, mu, X0);
> > end
> >
> > % Mean
> > fprintf('Mean X2 = %.4f\n', mean(X2));
> >
> > % Histogram
> > figure;
> > histogram(X2);
> >
> > xlabel('Number of Jobs in System');
> > ylabel('Frequency');
> > title('X_2: \lambda = 1, \mu = 10, X_0 = 100');
> > grid on;
> > ```
>
> > [!example]- Question (ii) — $\lambda=1,\ \mu=10,\ X_0=3$
> >
> > Repeat the experiment with only 3 initial jobs.
> >
> > ```matlab
> > lambda = 1;
> > mu = 10;
> > X0 = 3;
> >
> > n = 10000;
> > X2 = zeros(1,n);
> >
> > for i = 1:n
> >     X2(i) = JobsDoneInTwoArrivals(lambda, mu, X0);
> > end
> >
> > % Mean
> > fprintf('Mean X2 = %.4f\n', mean(X2));
> >
> > % Histogram
> > figure;
> > histogram(X2);
> >
> > xlabel('Number of Jobs in System');
> > ylabel('Frequency');
> > title('X_2: \lambda = 1, \mu = 10, X_0 = 3');
> > grid on;
> > ```
>
> > [!abstract]- Flowchart
> >
> > ```mermaid
> > flowchart TD
> >     A([Start]) --> B[Input lambda, mu, X0]
> >     B --> C[Call JobsDoneInOneArrival lambda, mu, X0]
> >     C --> D[Get J1]
> >     D --> E[X1 = X0 - J1 + 1]
> >     E --> F[Call JobsDoneInOneArrival lambda, mu, X1]
> >     F --> G[Get J2]
> >     G --> H[X2 = X1 - J2 + 1]
> >     H --> I[Return X2]
> >     I --> J([End])
> > ```
>
> > [!info]- Question (iii) — Comment on Results
> >
> > In both experiments:
> >
> > $$
> > \lambda=1,\qquad\mu=10.
> > $$
> >
> > Therefore, the service rate is much larger than the arrival rate:
> >
> > $$
> > \mu>\lambda.
> > $$
> >
> > This means jobs are completed much faster than new jobs arrive.
> >
> > **When $X_0=100$**
> >
> > There are initially many jobs in the system. During the time between arrivals, several of these jobs can be completed.
> >
> > Therefore, after two arrivals, $X_2$ can be substantially smaller than the initial value $100$, although each arrival adds one new job.
> >
> > **When $X_0=3$**
> >
> > There are only a few initial jobs. Since $\mu=10$ is much larger than $\lambda=1$, it is quite possible for all initial jobs to be completed before the next arrival.
> >
> > However, the number of jobs cannot become negative. Once the system becomes empty, the newly arriving job becomes the only job in the system.
> >
> > Thus the distribution for $X_0=3$ is concentrated on relatively small integer values.
> >
> > The two experiments demonstrate an important queueing idea:
> >
> > $$
> > \boxed{\text{The initial number of jobs strongly affects the short-term system size.}}
> > $$
> >
> > As the system is observed for more arrivals, the effect of the initial condition becomes less important when $\mu>\lambda$.

> [!abstract]- Exercise 2 — Jobs in System After More Poisson Arrivals
>
> > [!info]- Question (i) — Jobs in System After 4 Arrivals
> >
> > Repeat the experiment from Exercise 1, but now obtain the number of jobs in the system after **4 more arrivals**.
> >
> > Starting with $X_0$, calculate:
> >
> > $$
> > J_1=\text{JobsDoneInOneArrival}(\lambda,\mu,X_0)
> > $$
> >
> > $$
> > X_1=(X_0-J_1)+1
> > $$
> >
> > Then:
> >
> > $$
> > J_2=\text{JobsDoneInOneArrival}(\lambda,\mu,X_1)
> > $$
> >
> > $$
> > X_2=(X_1-J_2)+1
> > $$
> >
> > Similarly:
> >
> > $$
> > X_3=(X_2-J_3)+1
> > $$
> >
> > $$
> > X_4=(X_3-J_4)+1
> > $$
> >
> > **Pseudocode**
> >
> > ```text
> > Input lambda, mu, X0
> >
> > J1 = JobsDoneInOneArrival(lambda, mu, X0)
> > X1 = X0 - J1 + 1
> >
> > J2 = JobsDoneInOneArrival(lambda, mu, X1)
> > X2 = X1 - J2 + 1
> >
> > J3 = JobsDoneInOneArrival(lambda, mu, X2)
> > X3 = X2 - J3 + 1
> >
> > J4 = JobsDoneInOneArrival(lambda, mu, X3)
> > X4 = X3 - J4 + 1
> >
> > Return X4
> > ```
>>
> > **MATLAB Code**
> >
> > ```matlab
> > function X4 = JobsDoneInFourArrivals(lambda, mu, X0)
> >
> >     J1 = JobsDoneInOneArrival(lambda, mu, X0);
> >     X1 = (X0 - J1) + 1;
> >
> >     J2 = JobsDoneInOneArrival(lambda, mu, X1);
> >     X2 = (X1 - J2) + 1;
> >
> >     J3 = JobsDoneInOneArrival(lambda, mu, X2);
> >     X3 = (X2 - J3) + 1;
> >
> >     J4 = JobsDoneInOneArrival(lambda, mu, X3);
> >     X4 = (X3 - J4) + 1;
> >
> > end
> > ```
>>
> > **Generate 10000 Samples**
> >
> > ```matlab
> > lambda = 1;
> > mu = 10;
> > X0 = 100;
> >
> > n = 10000;
> > X4 = zeros(1,n);
> >
> > for i = 1:n
> >     X4(i) = JobsDoneInFourArrivals(lambda, mu, X0);
> > end
> >
> > fprintf('Mean X4 = %.4f\n', mean(X4));
> >
> > figure;
> > histogram(X4);
> > xlabel('Number of Jobs in System');
> > ylabel('Frequency');
> > title('Jobs in System After 4 Arrivals');
> > grid on;
> > ```
>>
> > **Comparison with Exercise 1**
> >
> > Exercise 1 observes the system after 2 arrivals, whereas this exercise observes it after 4 arrivals.
> >
> > Since
> >
> > $$
> > \mu=10>\lambda=1,
> > $$
> >
> > jobs are completed much faster than new jobs arrive.
> >
> > As more arrivals occur, the influence of the initial value $X_0$ becomes weaker.
>
> > [!info]- Question (ii) — Average Queue Seen by Arrivals
> >
> > Repeat the experiment for $N$ arrivals and calculate
> >
> > $$
> > \boxed{
> > \bar X_N=
> > \frac{1}{N}
> > \sum_{i=0}^{N-1}(X_i-J_{i+1})
> > }
> > $$
> >
> > Here,
> >
> > $$
> > X_i-J_{i+1}
> > $$
> >
> > is the number of jobs in the system **immediately before the $(i+1)$-th arrival**.
> >
> > The program should be called:
> >
> > `AverageQueueSeenByArrivals(lambda, mu, X0, N)`
> >
> > **Pseudocode**
> >
> > ```text
> > Input lambda, mu, X0, N
> >
> > Set X = X0
> > Set total = 0
> >
> > For i = 1 to N:
> >
> >     J = JobsDoneInOneArrival(lambda, mu, X)
> >
> >     jobsBeforeArrival = X - J
> >
> >     total = total + jobsBeforeArrival
> >
> >     X = jobsBeforeArrival + 1
> >
> > End For
> >
> > Average = total / N
> >
> > Return Average
> > ```
>>
> > **MATLAB Code**
> >
> > ```matlab
> > function average = AverageQueueSeenByArrivals(lambda, mu, X0, N)
> >
> >     X = X0;
> >     total = 0;
> >
> >     for i = 1:N
> >
> >         % Jobs completed before next arrival
> >         J = JobsDoneInOneArrival(lambda, mu, X);
> >
> >         % Jobs present immediately before arrival
> >         jobsBeforeArrival = X - J;
> >
> >         % Add to total
> >         total = total + jobsBeforeArrival;
> >
> >         % Add the new arrival
> >         X = jobsBeforeArrival + 1;
> >
> >     end
> >
> >     average = total / N;
> >
> > end
> > ```
>>
> > **Required Experiment**
> >
> > Use
> >
> > $$
> > \mu=10,\qquad N=10000
> > $$
> >
> > and
> >
> > $$
> > \lambda=3,5,8,9,9.5.
> > $$
> >
> > ```matlab
> > mu = 10;
> > X0 = 100;
> > N = 10000;
> >
> > lambdaValues = [3 5 8 9 9.5];
> > averages = zeros(size(lambdaValues));
> >
> > for i = 1:length(lambdaValues)
> >     lambda = lambdaValues(i);
> >
> >     averages(i) = AverageQueueSeenByArrivals( ...
> >         lambda, mu, X0, N);
> > end
> >
> > table(lambdaValues', averages', ...
> >     'VariableNames', {'Lambda', 'AverageJobs'})
> > ```
>
> > [!info]- Question (iii) — Comment on Results
> >
> > The utilization of an M/M/1 queue is
> >
> > $$
> > \rho=\frac{\lambda}{\mu}.
> > $$
> >
> > For the given values:
> >
> > $$
> > \rho=0.3,\ 0.5,\ 0.8,\ 0.9,\ 0.95.
> > $$
> >
> > As $\lambda$ approaches $\mu$, the system becomes more heavily loaded and the average number of jobs increases.
> >
> > The theoretical stationary expected number of customers in an M/M/1 system is
> >
> > $$
> > \boxed{L=\frac{\rho}{1-\rho}}
> > $$
> >
> > The simulation results can be compared against this formula.
>
> > [!abstract]- Flowchart
> >
> > ```mermaid
> > flowchart TD
> >     A([Start]) --> B[Input lambda, mu, X0, N]
> >     B --> C[Set X = X0 and total = 0]
> >     C --> D{More arrivals?}
> >     D -->|Yes| E[Generate J = JobsDoneInOneArrival]
> >     E --> F[Jobs before arrival = X - J]
> >     F --> G[Add jobs before arrival to total]
> >     G --> H[X = jobs before arrival + 1]
> >     H --> D
> >     D -->|No| I[Average = total / N]
> >     I --> J[Return average]
> >     J --> K([End])
> > ```

> [!abstract]- Exercise 3 — k-Capacity ATM (Practice — Not for Submission)
>
> > [!info]- Problem Statement
> >
> > Consider an ATM with:
> >
> > - One machine/server
> > - Poisson arrivals with rate $\lambda$
> > - Exponential service times with rate $\mu$
> > - Maximum capacity $k$
> >
> > If an arriving customer finds $k$ customers already in the system, the customer is **lost** and does not receive service.
> >
> > We want to estimate the fraction of customers that are lost.
>
> > [!info]- State Equations
> >
> > Start with
> >
> > $$
> > X_0=k,\qquad L_0=0.
> > $$
> >
> > For each arrival $t$, generate
> >
> > $$
> > J_t=
> > \text{JobsDoneInOneArrival}(\lambda,\mu,X_{t-1}).
> > $$
> >
> > Number of customers just before the arrival:
> >
> > $$
> > X_{t-1}-J_t.
> > $$
> >
> > The new number of customers is
> >
> > $$
> > \boxed{
> > X_t=\min\{k,X_{t-1}-J_t+1\}
> > }
> > $$
> >
> > If the system was already full when the customer arrived:
> >
> > $$
> > X_{t-1}-J_t=k,
> > $$
> >
> > then that customer is lost:
> >
> > $$
> > L_t=L_{t-1}+1.
> > $$
> >
> > Otherwise:
> >
> > $$
> > L_t=L_{t-1}.
> > $$
> >
> > Finally:
> >
> > $$
> > \boxed{Z=\frac{L_T}{T}}
> > $$
> >
> > is the fraction of customers lost after $T$ arrivals.
>
> > [!example]- Pseudocode
> >
> > ```text
> > Input lambda, mu, k, T
> >
> > Set X = k
> > Set L = 0
> >
> > For t = 1 to T:
> >
> >     J = JobsDoneInOneArrival(lambda, mu, X)
> >
> >     customersBeforeArrival = X - J
> >
> >     If customersBeforeArrival == k:
> >         L = L + 1
> >     End If
> >
> >     X = min(k, customersBeforeArrival + 1)
> >
> >     Store L/t if required
> >
> > End For
> >
> > Z = L/T
> > Return Z
> > ```
>
> > [!example]- MATLAB Function — EstimateATM
> >
> > ```matlab
> > function [Z, times, estimates] = EstimateATM( ...
> >     lambda, mu, k, T, IntermediatePrint)
> >
> >     % Initial number of customers
> >     X = k;
> >
> >     % Initial number of lost customers
> >     L = 0;
> >
> >     % Arrays for intermediate estimates
> >     times = [];
> >     estimates = [];
> >
> >     for t = 1:T
> >
> >         % Jobs completed before next arrival
> >         J = JobsDoneInOneArrival(lambda, mu, X);
> >
> >         % Customers just before arrival
> >         customersBeforeArrival = X - J;
> >
> >         % Check whether arriving customer is lost
> >         if customersBeforeArrival == k
> >             L = L + 1;
> >         end
> >
> >         % Update number of customers
> >         X = min(k, customersBeforeArrival + 1);
> >
> >         % Store estimates at 1, 101, 201, ...
> >         if t == 1 || mod(t-1,100) == 0
> >             times(end+1) = t;
> >             estimates(end+1) = L/t;
> >         end
> >
> >         % Optional intermediate printing
> >         if IntermediatePrint == 1 && mod(t,100) == 0
> >             fprintf('t = %d, Loss estimate = %.4f\n', ...
> >                     t, L/t);
> >         end
> >
> >     end
> >
> >     % Final loss fraction
> >     Z = L/T;
> >
> > end
> > ```
>
> > [!info]- Plot 3 Sample Paths
> >
> > The requirement is to plot
> >
> > $$
> > \frac{L_t}{t}
> > $$
> >
> > for
> >
> > $$
> > t\in\{1,101,201,\ldots,T\}
> > $$
> >
> > using 3 independent sample paths.
> >
> > ```matlab
> > lambda = 2;
> > mu = 2.4;
> > k = 4;
> > T = 10001;
> >
> > figure;
> > hold on;
> >
> > for path = 1:3
> >
> >     [Z, times, estimates] = EstimateATM( ...
> >         lambda, mu, k, T, 0);
> >
> >     plot(times, estimates, 'LineWidth', 1.2);
> >
> > end
> >
> > xlabel('Arrival number');
> > ylabel('L_t / t');
> > title('Loss Fraction — 3 Sample Paths');
> > grid on;
> > hold off;
> > ```
>
> > [!example]- Generate Random Sample of Loss Fractions
> >
> > Use:
> >
> > $$
> > n=1000,\qquad\lambda=2,\qquad\mu=2.4.
> > $$
> >
> > **For $T=10$**
> >
> > ```matlab
> > lambda = 2;
> > mu = 2.4;
> > k = 4;
> > T = 10;
> > n = 1000;
> >
> > Z10 = zeros(1,n);
> >
> > for i = 1:n
> >     Z10(i) = EstimateATM(lambda, mu, k, T, 0);
> > end
> >
> > fprintf('Mean for T = 10: %.4f\n', mean(Z10));
> >
> > figure;
> > histogram(Z10);
> > xlabel('Loss Fraction');
> > ylabel('Frequency');
> > title('Loss Fraction for T = 10');
> > grid on;
> > ```
>>
> > **For $T=400$**
> >
> > ```matlab
> > T = 400;
> > Z400 = zeros(1,n);
> >
> > for i = 1:n
> >     Z400(i) = EstimateATM(lambda, mu, k, T, 0);
> > end
> >
> > fprintf('Mean for T = 400: %.4f\n', mean(Z400));
> >
> > figure;
> > histogram(Z400);
> > xlabel('Loss Fraction');
> > ylabel('Frequency');
> > title('Loss Fraction for T = 400');
> > grid on;
> > ```
>
> > [!info]- Compare $k=1$ and $k=4$
> >
> > For $k=1$, the system can contain at most one customer.
> >
> > For $k=4$, the system can contain up to four customers.
> >
> > Therefore, increasing $k$ gives the system more capacity to accommodate customers before an arriving customer is rejected.
> >
> > The simulation can be used to compare the resulting loss fractions for:
> >
> > $$
> > k=1
> > $$
> >
> > and
> >
> > $$
> > k=4.
> >$$
> >
> > For larger $T$, the estimated loss fraction generally becomes more stable because it is based on more arrival events.
>
> > [!abstract]- Flowchart
> >
> > ```mermaid
> > flowchart TD
> >     A([Start]) --> B[Input lambda, mu, k, T]
> >     B --> C[Set X = k and L = 0]
> >     C --> D{t <= T?}
> >     D -->|Yes| E[Generate J = JobsDoneInOneArrival]
> >     E --> F[Customers before arrival = X - J]
> >     F --> G{Customers before arrival = k?}
> >     G -->|Yes| H[L = L + 1]
> >     G -->|No| I[L unchanged]
> >     H --> J[X = min k, customers before arrival + 1]
> >     I --> J
> >     J --> K[Store L/t if required]
> >     K --> D
> >     D -->|No| L[Z = L/T]
> >     L --> M([End])
> > ```

---


