---
section: "4.1"
date_covered: "2026-03-31"
textbook: "Stewart Calculus 9e"
tags: [calculus, integration, riemann-sums]
---

# Sigma Notation and Riemann Sums

> [!info] Deep Dive — Sigma Notation and Riemann Sums
> Supporting topic for [[4.1 The Area Under a Curve]].

## Sigma Notation

> [!def] Sigma Notation
> $$\sum_{i=1}^{n} a_i = a_1 + a_2 + a_3 + \cdots + a_n$$

### Useful Summation Formulas

> [!thm] Summation Formulas
> $$\sum_{i=1}^{n} 1 = n$$
> $$\sum_{i=1}^{n} i = \frac{n(n+1)}{2}$$
> $$\sum_{i=1}^{n} i^2 = \frac{n(n+1)(2n+1)}{6}$$
> $$\sum_{i=1}^{n} i^3 = \left[\frac{n(n+1)}{2}\right]^2$$

### Properties

$$\sum_{i=1}^{n} ca_i = c\sum_{i=1}^{n} a_i \qquad \sum_{i=1}^{n}(a_i \pm b_i) = \sum_{i=1}^{n} a_i \pm \sum_{i=1}^{n} b_i$$

> [!example] Example
> $$\sum_{i=1}^{5} (2i + 1) = 3 + 5 + 7 + 9 + 11 = 35$$
>
> Or: $2\sum_{i=1}^{5}i + \sum_{i=1}^{5}1 = 2\cdot 15 + 5 = 35$. ✓

## Riemann Sums

> [!def] Setup
> To approximate the area under $y = f(x)$ from $x = a$ to $x = b$:
> 1. Divide $[a, b]$ into $n$ equal subintervals of width $\Delta x = \frac{b-a}{n}$
> 2. Endpoints: $x_i = a + i\Delta x$ for $i = 0, 1, \ldots, n$
> 3. Choose a sample point $x_i^*$ in each subinterval $[x_{i-1}, x_i]$
> 4. Riemann sum: $\sum_{i=1}^{n} f(x_i^*)\Delta x$

### Types of Riemann Sums

| Type | Sample Point $x_i^*$ | Formula |
|---|---|---|
| Right | $x_i = a + i\Delta x$ | $R_n = \sum_{i=1}^{n} f(a + i\Delta x)\Delta x$ |
| Left | $x_{i-1} = a + (i-1)\Delta x$ | $L_n = \sum_{i=1}^{n} f(a + (i-1)\Delta x)\Delta x$ |
| Midpoint | $\bar{x}_i = a + (i - \frac{1}{2})\Delta x$ | $M_n = \sum_{i=1}^{n} f(\bar{x}_i)\Delta x$ |

> [!example] Example — Right Riemann Sum
> Approximate $\int_0^1 x^2\,dx$ with $n = 4$ right endpoints.
>
> $\Delta x = \frac{1}{4}$. Right endpoints: $\frac{1}{4}, \frac{1}{2}, \frac{3}{4}, 1$.
>
> $$R_4 = \frac{1}{4}\left[\left(\frac{1}{4}\right)^2 + \left(\frac{1}{2}\right)^2 + \left(\frac{3}{4}\right)^2 + 1^2\right] = \frac{1}{4}\left[\frac{1}{16} + \frac{1}{4} + \frac{9}{16} + 1\right]$$
> $$= \frac{1}{4} \cdot \frac{30}{16} = \frac{30}{64} = \frac{15}{32} = 0.46875$$
>
> (Exact value is $\frac{1}{3} \approx 0.333$, so right sum overestimates for increasing functions.)

## Exact Area as a Limit

> [!thm] Area as Limit of Riemann Sums
> $$A = \lim_{n \to \infty} \sum_{i=1}^{n} f(x_i^*)\Delta x$$
> provided $f$ is continuous (or at least integrable) on $[a, b]$.

> [!example] Example — Exact Area of $x^2$ on $[0, 1]$
> Using right endpoints: $x_i = \frac{i}{n}$, $\Delta x = \frac{1}{n}$.
>
> $$\sum_{i=1}^{n} \left(\frac{i}{n}\right)^2 \cdot \frac{1}{n} = \frac{1}{n^3}\sum_{i=1}^{n} i^2 = \frac{1}{n^3} \cdot \frac{n(n+1)(2n+1)}{6} = \frac{(n+1)(2n+1)}{6n^2}$$
>
> $$A = \lim_{n \to \infty} \frac{(n+1)(2n+1)}{6n^2} = \lim_{n \to \infty} \frac{2n^2 + 3n + 1}{6n^2} = \frac{2}{6} = \frac{1}{3}$$

## See Also
- [[4.1 The Area Under a Curve]]
- [[Limits at Infinity]] — used to evaluate the limit of Riemann sums
