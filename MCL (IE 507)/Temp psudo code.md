
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











