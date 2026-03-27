---
section: "3.7"
date_covered: "2026-03-16"
textbook: "Stewart Calculus 9e"
tags: [calculus, derivatives, optimization]
---

# Optimization Problem-Solving Strategy

> [!info] Deep Dive — Optimization Strategy
> Supporting topic for [[3.7 Optimization]].

## Step-by-Step Procedure

> [!def] Optimization Algorithm
> 1. **Read** the problem. Identify what quantity is to be maximized or minimized.
> 2. **Draw a diagram** if applicable. Label all relevant quantities.
> 3. **Assign variables.** Let the quantity to optimize be $Q$.
> 4. **Write $Q$ as a function** of one or more variables.
> 5. **Use constraints** to eliminate variables until $Q$ depends on a **single variable**: $Q = f(x)$.
> 6. **Determine the domain** of $f$ (realistic values of $x$).
> 7. **Find the absolute max or min** of $f$ on that domain:
>    - If closed interval $[a,b]$: use the Closed Interval Method
>    - If open interval or all of $\mathbb{R}$: find critical numbers, verify with First/Second Derivative Test, check endpoint behavior
> 8. **Answer the question** asked (they may want the optimal value, the optimal dimensions, etc.)

## Common Constraint Equations

| Problem Type | Typical Constraint |
|---|---|
| Fencing / perimeter | $2l + 2w = P$ (fixed perimeter) |
| Box with fixed material | $2lw + 2wh + 2lh = S$ (fixed surface area) |
| Box with open top | $lw + 2wh + 2lh = S$ |
| Can (cylinder) | $2\pi r^2 + 2\pi rh = S$ |
| Distance | $d = \sqrt{(x-a)^2 + (y-b)^2}$ |
| Points on a curve | $y = f(x)$ relates coordinates |

> [!tip] Minimize Distance² Instead of Distance
> Since $\sqrt{\cdot}$ is increasing, the value of $x$ that minimizes $d^2 = (x-a)^2 + (y-b)^2$ also minimizes $d$. This avoids dealing with square roots in the derivative.

## Verifying You Found a Max/Min

On a **closed interval** $[a, b]$: the Closed Interval Method guarantees you find the absolute extrema.

On an **open interval** or $\mathbb{R}$: you need additional justification. Common approaches:

> [!thm] First Derivative Test for Absolute Extrema
> If $f$ has only **one** critical number $c$ on an interval, and it's a local max (or min), then it's the **absolute** max (or min) on that interval.

> [!thm] Second Derivative Test
> If $f'(c) = 0$ and $f''(c) > 0$, then $c$ gives a local min. If it's the only critical number, it's the absolute min.

**Or:** Check that $f(x) \to \infty$ (or some large value) at the endpoints/limits of the domain, confirming the critical point gives the minimum.

## Worked Examples

> [!example] Example 1 — Two Numbers
> Find two positive numbers whose sum is 100 and whose product is maximized.
>
> Let $x$ and $y = 100 - x$ be the numbers. $P = xy = x(100-x) = 100x - x^2$.
>
> Domain: $0 < x < 100$.
>
> $P'(x) = 100 - 2x = 0 \implies x = 50$. $P''(x) = -2 < 0$ → max.
>
> The numbers are $50$ and $50$. Max product: $2500$.

> [!example] Example 2 — Farmer's Fence (Classic)
> A farmer has 400 m of fencing to enclose a rectangular field next to a river (no fence on river side). Maximize the area.
>
> Constraint: $x + 2y = 400$ (one length, two widths). So $x = 400 - 2y$.
>
> $A = xy = (400-2y)y = 400y - 2y^2$. Domain: $0 < y < 200$.
>
> $A'(y) = 400 - 4y = 0 \implies y = 100$. Then $x = 200$.
>
> $A''(y) = -4 < 0$ → max. Maximum area: $200 \times 100 = 20{,}000$ m².

> [!example] Example 3 — Open-Top Box
> A box with square base and open top must have volume 32,000 cm³. Find dimensions that minimize surface area.
>
> Let base side $= x$, height $= h$. Constraint: $x^2h = 32000 \implies h = \frac{32000}{x^2}$.
>
> $S = x^2 + 4xh = x^2 + 4x \cdot \frac{32000}{x^2} = x^2 + \frac{128000}{x}$
>
> Domain: $x > 0$.
>
> $S'(x) = 2x - \frac{128000}{x^2} = 0 \implies 2x^3 = 128000 \implies x = 40$
>
> $h = \frac{32000}{1600} = 20$. $S''(40) = 2 + \frac{256000}{64000} = 6 > 0$ → min.
>
> Dimensions: $40 \times 40 \times 20$ cm.

> [!example] Example 4 — Closest Point on a Curve
> Find the point on $y = \sqrt{x}$ closest to $(3, 0)$.
>
> Minimize $D^2 = (x-3)^2 + (\sqrt{x})^2 = (x-3)^2 + x = x^2 - 5x + 9$.
>
> Domain: $x \ge 0$.
>
> $\frac{d}{dx}(D^2) = 2x - 5 = 0 \implies x = \frac{5}{2}$. $y = \sqrt{\frac{5}{2}}$.
>
> $\frac{d^2}{dx^2}(D^2) = 2 > 0$ → min.
>
> Closest point: $\left(\frac{5}{2}, \sqrt{\frac{5}{2}}\right)$.

## Common Mistakes

> [!tip] Watch Out
> - **Not checking the domain.** Physical constraints mean $x$ can't be negative, dimensions can't exceed totals, etc.
> - **Forgetting to answer the actual question.** If they ask for dimensions, give $x$ AND $y$ (and $h$, etc.). If they ask for the maximum value, plug back in.
> - **Not verifying max vs min.** Just finding $f'(c) = 0$ isn't enough — confirm it's the type of extremum you want.
> - **Using the wrong constraint.** Re-read the problem to make sure you're using the right fixed quantity.

## See Also
- [[3.7 Optimization]]
- [[Critical Numbers]]
- [[First and Second Derivative Tests]]
- [[3.1 Maximum and Minimum Values]]
