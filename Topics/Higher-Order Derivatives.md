---
section: "2.2"
date_covered:
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, derivatives]
---

# Higher-Order Derivatives

Because the derivative $f'$ is itself a function, we can differentiate it again — and again. Each successive derivative tells us about the rate of change of the previous one.

---

## Second Derivative

> [!def] Second Derivative
> The **second derivative** of $f$ is the derivative of $f'$:
> $$f''(x) = (f')'(x) = \lim_{h\to 0}\frac{f'(x+h)-f'(x)}{h}$$

### Notation

| Notation | Read as |
|----------|---------|
| $f''(x)$ | "$f$ double prime of $x$" |
| $y''$ | "$y$ double prime" |
| $\dfrac{d^2y}{dx^2}$ | "dee-two-$y$ over dee-$x$-squared" |
| $\dfrac{d^2f}{dx^2}$ | "dee-two-$f$ over dee-$x$-squared" |
| $D^2 f(x)$ | "$D$-squared $f$ of $x$" |

> [!tip] Understanding $\frac{d^2y}{dx^2}$
> This notation comes from applying the operator $\frac{d}{dx}$ twice:
> $$\frac{d^2y}{dx^2} = \frac{d}{dx}\!\left(\frac{dy}{dx}\right)$$
> Think of $(dx)^2$ in the denominator as the operator $d/dx$ applied to $dy/dx$.

---

## Physical Interpretation

If $s(t)$ is the position of an object at time $t$, then:

| Derivative | Meaning |
|-----------|---------|
| $s'(t) = v(t)$ | **Velocity** — rate of change of position |
| $s''(t) = v'(t) = a(t)$ | **Acceleration** — rate of change of velocity |

> [!example] Falling Object
> A ball dropped from rest has position $s(t)=4.9t^2$ (metres, with downward positive).
>
> - Velocity: $s'(t)=9.8t$ m/s
> - Acceleration: $s''(t)=9.8$ m/s$^2$ (constant — gravitational acceleration)

Acceleration measures how the velocity is changing. When $a(t)>0$, velocity is increasing; when $a(t)<0$, velocity is decreasing (the object is decelerating).

---

## Third and Higher Derivatives

Differentiating repeatedly:

| Order | Notation (function) | Notation (Leibniz) |
|-------|--------------------|--------------------|
| 1st | $f'(x)$ | $\dfrac{dy}{dx}$ |
| 2nd | $f''(x)$ | $\dfrac{d^2y}{dx^2}$ |
| 3rd | $f'''(x)$ | $\dfrac{d^3y}{dx^3}$ |
| $n$th | $f^{(n)}(x)$ | $\dfrac{d^ny}{dx^n}$ |

> [!tip] Parentheses in $f^{(n)}$
> For $n\ge 4$, we write $f^{(n)}(x)$ instead of adding more primes. The parentheses distinguish the derivative order from an exponent: $f^{(4)}(x)$ is the fourth derivative, not $f$ raised to the fourth power.

The third derivative $s'''(t)$ of position is called the **jerk** — it measures the rate of change of acceleration.

---

## Worked Example

> [!example] Finding Higher Derivatives of a Polynomial
> Let $f(x) = x^4 - 3x^3 + 2x^2 - x + 5$.
>
> Using the limit definition (or derivative rules from later sections):
>
> $$f'(x) = 4x^3 - 9x^2 + 4x - 1$$
>
> $$f''(x) = 12x^2 - 18x + 4$$
>
> $$f'''(x) = 24x - 18$$
>
> $$f^{(4)}(x) = 24$$
>
> $$f^{(5)}(x) = 0$$
>
> Every subsequent derivative is also $0$. In general, a degree-$n$ polynomial has $f^{(n+1)}(x)=0$.

---

## Connection to Concavity (Preview)

The second derivative gives geometric information about the graph of $f$:

- $f''(x) > 0$ on an interval ⟹ $f$ is **concave up** there (curves upward, "holds water")
- $f''(x) < 0$ on an interval ⟹ $f$ is **concave down** there (curves downward)
- Where $f''(x)$ changes sign, $f$ has an **inflection point**

This will be explored in detail in **Section 3.3**.

---

## See Also

- [[2.2 The Derivative as a Function]] — the derivative as a function and the limit definition
- [[Differentiability]] — when derivatives exist
