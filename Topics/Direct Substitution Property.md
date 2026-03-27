---
section: "1.6"
date_covered:
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, limits]
---

# Direct Substitution Property

Direct substitution is the simplest and most common way to evaluate a limit: just plug $a$ into $f(x)$.

## Statement

> [!thm] Direct Substitution Property
> If $f$ is a polynomial or rational function and $a$ is in the domain of $f$, then
> $$\lim_{x\to a}f(x) = f(a).$$

## Why It Works

The proof builds directly from the [[Limit Laws]].

**Polynomials.** Every polynomial is a sum of terms $c_kx^k$. Using the basic limits
$$\lim_{x\to a}c = c, \qquad \lim_{x\to a}x = a$$
together with the Constant Multiple, Power, and Sum Laws:
$$\lim_{x\to a}(c_nx^n + c_{n-1}x^{n-1}+\cdots+c_1x+c_0) = c_na^n + c_{n-1}a^{n-1}+\cdots+c_1a+c_0 = p(a).$$

**Rational functions.** A rational function is $\frac{p(x)}{q(x)}$ where $p$ and $q$ are polynomials. If $a$ is in the domain, then $q(a)\neq 0$, so the Quotient Law applies:
$$\lim_{x\to a}\frac{p(x)}{q(x)} = \frac{p(a)}{q(a)}.$$

## Functions That Allow Direct Substitution

Direct substitution works for a much broader class than just polynomials and rationals. It works for any function that is **continuous** at $a$ (this is actually the *definition* of continuity, covered in Section 1.8).

> [!def] Functions supporting direct substitution
> The following functions allow direct substitution at every point in their domain:
> - **Polynomials:** $p(x) = c_nx^n + \cdots + c_0$ — all real numbers
> - **Rational functions:** $\frac{p(x)}{q(x)}$ — wherever $q(a)\neq 0$
> - **Root functions:** $\sqrt[n]{x}$ — on their natural domains
> - **Trigonometric functions:** $\sin x,\ \cos x,\ \tan x,\ \csc x,\ \sec x,\ \cot x$ — on their domains
> - **Exponential functions:** $b^x$, $e^x$ — all real numbers
> - **Logarithmic functions:** $\ln x$, $\log_b x$ — for $x > 0$
> - **Inverse trig functions:** $\arcsin x$, $\arctan x$, etc. — on their domains
>
> Furthermore, **sums, products, quotients, and compositions** of these functions support direct substitution at points in their domain, by the Limit Laws and the composition limit theorem.

> [!example] Direct substitution with composition
> $$\lim_{x\to\pi}\sin\!\left(\frac{x}{2}\right) = \sin\!\left(\frac{\pi}{2}\right) = 1$$
> This works because $\sin$ is continuous everywhere and $\frac{x}{2}$ is a polynomial.

## When Direct Substitution Fails: The $\frac{0}{0}$ Indeterminate Form

> [!tip] The $\frac{0}{0}$ signal
> If direct substitution gives $\frac{0}{0}$, it means:
> 1. The limit **might still exist** — you just can't find it by plugging in.
> 2. You need an algebraic technique: **factoring**, **rationalizing**, or **simplifying complex fractions**.
> 3. The $\frac{0}{0}$ form tells you the numerator and denominator share a common factor involving $(x-a)$.

> [!example] Example — Substitution fails, factoring succeeds
> Evaluate $\displaystyle\lim_{x\to 3}\frac{x^2-9}{x-3}$.
>
> Direct substitution: $\frac{9-9}{3-3} = \frac{0}{0}$. Fails.
>
> Factor: $\frac{x^2-9}{x-3} = \frac{(x-3)(x+3)}{x-3} = x+3$ for $x\neq 3$.
>
> $$\lim_{x\to 3}\frac{x^2-9}{x-3} = \lim_{x\to 3}(x+3) = 6.$$

> [!example] Example — Substitution fails, rationalizing succeeds
> Evaluate $\displaystyle\lim_{x\to 0}\frac{\sqrt{x+4}-2}{x}$.
>
> Direct substitution: $\frac{\sqrt{4}-2}{0} = \frac{0}{0}$. Fails.
>
> Multiply by the conjugate:
> $$\frac{\sqrt{x+4}-2}{x}\cdot\frac{\sqrt{x+4}+2}{\sqrt{x+4}+2} = \frac{(x+4)-4}{x(\sqrt{x+4}+2)} = \frac{1}{\sqrt{x+4}+2}$$
>
> $$\lim_{x\to 0}\frac{1}{\sqrt{x+4}+2} = \frac{1}{2+2} = \frac{1}{4}.$$

## Connection to Continuity

> [!def] Preview of Section 1.8
> A function $f$ is **continuous at $a$** if and only if
> $$\lim_{x\to a}f(x) = f(a).$$
>
> So saying "direct substitution works for $f$ at $a$" is exactly the same as saying "$f$ is continuous at $a$." The Direct Substitution Property is really the statement that polynomials, rationals (on their domain), trig functions, exponentials, and logarithms are all continuous on their domains.

> [!tip] Strategy
> **Always try direct substitution first.** It's the fastest method and works most of the time. Only when it produces $\frac{0}{0}$ (or another indeterminate form) should you switch to algebraic techniques.

## See Also

- [[1.6 Calculating Limits]]
- [[Limit Laws]]
- [[The Squeeze Theorem]]
