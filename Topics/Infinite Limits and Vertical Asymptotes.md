---
section: "1.5"
date_covered:
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, limits]
---

# Infinite Limits and Vertical Asymptotes

## Infinite Limits

When a function grows without bound near a point, we describe this with infinite limit notation.

> [!def] Infinite Limits
> Let $f$ be defined on both sides of $a$ (except possibly at $a$ itself).
>
> $$\lim_{x \to a} f(x) = \infty$$
> means that the values of $f(x)$ can be made **arbitrarily large** (as large as we please) by taking $x$ sufficiently close to $a$, but $x \neq a$.
>
> $$\lim_{x \to a} f(x) = -\infty$$
> means that the values of $f(x)$ can be made **arbitrarily large negative** by taking $x$ sufficiently close to $a$, but $x \neq a$.

Similar definitions apply for the one-sided versions: $\lim_{x \to a^+} f(x) = \infty$, $\lim_{x \to a^-} f(x) = -\infty$, etc.

> [!tip] Important Distinction
> Writing $\lim_{x \to a} f(x) = \infty$ does **not** mean the limit "exists" in the usual sense — $\infty$ is not a real number. This notation is a shorthand for describing the specific way the limit fails to exist: the function blows up.

## Vertical Asymptotes

> [!def] Vertical Asymptote
> The vertical line $x = a$ is called a **vertical asymptote** of the curve $y = f(x)$ if at least one of the following is true:
>
> $$\lim_{x \to a} f(x) = \infty \qquad \lim_{x \to a} f(x) = -\infty$$
> $$\lim_{x \to a^+} f(x) = \infty \qquad \lim_{x \to a^+} f(x) = -\infty$$
> $$\lim_{x \to a^-} f(x) = \infty \qquad \lim_{x \to a^-} f(x) = -\infty$$

In other words, a vertical asymptote occurs wherever the function "blows up" to $\pm\infty$ from at least one side.

## Finding Vertical Asymptotes of Rational Functions

For a rational function $f(x) = \dfrac{p(x)}{q(x)}$ (where $p$ and $q$ are polynomials with no common factors):

> [!tip] Procedure
> 1. **Set the denominator equal to zero:** solve $q(a) = 0$.
> 2. **Check the numerator:** if $p(a) \neq 0$, then $x = a$ is a vertical asymptote.
> 3. If $p(a) = 0$ **and** $q(a) = 0$, there is a **common factor** — cancel it first, then re-check. (The point may be a hole rather than an asymptote.)

> [!example] Finding Vertical Asymptotes
> Find the vertical asymptotes of $f(x) = \dfrac{x + 1}{x^2 - 4}$.
>
> **Solution.** Factor the denominator: $x^2 - 4 = (x-2)(x+2)$.
>
> Set denominator $= 0$: $x = 2$ or $x = -2$.
>
> Check the numerator at each:
> - $f$ numerator at $x = 2$: $2 + 1 = 3 \neq 0$ $\checkmark$ — vertical asymptote at $x = 2$.
> - $f$ numerator at $x = -2$: $-2 + 1 = -1 \neq 0$ $\checkmark$ — vertical asymptote at $x = -2$.

## Sign Analysis: Determining $+\infty$ vs. $-\infty$

Once you know there's a vertical asymptote at $x = a$, determine the **sign** of $f(x)$ on each side to decide whether the function goes to $+\infty$ or $-\infty$.

> [!tip] Sign Analysis Technique
> To find $\lim_{x \to a^+} f(x)$ or $\lim_{x \to a^-} f(x)$:
> 1. Substitute a **test value** just to the left or right of $a$.
> 2. Determine the **sign** of each factor in the numerator and denominator.
> 3. The overall sign tells you $+\infty$ or $-\infty$.
>
> You don't need the exact value — just the sign.

> [!example] Sign Analysis for $\dfrac{x+1}{x^2-4}$ near $x = 2$
> We have $f(x) = \dfrac{x+1}{(x-2)(x+2)}$.
>
> **As $x \to 2^+$** (e.g., $x = 2.01$):
> - Numerator: $2.01 + 1 = 3.01 > 0$ → positive
> - $(x - 2)$: $0.01 > 0$ → positive
> - $(x + 2)$: $4.01 > 0$ → positive
> - Overall: $\dfrac{(+)}{(+)(+)} = +$ → $\lim_{x \to 2^+} f(x) = +\infty$
>
> **As $x \to 2^-$** (e.g., $x = 1.99$):
> - Numerator: $2.99 > 0$ → positive
> - $(x - 2)$: $-0.01 < 0$ → **negative**
> - $(x + 2)$: $3.99 > 0$ → positive
> - Overall: $\dfrac{(+)}{(-)(+)} = -$ → $\lim_{x \to 2^-} f(x) = -\infty$

## Classic Examples

### Example 1: $f(x) = \dfrac{1}{x^2}$

> [!example] $1/x^2$ near $x = 0$
> As $x \to 0$ from either side, $x^2 \to 0^+$ (always positive), so:
> $$\frac{1}{x^2} \to +\infty$$
>
> Both one-sided limits agree:
> $$\lim_{x \to 0^-} \frac{1}{x^2} = +\infty \qquad \lim_{x \to 0^+} \frac{1}{x^2} = +\infty$$
>
> Therefore $\displaystyle\lim_{x \to 0} \frac{1}{x^2} = \infty$. The line $x = 0$ is a vertical asymptote.
>
> Compare with $1/x$, where the two sides go in **opposite** directions:
> $$\lim_{x \to 0^-} \frac{1}{x} = -\infty \qquad \lim_{x \to 0^+} \frac{1}{x} = +\infty$$
>
> For $1/x$, we cannot write $\lim_{x \to 0} \frac{1}{x} = \infty$ because the two sides disagree on sign. The line $x = 0$ is still a vertical asymptote (we only need one side to blow up).

### Example 2: $\tan(x)$

> [!example] $\tan(x)$ near $x = \pi/2$
> Recall $\tan(x) = \dfrac{\sin x}{\cos x}$. At $x = \pi/2$, $\cos(\pi/2) = 0$ and $\sin(\pi/2) = 1 \neq 0$.
>
> - As $x \to (\pi/2)^-$: $\cos x \to 0^+$ (cosine is positive just left of $\pi/2$), so $\tan x \to +\infty$.
> - As $x \to (\pi/2)^+$: $\cos x \to 0^-$ (cosine is negative just right of $\pi/2$), so $\tan x \to -\infty$.
>
> Therefore $x = \pi/2$ is a vertical asymptote of $\tan(x)$. In fact, $\tan(x)$ has vertical asymptotes at every $x = \dfrac{\pi}{2} + n\pi$ for integer $n$.

### Example 3: $\ln(x)$ near $0$

> [!example] $\ln(x)$ near $x = 0$
> The natural logarithm is only defined for $x > 0$, so we consider the one-sided limit:
> $$\lim_{x \to 0^+} \ln(x) = -\infty$$
>
> As $x$ decreases toward $0$ from the right, $\ln(x)$ decreases without bound. The line $x = 0$ (the $y$-axis) is a vertical asymptote of $y = \ln(x)$.
>
> Quick check: $\ln(0.1) \approx -2.3$, $\ln(0.01) \approx -4.6$, $\ln(0.001) \approx -6.9$ — the values keep getting more negative.

## Worked Examples

> [!example] Worked Example: Rational Function
> Find all vertical asymptotes of $f(x) = \dfrac{2x}{x^2 - x - 6}$ and evaluate the relevant one-sided limits at each.
>
> **Solution.**
>
> Factor denominator: $x^2 - x - 6 = (x-3)(x+2)$.
>
> Denominator $= 0$: $x = 3$ and $x = -2$. Numerator at $x = 3$: $6 \neq 0$. Numerator at $x = -2$: $-4 \neq 0$. So **both** are vertical asymptotes.
>
> **At $x = 3$:** $f(x) = \dfrac{2x}{(x-3)(x+2)}$
> - $x \to 3^+$: signs are $\dfrac{(+)}{(+)(+)} = +$ → $\lim_{x \to 3^+} f(x) = +\infty$
> - $x \to 3^-$: signs are $\dfrac{(+)}{(-)(+)} = -$ → $\lim_{x \to 3^-} f(x) = -\infty$
>
> **At $x = -2$:** $f(x) = \dfrac{2x}{(x-3)(x+2)}$
> - $x \to -2^+$: signs are $\dfrac{(-)}{(-)(+)} = +$ → $\lim_{x \to -2^+} f(x) = +\infty$
> - $x \to -2^-$: signs are $\dfrac{(-)}{(-)(-)} = -$ → $\lim_{x \to -2^-} f(x) = -\infty$

> [!example] Worked Example: Hole vs. Asymptote
> Analyze $g(x) = \dfrac{x^2 - 9}{x^2 - 5x + 6}$ at points where the denominator is zero.
>
> **Solution.**
>
> Factor: $g(x) = \dfrac{(x-3)(x+3)}{(x-3)(x-2)}$.
>
> Denominator $= 0$ at $x = 3$ and $x = 2$.
>
> - **At $x = 3$:** Both numerator and denominator are $0$. Cancel the common factor:
>   $$g(x) = \frac{x+3}{x-2} \quad (x \neq 3)$$
>   Now at $x = 3$: $\dfrac{6}{1} = 6$. So $\lim_{x \to 3} g(x) = 6$. This is a **removable discontinuity** (hole), not a vertical asymptote.
>
> - **At $x = 2$:** After cancellation, $g(x) = \dfrac{x+3}{x-2}$. Numerator at $x = 2$: $5 \neq 0$. So $x = 2$ **is** a vertical asymptote.
>   - $x \to 2^+$: $\dfrac{(+)}{(+)} = +$ → $+\infty$
>   - $x \to 2^-$: $\dfrac{(+)}{(-)} = -$ → $-\infty$

## See Also

- [[1.5 Introduction to Limits]]
- [[Intuitive Idea of a Limit]]
- [[One-Sided Limits]]
