---
section: "3.9"
date_covered: "2026-03-23"
textbook: "Stewart Calculus 9e"
tags: [calculus, antiderivatives, integration]
---

# Antiderivative Rules

> [!info] Deep Dive — Antiderivative Rules
> Supporting topic for [[3.9 Antiderivatives]].

## Basic Antiderivative Table

> [!thm] Table of Antiderivatives
>
> | Function $f(x)$ | Antiderivative $F(x)$ |
> |---|---|
> | $x^n$ ($n \neq -1$) | $\frac{x^{n+1}}{n+1} + C$ |
> | $\frac{1}{x}$ | $\ln\|x\| + C$ |
> | $e^x$ | $e^x + C$ |
> | $\cos x$ | $\sin x + C$ |
> | $\sin x$ | $-\cos x + C$ |
> | $\sec^2 x$ | $\tan x + C$ |
> | $\csc^2 x$ | $-\cot x + C$ |
> | $\sec x \tan x$ | $\sec x + C$ |
> | $\csc x \cot x$ | $-\csc x + C$ |

Each entry can be verified by differentiating $F(x)$ to get $f(x)$.

## Key Rules

> [!thm] Constant Multiple Rule
> $$\int cf(x)\,dx = c\int f(x)\,dx$$

> [!thm] Sum/Difference Rule
> $$\int [f(x) \pm g(x)]\,dx = \int f(x)\,dx \pm \int g(x)\,dx$$

> [!tip] No Product or Quotient Rule for Antiderivatives
> Unlike derivatives, there is **no** simple antiderivative rule for products or quotients. You must simplify first (expand, divide, rewrite) before antidifferentiating.

## Common Rewrites

Many functions need to be rewritten before applying the power rule:

| Original | Rewrite | Antiderivative |
|---|---|---|
| $\sqrt{x}$ | $x^{1/2}$ | $\frac{2}{3}x^{3/2} + C$ |
| $\frac{1}{x^2}$ | $x^{-2}$ | $-x^{-1} + C = -\frac{1}{x} + C$ |
| $\frac{1}{\sqrt{x}}$ | $x^{-1/2}$ | $2x^{1/2} + C = 2\sqrt{x} + C$ |
| $\sqrt[3]{x^2}$ | $x^{2/3}$ | $\frac{3}{5}x^{5/3} + C$ |
| $\frac{x^2 + 1}{x}$ | $x + x^{-1}$ | $\frac{x^2}{2} + \ln|x| + C$ |

> [!example] Example — Expand Before Integrating
> $$\int (3x + 2)^2\,dx = \int (9x^2 + 12x + 4)\,dx = 3x^3 + 6x^2 + 4x + C$$
>
> (Note: you could also use substitution, covered in Section 4.5, but expanding works here.)

> [!example] Example — Divide First
> $$\int \frac{x^3 + 2x}{x^2}\,dx = \int \left(x + 2x^{-1}\right)\,dx = \frac{x^2}{2} + 2\ln|x| + C$$

## The Power Rule Pitfall: $n = -1$

$$\int x^{-1}\,dx = \int \frac{1}{x}\,dx = \ln|x| + C$$

The power rule formula $\frac{x^{n+1}}{n+1}$ gives $\frac{x^0}{0}$, which is undefined. This is the one exception — memorize it separately.

## Verifying Antiderivatives

> [!tip] Always Check by Differentiating
> If $\int f(x)\,dx = F(x) + C$, then $F'(x)$ should equal $f(x)$. This is the quickest way to catch errors.

## See Also
- [[3.9 Antiderivatives]]
- [[Power Rule]] — the derivative version
- [[Derivatives of Sine and Cosine]] — reverse these for trig antiderivatives
