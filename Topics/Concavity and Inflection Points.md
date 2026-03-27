---
section: "3.3"
date_covered: "2026-02-24"
textbook: "Stewart Calculus 9e"
tags: [calculus, derivatives, concavity]
---

# Concavity and Inflection Points

> [!info] Deep Dive — Concavity and Inflection Points
> Supporting topic for [[3.3 The Shape of Graphs]].

## Concavity

> [!def] Concave Up and Concave Down
> - $f$ is **concave up** on $I$ if $f'$ is increasing on $I$ (equivalently, $f''(x) > 0$)
> - $f$ is **concave down** on $I$ if $f'$ is decreasing on $I$ (equivalently, $f''(x) < 0$)

> [!thm] Concavity Test
> If $f''(x) > 0$ for all $x$ in $I$, then $f$ is concave up on $I$.
> If $f''(x) < 0$ for all $x$ in $I$, then $f$ is concave down on $I$.

**Geometric meaning:**
- Concave up: curve lies **above** its tangent lines (shaped like a cup ∪)
- Concave down: curve lies **below** its tangent lines (shaped like a cap ∩)

**Slope interpretation:**
- Concave up: slopes are **increasing** (tangent rotates counterclockwise)
- Concave down: slopes are **decreasing** (tangent rotates clockwise)

## Inflection Points

> [!def] Inflection Point
> A point $P = (c, f(c))$ is an **inflection point** of $f$ if $f$ is continuous at $c$ and the concavity **changes** at $c$ (from up to down, or down to up).

### Finding Inflection Points

1. Find where $f''(x) = 0$ or $f''(x)$ DNE — these are **candidates**
2. Check that $f''$ actually **changes sign** at that point
3. If it does, $(c, f(c))$ is an inflection point

> [!tip] Important
> $f''(c) = 0$ does NOT automatically mean $c$ is an inflection point. You must verify a sign change.
>
> Counterexample: $f(x) = x^4$. $f''(x) = 12x^2$, $f''(0) = 0$, but $f''$ is positive on both sides of $0$. No inflection point.

> [!example] Example 1
> $f(x) = x^3 - 3x^2 + 2$
>
> $f'(x) = 3x^2 - 6x$, $f''(x) = 6x - 6$
>
> $f''(x) = 0$: $x = 1$
>
> | Interval | $f''$ sign | Concavity |
> |---|---|---|
> | $(-\infty, 1)$ | $-$ | Down |
> | $(1, \infty)$ | $+$ | Up |
>
> $f''$ changes sign at $x = 1$. Inflection point: $(1, f(1)) = (1, 0)$.

> [!example] Example 2
> $f(x) = x^{1/3}$
>
> $f'(x) = \frac{1}{3}x^{-2/3}$, $f''(x) = -\frac{2}{9}x^{-5/3}$
>
> $f''$ is never zero but undefined at $x = 0$.
>
> $f''(-1) = \frac{2}{9} > 0$ (concave up), $f''(1) = -\frac{2}{9} < 0$ (concave down).
>
> Concavity changes at $x = 0$. Inflection point: $(0, 0)$.

> [!example] Example 3 — Full Analysis
> $f(x) = 3x^4 - 4x^3 + 1$
>
> $f''(x) = 36x^2 - 24x = 12x(3x - 2)$
>
> $f''(x) = 0$: $x = 0$ and $x = \frac{2}{3}$
>
> | Interval | $f''$ sign | Concavity |
> |---|---|---|
> | $(-\infty, 0)$ | $+$ | Up |
> | $(0, \frac{2}{3})$ | $-$ | Down |
> | $(\frac{2}{3}, \infty)$ | $+$ | Up |
>
> Two inflection points: $(0, 1)$ and $\left(\frac{2}{3}, \frac{11}{27}\right)$.

## Connection to the Second Derivative Test

At a critical number $c$ where $f'(c) = 0$:
- $f''(c) > 0$ means concave up at $c$ → local **min** (bottom of cup)
- $f''(c) < 0$ means concave down at $c$ → local **max** (top of cap)

This is exactly the [[First and Second Derivative Tests|Second Derivative Test]].

## See Also
- [[3.3 The Shape of Graphs]]
- [[First and Second Derivative Tests]]
- [[Higher-Order Derivatives]]
