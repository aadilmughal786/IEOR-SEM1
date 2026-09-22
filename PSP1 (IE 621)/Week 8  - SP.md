random process -  a collection of RV - stochastic process - 

$$P(X_{1} = +1) = P(X_{1}=-1) = \frac{1}{2}$$


Let $$S_{0} = 0$$
$$S_{n} = \sum_{i=1}^{n} X_{i} = S_{n-1}+X_{n}$$


$\{S_{n}\}\to$ also a  SP discreate time (DRV)
- $S_{n}$ is  not  independant as we  can  see  in recursion as well


>[!tip]- Sample Path
>$${S_{n}(\omega) \to n = 0,1,2,3,\dots}$$
>WIP

>[!tip]- Symmetric random walk
>
>WIP

$$P(S_{n+1} = j | S_{n}=i) = \begin{cases}
\frac{1}{2} & j = i-1 \\ \\
\frac{1}{2} & j = i+1 \\ \\
0 & \text{o.w.}
\end{cases}$$


The  **future** $(n+1)$  depands on the **present** $(n)$

>[!tip]- Discreate-time Markov chain
>A RP taking  values in a discreate set X (**state space**) is said to be  a DTMC
>$$P(X_{n+1} = x_{n+1} | X_{n} = x_{n}, X_{n-1} = x_{n-1}\dots,X_{0}=x_{0}) = P(X_{n+1} = x_{n+1} | X_{n} = x_{n})$$
>
>So we can  see for any  path  probability will be  same 

>[!tip] Time Homogeneity
>$$P(X_{n+1} = y | X_{n} = x_{n}, X_{n-1} = x_{n-1}\dots,X_{0}=x_{0}) = P(X_{n+1} = y | X_{n} = x_{n})$$
>
>A DTMC is said  to me time-homogeneity if $\forall x,y$
>$$P(X_{n+1} = y | X_{n} = x) = P(X_{1} = y | X_{0} = x) \quad \forall n$$


>[!tip] Transition probability and  matrix , diagram
>WIP

$$p_{x,y} = \{ P(X_{1}=y|X_{0}=x)\}, \quad p_{x,y} \geq 0$$

