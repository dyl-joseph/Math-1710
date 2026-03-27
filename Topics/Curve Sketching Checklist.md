---
section: "3.5"
date_covered: "2026-03-03"
textbook: "Stewart Calculus 9e"
tags: [calculus, derivatives, curve-sketching]
---

# Curve Sketching Checklist

> [!info] Deep Dive — Systematic Curve Sketching
> Supporting topic for [[3.5 Curve Sketching]].

## The Complete Checklist

> [!def] Curve Sketching Procedure
> For $y = f(x)$, analyze the following (in order):
>
> **A. Domain** — What values of $x$ are allowed?
>
> **B. Intercepts**
> - $y$-intercept: set $x = 0$, find $f(0)$
> - $x$-intercepts: set $y = 0$, solve $f(x) = 0$ (if feasible)
>
> **C. Symmetry**
> - Even: $f(-x) = f(x)$ → symmetric about $y$-axis
> - Odd: $f(-x) = -f(x)$ → symmetric about origin
> - Periodic: $f(x + T) = f(x)$ → only sketch one period
>
> **D. Asymptotes**
> - Horizontal: $\lim_{x \to \pm\infty} f(x)$
> - Vertical: where denominator $= 0$ (check with sign analysis)
> - Slant: if degree of numerator = degree of denominator + 1, do polynomial long division
>
> **E. Intervals of increase/decrease**
> - Find $f'(x)$, critical numbers, sign chart
>
> **F. Local extrema**
> - Apply First or Second Derivative Test at critical numbers
>
> **G. Concavity and inflection points**
> - Find $f''(x)$, sign chart, identify where concavity changes
>
> **H. Sketch**
> - Plot key points (intercepts, extrema, inflection points)
> - Draw asymptotes as dashed lines
> - Connect using increase/decrease and concavity information

## Slant (Oblique) Asymptotes

> [!def] Slant Asymptote
> $y = mx + b$ is a **slant asymptote** if $\lim_{x \to \pm\infty}[f(x) - (mx + b)] = 0$.
>
> This occurs for rational functions when degree of numerator = degree of denominator + 1.

**How to find:** Perform polynomial long division. The quotient (ignoring remainder) is the slant asymptote.

> [!example] Example
> $f(x) = \frac{x^2 + 1}{x - 1}$
>
> Long division: $\frac{x^2+1}{x-1} = x + 1 + \frac{2}{x-1}$
>
> Slant asymptote: $y = x + 1$ (the remainder $\frac{2}{x-1} \to 0$).

## Worked Example — Full Analysis

> [!example] Complete Curve Sketch: $f(x) = \frac{x^2}{x^2 - 4}$
>
> **A. Domain:** $x \neq \pm 2$, i.e., $(-\infty, -2) \cup (-2, 2) \cup (2, \infty)$
>
> **B. Intercepts:**
> - $y$-intercept: $f(0) = 0$
> - $x$-intercept: $x^2 = 0 \implies x = 0$
>
> **C. Symmetry:** $f(-x) = \frac{(-x)^2}{(-x)^2-4} = \frac{x^2}{x^2-4} = f(x)$. **Even** — symmetric about $y$-axis.
>
> **D. Asymptotes:**
> - Vertical: $x = 2$ and $x = -2$
> - Horizontal: $\lim_{x \to \pm\infty}\frac{x^2}{x^2-4} = 1$, so HA: $y = 1$
>
> **E. First derivative:**
> $$f'(x) = \frac{2x(x^2-4) - x^2(2x)}{(x^2-4)^2} = \frac{-8x}{(x^2-4)^2}$$
> Critical number: $x = 0$
>
> | Interval | $f'$ sign | Behavior |
> |---|---|---|
> | $(-\infty, -2)$ | $+$ | Increasing |
> | $(-2, 0)$ | $+$ | Increasing |
> | $(0, 2)$ | $-$ | Decreasing |
> | $(2, \infty)$ | $-$ | Decreasing |
>
> **F. Local extrema:** Local max at $x = 0$, $f(0) = 0$.
>
> **G. Second derivative:**
> $$f''(x) = \frac{8(3x^2+4)}{(x^2-4)^3}$$
> $3x^2+4 > 0$ always. Sign depends on $(x^2-4)^3$:
> - $|x| < 2$: $(x^2-4)^3 < 0$ → concave down
> - $|x| > 2$: $(x^2-4)^3 > 0$ → concave up
> No inflection points (concavity changes at VAs, not at points on the curve).
>
> **H. Key features:** Local max $(0, 0)$, VAs $x = \pm 2$, HA $y = 1$, symmetric about $y$-axis. Curve approaches $y = 1$ from above for $|x| > 2$ and from below for $|x| < 2$.

## Another Worked Example

> [!example] Complete Curve Sketch: $f(x) = xe^{-x^2/2}$
>
> **A. Domain:** All $\mathbb{R}$
>
> **B. Intercepts:** $f(0) = 0$. $x$-intercept at $x = 0$.
>
> **C. Symmetry:** $f(-x) = -xe^{-x^2/2} = -f(x)$. **Odd** — symmetric about origin.
>
> **D. Asymptotes:** $\lim_{x \to \pm\infty} xe^{-x^2/2} = 0$ (exponential beats polynomial). HA: $y = 0$.
>
> **E. First derivative:**
> $$f'(x) = e^{-x^2/2} + x(-x)e^{-x^2/2} = e^{-x^2/2}(1 - x^2)$$
> $f'(x) = 0$: $x = \pm 1$
>
> | Interval | $f'$ sign | Behavior |
> |---|---|---|
> | $(-\infty, -1)$ | $-$ | Decreasing |
> | $(-1, 1)$ | $+$ | Increasing |
> | $(1, \infty)$ | $-$ | Decreasing |
>
> **F.** Local min at $(-1, -e^{-1/2})$. Local max at $(1, e^{-1/2})$.
>
> **G. Second derivative:**
> $$f''(x) = e^{-x^2/2}(x^3 - 3x) = xe^{-x^2/2}(x^2 - 3)$$
> $f''(x) = 0$: $x = 0, \pm\sqrt{3}$. All three are inflection points (sign changes confirmed).
>
> **H.** Bell-curve-like shape (odd version), local max at $(1, e^{-1/2} \approx 0.607)$, local min at $(-1, -0.607)$, three inflection points, approaches $x$-axis at both ends.

## Tips for Exams

> [!tip] Practical Advice
> - **You don't always need every step.** If the problem just asks to sketch, focus on the most informative features (extrema, asymptotes, end behavior).
> - **Use symmetry** to cut work in half — if $f$ is even, analyze $x \ge 0$ and reflect.
> - **Asymptote behavior:** determine if the function approaches from above or below by checking sign near the asymptote.
> - **Don't compute $f''$ if not asked** — it's often the most tedious step. Only do it if the problem asks for concavity or if you need the Second Derivative Test.

## See Also
- [[3.5 Curve Sketching]]
- [[First and Second Derivative Tests]]
- [[Concavity and Inflection Points]]
- [[Limits at Infinity]]
- [[Infinite Limits and Vertical Asymptotes]]
