
> [!tip]- Numerical Methods and Why Do We Need Them?
> 
> Numerical Methods are a **collection of techniques** used to solve mathematical problems that cannot be solved exactly or easily by **analytical methods**. They are crucial for approximating solutions to complex problems in fields such as engineering, physics, computer science, and economics.
> 
> We need Numerical Methods because many real-world problems involve equations that cannot be solved symbolically or have no closed-form solutions. These methods allow us to find **approximate solutions** with a **desired level of accuracy**, enabling practical decision-making and simulations.

---

> [!tip]- Horner’s Method
> 
> Horner’s Method simplifies polynomial evaluation by **reducing the number of multiplications**. 
> 
> **For a polynomial like** $$P(x) = a_n x^n + a_{n-1} x^{n-1} + \dots + a_1 x + a_0$$ **rewrite it as:**
> 
> $$P(x) = (((a_n x + a_{n-1}) x + a_{n-2}) x + \dots) x + a_0$$
> 
> This reduces the computational complexity and makes the evaluation more efficient.
> 
>---
>
> - The number of multiplications required in **Horner’s method** depends on the degree of the polynomial.
> - For a polynomial of degree $n$, there will be $n$ **multiplications** and $n$ **additions**.


