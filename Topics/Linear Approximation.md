---
section: "2.9"
date_covered: "2026-02-16"
textbook: "Stewart Calculus 9e"
tags: [calculus, derivatives, linearization]
---

# Linear Approximation

> [!info] Deep Dive — Linear Approximation and Differentials
> Supporting topic for [[2.9 Linearization and Differentials]].

## The Idea

Near a point $x = a$, the tangent line is a good approximation to the curve. The closer $x$ is to $a$, the better the approximation.

> [!def] Linearization
> The **linearization** of $f$ at $a$ is the tangent line function:
> $$L(x) = f(a) + f'(a)(x - a)$$
> The approximation $f(x) \approx L(x)$ is called the **linear approximation** (or **tangent line approximation**) of $f$ near $a$.

This is just the tangent line in point-slope form, rewritten as a function.

## Why It Works

By definition of the derivative, $f(x) \approx f(a) + f'(a)(x-a)$ when $x$ is close to $a$. More precisely:

$$\lim_{x \to a} \frac{f(x) - [f(a) + f'(a)(x-a)]}{x - a} = 0$$

The error goes to zero faster than $x - a$ itself — we say the error is $o(x-a)$.

## Standard Linearizations at $a = 0$

These are worth memorizing for quick approximations:

| Function | Linearization near $0$ |
|---|---|
| $(1+x)^n$ | $1 + nx$ |
| $\sin x$ | $x$ |
| $\cos x$ | $1$ |
| $\tan x$ | $x$ |
| $e^x$ | $1 + x$ |
| $\ln(1+x)$ | $x$ |
| $\frac{1}{1+x}$ | $1 - x$ |

> [!example] Example — Approximate $\sqrt{4.02}$
> Let $f(x) = \sqrt{x}$, $a = 4$. Then $f(4) = 2$, $f'(x) = \frac{1}{2\sqrt{x}}$, $f'(4) = \frac{1}{4}$.
>
> $L(x) = 2 + \frac{1}{4}(x - 4)$
>
> $\sqrt{4.02} \approx L(4.02) = 2 + \frac{1}{4}(0.02) = 2.005$
>
> Actual value: $2.00499...\,$ — excellent approximation!

> [!example] Example — Approximate $\sin(0.1)$
> Using the linearization $\sin x \approx x$ near $0$:
>
> $\sin(0.1) \approx 0.1$
>
> Actual: $0.09983...\,$ — error less than $0.002$.

> [!example] Example — Approximate $(1.01)^{10}$
> Use $(1+x)^n \approx 1 + nx$ with $x = 0.01$, $n = 10$:
>
> $(1.01)^{10} \approx 1 + 10(0.01) = 1.1$
>
> Actual: $1.10462...\,$ — reasonable for a quick estimate.

## When Is the Approximation Good?

- Works best when $x$ is **close to $a$**
- Works better when $|f''|$ is **small** near $a$ (less curvature = more linear)
- Can quantify error with Taylor's theorem: $|f(x) - L(x)| \le \frac{M}{2}(x-a)^2$ where $M = \max|f''|$

## Differentials

> [!def] Differentials
> Let $y = f(x)$ be differentiable. The **differential** $dx$ is an independent variable. The **differential** $dy$ is defined by:
> $$dy = f'(x)\,dx$$

Geometric meaning:
- $\Delta x = dx$ is the actual change in $x$
- $\Delta y = f(x + dx) - f(x)$ is the actual change in $y$
- $dy = f'(x)\,dx$ is the change along the **tangent line**
- $dy \approx \Delta y$ when $dx$ is small

> [!example] Example — Differentials
> $y = x^3 + 2x$. Find $dy$ when $x = 2$ and $dx = 0.1$.
>
> $dy = (3x^2 + 2)\,dx = (3(4) + 2)(0.1) = 14(0.1) = 1.4$
>
> Actual change: $f(2.1) - f(2) = (9.261 + 4.2) - (8 + 4) = 13.461 - 12 = 1.461$
>
> Approximation error: $|1.461 - 1.4| = 0.061$

## Applications of Differentials

**Error propagation:** If a measurement $x$ has error $dx$, then the error in $f(x)$ is approximately $dy = f'(x)\,dx$.

**Relative error:** $\frac{dy}{y} = \frac{f'(x)}{f(x)}\,dx$. Percentage error is $\frac{dy}{y} \times 100\%$.

> [!example] Error Propagation
> A sphere's radius is measured as $r = 10$ cm with error $dr = \pm 0.1$ cm. Estimate the error in volume.
>
> $V = \frac{4}{3}\pi r^3$, so $dV = 4\pi r^2\,dr = 4\pi(100)(0.1) = 40\pi \approx 125.7$ cm³
>
> Relative error: $\frac{dV}{V} = \frac{4\pi r^2\,dr}{\frac{4}{3}\pi r^3} = \frac{3\,dr}{r} = \frac{3(0.1)}{10} = 0.03 = 3\%$

## See Also
- [[2.9 Linearization and Differentials]]
- [[Tangent Lines and Secant Lines]]
- [[Differentiability]]
