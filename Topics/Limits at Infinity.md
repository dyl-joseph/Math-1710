---
section: "3.4"
date_covered: "2026-03-02"
textbook: "Stewart Calculus 9e"
tags: [calculus, limits, asymptotes]
---

# Limits at Infinity

> [!info] Deep Dive — Limits at Infinity
> Supporting topic for [[3.4 Limits at Infinity and Horizontal Asymptotes]].

## Definition

> [!def] Limit at Infinity
> $\lim_{x \to \infty} f(x) = L$ means $f(x)$ gets arbitrarily close to $L$ as $x$ grows without bound.
>
> $\lim_{x \to -\infty} f(x) = L$ means $f(x)$ gets arbitrarily close to $L$ as $x$ decreases without bound.

> [!def] Horizontal Asymptote
> The line $y = L$ is a **horizontal asymptote** of $f$ if
> $$\lim_{x \to \infty} f(x) = L \quad \text{or} \quad \lim_{x \to -\infty} f(x) = L$$

A function can have 0, 1, or 2 horizontal asymptotes.

## Precise Definition

> [!def] Formal (Epsilon) Definition
> $\lim_{x \to \infty} f(x) = L$ means: for every $\varepsilon > 0$, there exists $N$ such that
> $$x > N \implies |f(x) - L| < \varepsilon$$

## Fundamental Limits

$$\lim_{x \to \infty} \frac{1}{x^n} = 0 \quad \text{for } n > 0$$

$$\lim_{x \to -\infty} \frac{1}{x^n} = 0 \quad \text{for } n > 0 \text{ (where defined)}$$

These are the building blocks — most limits at infinity reduce to these.

## Techniques for Rational Functions

### The "Divide by Highest Power" Method

For $\lim_{x \to \pm\infty} \frac{P(x)}{Q(x)}$ where $P$ and $Q$ are polynomials: **divide numerator and denominator by the highest power of $x$ in the denominator**.

> [!example] Example 1
> $$\lim_{x \to \infty} \frac{3x^2 - x + 4}{5x^2 + 2x - 1}$$
>
> Divide by $x^2$:
> $$= \lim_{x \to \infty} \frac{3 - \frac{1}{x} + \frac{4}{x^2}}{5 + \frac{2}{x} - \frac{1}{x^2}} = \frac{3 - 0 + 0}{5 + 0 - 0} = \frac{3}{5}$$

### The Shortcut Rule

For $\frac{a_nx^n + \cdots}{b_mx^m + \cdots}$:

| Comparison | Limit | HA |
|---|---|---|
| $n < m$ (degree top < bottom) | $0$ | $y = 0$ |
| $n = m$ (equal degrees) | $\frac{a_n}{b_m}$ | $y = \frac{a_n}{b_m}$ |
| $n > m$ (degree top > bottom) | $\pm\infty$ | None |

> [!tip] Memory Aid
> **"Bottom heavy → 0, Equal → ratio of leading coefficients, Top heavy → ∞"**

> [!example] Example 2 — Bottom Heavy
> $$\lim_{x \to \infty} \frac{2x + 1}{x^3 - 5} = 0$$

> [!example] Example 3 — Top Heavy
> $$\lim_{x \to \infty} \frac{x^3 + 1}{2x - 7} = \infty$$

## Non-Rational Functions

### Square Roots

Divide by $|x| = \sqrt{x^2}$ (be careful with sign when $x \to -\infty$).

> [!example] Example 4
> $$\lim_{x \to \infty} \frac{\sqrt{4x^2 + 3}}{x + 1}$$
>
> For $x > 0$: $\sqrt{4x^2+3} = x\sqrt{4 + \frac{3}{x^2}}$
>
> $$= \lim_{x \to \infty} \frac{x\sqrt{4 + \frac{3}{x^2}}}{x + 1} = \lim_{x \to \infty} \frac{\sqrt{4 + \frac{3}{x^2}}}{1 + \frac{1}{x}} = \frac{2}{1} = 2$$

> [!example] Example 5 — Watch the Sign at $-\infty$
> $$\lim_{x \to -\infty} \frac{\sqrt{4x^2 + 3}}{x + 1}$$
>
> For $x < 0$: $\sqrt{x^2} = |x| = -x$, so $\sqrt{4x^2+3} = -x\sqrt{4 + \frac{3}{x^2}}$
>
> $$= \lim_{x \to -\infty} \frac{-x\sqrt{4 + \frac{3}{x^2}}}{x + 1} = \frac{-\sqrt{4}}{1} = -2$$
>
> Two different horizontal asymptotes: $y = 2$ (right) and $y = -2$ (left).

### Exponentials

$$\lim_{x \to \infty} e^x = \infty, \quad \lim_{x \to -\infty} e^x = 0$$

$$\lim_{x \to \infty} e^{-x} = 0, \quad \lim_{x \to -\infty} e^{-x} = \infty$$

> [!example] Example 6
> $$\lim_{x \to \infty} \frac{e^x}{e^x + 1}$$
>
> Divide by $e^x$: $= \lim_{x \to \infty} \frac{1}{1 + e^{-x}} = \frac{1}{1 + 0} = 1$

### Trig Functions

$\sin x$ and $\cos x$ oscillate — $\lim_{x \to \infty}\sin x$ does **not exist**.

But bounded oscillation divided by growing function → 0:

$$\lim_{x \to \infty} \frac{\sin x}{x} = 0 \quad \text{(Squeeze Theorem)}$$

## Infinite Limits at Infinity

> [!def] Infinite Limit at Infinity
> $\lim_{x \to \infty} f(x) = \infty$ means $f(x)$ grows without bound as $x \to \infty$.

For polynomials $f(x) = a_nx^n + \cdots$ with $a_n \neq 0$:
- $\lim_{x \to \infty} f(x)$ depends on $a_n$ and whether $n$ is even/odd
- Leading term dominates: $\lim_{x \to \pm\infty} f(x) = \lim_{x \to \pm\infty} a_nx^n$

## See Also
- [[3.4 Limits at Infinity and Horizontal Asymptotes]]
- [[Infinite Limits and Vertical Asymptotes]] — vertical asymptotes (different concept)
- [[The Squeeze Theorem]] — used for oscillating functions
