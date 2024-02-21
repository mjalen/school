# Lecture 2

## Taylor's Thm (p. 9)

There exists an $\xi = \xi(x)$ between $x$ and $x_0$. The remainder is

$R_n(x) = \frac{f^{(n=1)}(\xi)}{(n+1)!} (x-x_0)^{n+1}$

This thm also gives $P_n(x)$ such that 

$f(x) = P_n(x) + R_n(x).$

Remember the interval of $c$ is always $[x, x_0]$ or $[x_0, x]$. 

### Cases of Upper Bound Error

1. If $x$ is fixed, you can approx $|f(x) - P_n(x)| = | R_n(x) | = \frac{| f^{(n+1)} (c) \cdot (x-x_0)^{n+1} |}{(n+1)!}$. Furthermore, $|R_n(x)| \leq \frac{| (x-x_0)^{n+1} |}{(n+1)!} \cdot \max_c | f^{(n+1)}(c) |$.

2. If $x$ is not fixed ($x\in[a,b]$), then $|f(x) - P_n(x) | \leq \max_x \frac{| \cdot (x-x_0)^{n+1} |}{(n+1)!} \cdot \max_c | f^{(n+1)}(c) |$ 


### Exp 

Consider $f(x) = e^{-x}$ given $x_0 = 0$.

1. $P_n (x) = \sum_{k=0}^n \frac{(-1)^k}{k!} x^k$, since $f^{(k)}(x) = (-1)^k e^{-x}$. $R_n(x) = \frac{(-1)^{n+1} e^{-c}}{(n+1)!} x^{n+1}$.

2. $P_4(0.5) = 0.9048375$. The upper bound error $|f(0.5) - P_4(0.5)| = | R_4(0.5) | = \frac{0.5^5}{120} e^{-c}$. To find the maximum error in terms of $c$, note $c\in [0, 0.5]$. Then the max error is $2.6 \times 10^{-4}$. The actual error can be computed by $|e^{-0.5} - P_4(0.4)| = 2.4\times 10^{-4}$.  

3. Find upper bound for $|f(x) - P_4(x)|$ for $x\in [0,1]$. $x$ is not fixed, so we max two things. $=|R_4(x)| = |\frac{(-1)^{5} e^{-c}}{5!} x^5| = \frac{1}{120} e^{-c} x^5 \leq \frac{1}{120} \max_c e^{-c} \max_x x^5 = 8.33 \times 10^{-3}$.

4. $\int_0^{0.5} f(x) dx \approx \int_0^{0.5} P_4(x) dx = x - \frac{x^2}{2} + \frac{x^3}{6} - \frac{x^4}{24} + \frac{x^5}{120} \Bigm|_0^1 = 0.39489$.

5. The upper bound error of the integral in (4) is $\int_0^{0.5} | R_4(x) | dx = \int_0^{0.5} | \frac{(-1)^5 e^{-c}}{5!} x^5 dx \leq \frac{1}{120} \int_0^{0.5} e^{-c} x^5 dx \leq \frac{1}{120} \int_0^{0.5} x^5 dx = \frac{1}{120} \frac{(0.5)^5}{6} = 2.17\times 10^{-5}$. 

6. Find a value $n$ to approximate $f(x)$ within $10^{-8}$ on $[0,1]$. $|f(x) - P_n(x)| \leq 10^{-8}$, or $|R_n(x)| \leq 10^{-8}$. This is solved by maximizing in terms of $c$ and $x$ and to find a remainder in terms of $n$. The answer is $\frac{1}{(n+1)!} \leq 10^{-8}$.  

### Exp

- $e^x = \sum_{k=0}^n \frac{x^k}{k!} + \frac{e^c x^{n+1}}{(n+1)!}$. 

- $\frac{1}{1-x} = \sum_{k=0}^n x^k + \frac{x^{n+1}}{(1+c)^{n+2}}$.

- $\ln(1+x) = \ldots$.

So on... this is review.

## Section 1.2

- _Round-off err_. 
    - Due to the finite floating point precision. Computers truncate binary.
    - Clamping $n$ in a Taylor polynomial.

Error can propogate and magnify

### Round Off Error

aka. rounding error, machine error.

The difference between the exact number and machine numbers.

