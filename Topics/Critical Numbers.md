---
section: "3.1"
date_covered: "2026-02-17"
textbook: "Stewart Calculus 9e"
tags: [calculus, derivatives, extrema]
---

# Critical Numbers

> [!info] Deep Dive — Critical Numbers
> Supporting topic for [[3.1 Maximum and Minimum Values]].

## Definition

> [!def] Critical Number
> A number $c$ in the domain of $f$ is a **critical number** if either:
> 1. $f'(c) = 0$, or
> 2. $f'(c)$ does not exist

Critical numbers are the **only candidates** for local extrema (by Fermat's Theorem).

## Why Two Cases?

**Case 1: $f'(c) = 0$** — horizontal tangent line. The function levels off, potentially changing from increasing to decreasing (or vice versa).

**Case 2: $f'(c)$ DNE** — this happens at corners, cusps, or vertical tangents. The function can still have a max or min at these points (e.g., $|x|$ at $x = 0$).

## Finding Critical Numbers

> [!def] Procedure
> 1. Find $f'(x)$
> 2. Set $f'(x) = 0$ and solve
> 3. Find where $f'(x)$ is undefined (but $f(x)$ IS defined)
> 4. List all such $x$-values — these are the critical numbers

> [!example] Example 1 — Polynomial
> $f(x) = 2x^3 - 9x^2 + 12x - 4$
>
> $f'(x) = 6x^2 - 18x + 12 = 6(x^2 - 3x + 2) = 6(x-1)(x-2)$
>
> $f'(x) = 0$: $x = 1$ and $x = 2$. $f'$ exists everywhere.
>
> Critical numbers: $x = 1, 2$.

> [!example] Example 2 — Absolute Value
> $f(x) = |x - 3|$
>
> $f'(x) = \begin{cases} -1 & x < 3 \\ 1 & x > 3 \end{cases}$
>
> $f'(3)$ does not exist (corner). $f'(x) \neq 0$ elsewhere.
>
> Critical number: $x = 3$.

> [!example] Example 3 — Rational Exponent
> $f(x) = x^{2/3}(x - 4)$
>
> Using product rule: $f'(x) = \frac{2}{3}x^{-1/3}(x-4) + x^{2/3} = \frac{2(x-4)}{3x^{1/3}} + x^{2/3}$
>
> Combine over common denominator $3x^{1/3}$:
> $$f'(x) = \frac{2(x-4) + 3x}{3x^{1/3}} = \frac{5x - 8}{3x^{1/3}}$$
>
> $f'(x) = 0$: $x = \frac{8}{5}$. $f'$ undefined at $x = 0$ (but $f(0) = 0$ exists).
>
> Critical numbers: $x = 0$ and $x = \frac{8}{5}$.

> [!example] Example 4 — Trig
> $f(x) = \sin x + \cos x$ on $[0, 2\pi]$
>
> $f'(x) = \cos x - \sin x = 0 \implies \sin x = \cos x \implies x = \frac{\pi}{4}, \frac{5\pi}{4}$
>
> Critical numbers: $x = \frac{\pi}{4}, \frac{5\pi}{4}$.

## Important Warning

> [!tip] Critical Number ≠ Extremum
> A critical number is a **candidate** for an extremum, but not every critical number gives one.
>
> Example: $f(x) = x^3$ has $f'(0) = 0$, so $x = 0$ is a critical number. But $f$ has **no** local max or min at $x = 0$ (it's an inflection point).

## See Also
- [[3.1 Maximum and Minimum Values]]
- [[Differentiability]]
