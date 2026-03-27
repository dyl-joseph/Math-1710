---
section: "3.3"
date_covered: "2026-02-24"
textbook: "Stewart Calculus 9e"
tags: [calculus, derivatives, extrema, concavity]
---

# First and Second Derivative Tests

> [!info] Deep Dive — Tests for Local Extrema
> Supporting topic for [[3.3 The Shape of Graphs]].

## The First Derivative Test

> [!thm] First Derivative Test
> Suppose $c$ is a critical number of a continuous function $f$.
>
> **(a)** If $f'$ changes from **positive to negative** at $c$, then $f$ has a **local maximum** at $c$.
>
> **(b)** If $f'$ changes from **negative to positive** at $c$, then $f$ has a **local minimum** at $c$.
>
> **(c)** If $f'$ does **not change sign** at $c$ (positive on both sides, or negative on both sides), then $f$ has **no local extremum** at $c$.

### How to Apply

1. Find all critical numbers
2. Make a sign chart for $f'$ using test points in each interval
3. Check where $f'$ changes sign

> [!example] Example
> $f(x) = x^4 - 4x^3$
>
> $f'(x) = 4x^3 - 12x^2 = 4x^2(x - 3)$
>
> Critical numbers: $x = 0, 3$
>
> | Interval | Test point | $f'$ sign |
> |---|---|---|
> | $(-\infty, 0)$ | $x = -1$ | $4(1)(-4) = -$ |
> | $(0, 3)$ | $x = 1$ | $4(1)(-2) = -$ |
> | $(3, \infty)$ | $x = 4$ | $4(16)(1) = +$ |
>
> At $x = 0$: $f'$ is negative on both sides → **no extremum**
>
> At $x = 3$: $f'$ changes from $-$ to $+$ → **local minimum**, $f(3) = 81 - 108 = -27$

### Advantages Over Second Derivative Test
- Works when $f''(c) = 0$ (second derivative test is inconclusive)
- Works when $f'(c)$ DNE (corners, cusps)
- Always gives a definitive answer

## The Second Derivative Test

> [!thm] Second Derivative Test
> Suppose $f''$ is continuous near $c$ and $f'(c) = 0$.
>
> **(a)** If $f''(c) > 0$, then $f$ has a **local minimum** at $c$ (concave up = cup = minimum)
>
> **(b)** If $f''(c) < 0$, then $f$ has a **local maximum** at $c$ (concave down = cap = maximum)
>
> **(c)** If $f''(c) = 0$, the test is **inconclusive** — use the First Derivative Test instead

> [!tip] Memory Aid
> - $f''(c) > 0$: concave **up** like a cup → holds water → **minimum**
> - $f''(c) < 0$: concave **down** like a cap → sheds water → **maximum**

### How to Apply

1. Find critical numbers where $f'(c) = 0$
2. Compute $f''(c)$
3. Classify based on sign

> [!example] Example
> $f(x) = x^3 - 6x^2 + 9x + 1$
>
> $f'(x) = 3x^2 - 12x + 9 = 3(x-1)(x-3)$. Critical: $x = 1, 3$.
>
> $f''(x) = 6x - 12$
>
> $f''(1) = -6 < 0$ → **local max** at $x = 1$, $f(1) = 5$
>
> $f''(3) = 6 > 0$ → **local min** at $x = 3$, $f(3) = 1$

### When the Test Fails

$f''(c) = 0$ is inconclusive. Consider $f(x) = x^4$ vs $g(x) = x^3$ at $x = 0$:
- $f(x) = x^4$: $f'(0) = 0$, $f''(0) = 0$, but $x = 0$ IS a local min
- $g(x) = x^3$: $g'(0) = 0$, $g''(0) = 0$, and $x = 0$ is NOT an extremum

In both cases $f''(0) = 0$, but the conclusions differ. Must use First Derivative Test.

## When to Use Which Test

| Situation | Recommended Test |
|---|---|
| $f'(c) = 0$ and $f''(c)$ is easy to compute | Second Derivative Test |
| $f'(c) = 0$ and $f''(c) = 0$ | First Derivative Test |
| $f'(c)$ DNE | First Derivative Test |
| Many critical numbers, $f''$ is complicated | First Derivative Test |
| Need concavity info anyway | Second Derivative Test |

## See Also
- [[3.3 The Shape of Graphs]]
- [[Critical Numbers]]
- [[Mean Value Theorem]] — theoretical basis for the increasing/decreasing test
