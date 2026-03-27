---
section: "3.2"
date_covered: "2026-02-23"
textbook: "Stewart Calculus 9e"
tags: [calculus, derivatives, mean-value-theorem]
---

# Mean Value Theorem

> [!info] Deep Dive — The Mean Value Theorem
> Supporting topic for [[3.2 The Mean Value Theorem]].

## Rolle's Theorem

> [!thm] Rolle's Theorem
> If $f$ satisfies:
> 1. $f$ is continuous on $[a, b]$
> 2. $f$ is differentiable on $(a, b)$
> 3. $f(a) = f(b)$
>
> then there exists $c \in (a, b)$ such that $f'(c) = 0$.

**Geometric meaning:** If a continuous curve starts and ends at the same height, it must have a horizontal tangent somewhere in between.

### Proof Sketch

By the Extreme Value Theorem, $f$ attains its absolute max and min on $[a, b]$.

- If both occur at endpoints, then $f$ is constant on $[a, b]$, so $f'(c) = 0$ for all $c \in (a, b)$.
- If either the max or min occurs at an interior point $c$, then by Fermat's Theorem, $f'(c) = 0$. $\blacksquare$

> [!example] Example — Rolle's Theorem
> $f(x) = x^2 - 4x + 3$ on $[1, 3]$.
>
> Check: $f(1) = 0$, $f(3) = 0$. Continuous, differentiable. ✓
>
> $f'(x) = 2x - 4 = 0 \implies x = 2 \in (1, 3)$. ✓

## The Mean Value Theorem

> [!thm] Mean Value Theorem (MVT)
> If $f$ satisfies:
> 1. $f$ is continuous on $[a, b]$
> 2. $f$ is differentiable on $(a, b)$
>
> then there exists $c \in (a, b)$ such that
> $$f'(c) = \frac{f(b) - f(a)}{b - a}$$

**Geometric meaning:** There is a point where the tangent line is parallel to the secant line through $(a, f(a))$ and $(b, f(b))$.

**Physical meaning:** If you travel from A to B, at some instant your instantaneous velocity equals your average velocity.

### Proof

Define $g(x) = f(x) - \left[f(a) + \frac{f(b)-f(a)}{b-a}(x-a)\right]$ (subtract the secant line from $f$).

Then $g(a) = 0$ and $g(b) = 0$, $g$ is continuous on $[a,b]$ and differentiable on $(a,b)$.

By Rolle's Theorem, there exists $c \in (a,b)$ with $g'(c) = 0$:

$$g'(c) = f'(c) - \frac{f(b)-f(a)}{b-a} = 0 \implies f'(c) = \frac{f(b)-f(a)}{b-a} \quad \blacksquare$$

## Key Consequences

> [!thm] Consequence 1 — Zero Derivative ⟹ Constant
> If $f'(x) = 0$ for all $x$ in an interval $(a, b)$, then $f$ is constant on $(a, b)$.

*Proof.* For any $x_1, x_2 \in (a,b)$, MVT gives $f(x_2) - f(x_1) = f'(c)(x_2 - x_1) = 0$. $\blacksquare$

> [!thm] Consequence 2 — Equal Derivatives ⟹ Differ by Constant
> If $f'(x) = g'(x)$ for all $x$ in $(a,b)$, then $f(x) = g(x) + C$ for some constant $C$.

> [!thm] Consequence 3 — Positive Derivative ⟹ Increasing
> If $f'(x) > 0$ for all $x$ in $(a, b)$, then $f$ is increasing on $(a, b)$.
> If $f'(x) < 0$ for all $x$ in $(a, b)$, then $f$ is decreasing on $(a, b)$.

## Common Applications

**Proving uniqueness of roots:** If $f'(x) > 0$ on an interval, $f$ is strictly increasing, so it can cross zero at most once.

**Speed trap argument:** If you travel 80 miles in 1 hour, then at some instant you were going exactly 80 mph.

**Bounding function values:** If $|f'(x)| \le M$ on $[a,b]$, then $|f(b) - f(a)| \le M|b - a|$.

> [!example] Bounding Example
> Show $|\sin a - \sin b| \le |a - b|$ for all $a, b$.
>
> Let $f(x) = \sin x$. By MVT: $\sin a - \sin b = \cos(c)(a - b)$ for some $c$.
>
> Since $|\cos c| \le 1$: $|\sin a - \sin b| = |\cos c||a - b| \le |a - b|$. $\blacksquare$

## See Also
- [[3.2 The Mean Value Theorem]]
- [[Extreme Value Theorem and Fermats Theorem]]
- [[Critical Numbers]]
