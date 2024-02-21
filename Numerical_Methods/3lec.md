# Lecture 3

Floating points are based on IEEE 754-1985 and 2008.

The first bit $s$ is the _sign_ bit, followed by a set number of _characteristic_ (exponent) bits $c$, and then the _mantissa_ $f$.  

- Single precision: `f32` or `float`
- Double precision `f64` or `double`
- Extended precision: `f128` or (long?)

A `f64` is represented as $(-1)^{s} \cdot 2^{(c-1023)} \cdot (1+f)$

Note that $(c - 1023)\in [-1023, 1024]$. Notice that the floating point number is a binary representation of 
scientific notation.

The _underflow_ ($0$) is $<2^{-1022} \cdot ( 1 + 0 )$ and the _overflow_ ($\infty$) is $>2^{1023} \cdot (2 - 2^{-52})$ 

Keep in mind the mantisa is calculated left to right with $2^{-d}$ where $d$ is the digit from left to right
starting from $-1$ on the left to $-52$ at the right. Think of the mantisa as $0.b_{-1}b_{-2}\ldots$. 

## Exp

Consider $1$ $10000000101$ $01101010\ldots 0$ (45 zeroes). 

Then, $s=1$, $c=1029$, and $m=0.4140625$. The resulting number is $(90.5)_{10}$.

## Rounding / Chopping

Can represent $float(x)$ ($fl(x)$) in two ways.

A number $x$ can be normalized to decimal scientific notation. We can then represent $x$ by:

- *Chopping* involves 
