---
section: "2.3"
date_covered: [2026-01-27, 2026-01-29]
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, derivatives, differentiation-rules]
---

# The Power Rule

The Power Rule is the single most-used differentiation formula. It handles every function of the form $x^n$ — whether $n$ is a positive integer, negative integer, fraction, or any real number.

---

## Statement (Positive Integers)

> [!thm] Power Rule (positive integer version)
> If $n$ is a positive integer, then
> $$\frac{d}{dx}(x^n) = nx^{n-1}$$

### Proof (Limit Definition + Binomial Theorem)

We use the limit definition of the derivative:

$$f'(x) = \lim_{h\to 0}\frac{(x+h)^n - x^n}{h}$$

Expand $(x+h)^n$ using the **Binomial Theorem**:

$$(x+h)^n = x^n + nx^{n-1}h + \binom{n}{2}x^{n-2}h^2 + \cdots + h^n$$

Substituting:

$$f'(x) = \lim_{h\to 0}\frac{x^n + nx^{n-1}h + \binom{n}{2}x^{n-2}h^2 + \cdots + h^n - x^n}{h}$$

$$= \lim_{h\to 0}\frac{nx^{n-1}h + \binom{n}{2}x^{n-2}h^2 + \cdots + h^n}{h}$$

$$= \lim_{h\to 0}\left[nx^{n-1} + \binom{n}{2}x^{n-2}h + \cdots + h^{n-1}\right]$$

Every term after $nx^{n-1}$ contains a factor of $h$, so as $h\to 0$ they all vanish:

$$\boxed{f'(x) = nx^{n-1}}$$

---

## Extension to Negative Integers

> [!thm] Power Rule (negative integers)
> If $n$ is a negative integer, then $\frac{d}{dx}(x^n) = nx^{n-1}$ still holds (for $x\neq 0$).

### Proof

Write $n = -m$ where $m$ is a positive integer, so $x^n = x^{-m} = \dfrac{1}{x^m}$. Using the [[Product and Quotient Rules|Quotient Rule]]:

$$\frac{d}{dx}\left(\frac{1}{x^m}\right) = \frac{0\cdot x^m - 1\cdot mx^{m-1}}{(x^m)^2} = \frac{-mx^{m-1}}{x^{2m}} = -mx^{m-1-2m} = -mx^{-m-1}$$

Since $n = -m$, this is $nx^{n-1}$. $\blacksquare$

---

## Extension to Rational Exponents

> [!thm] Power Rule (rational exponents)
> If $n = \frac{p}{q}$ is any rational number, then
> $$\frac{d}{dx}(x^{p/q}) = \frac{p}{q}\,x^{p/q - 1}$$

The proof requires **implicit differentiation** (Section 2.6). The idea: if $y = x^{p/q}$, then $y^q = x^p$. Differentiate both sides implicitly and solve for $\frac{dy}{dx}$.

---

## Extension to All Real Exponents

> [!thm] Power Rule (general version)
> If $n$ is **any real number**, then
> $$\frac{d}{dx}(x^n) = nx^{n-1}$$

The full proof uses logarithmic differentiation (Section 3.6). For now, we accept and use the result for all real $n$.

---

## Common Mistakes

> [!tip] Watch out for these errors
> 1. **Forgetting to subtract 1 from the exponent.** $\frac{d}{dx}(x^5) = 5x^4$, NOT $5x^5$.
> 2. **Forgetting the coefficient.** $\frac{d}{dx}(x^5) = 5x^4$, NOT $x^4$.
> 3. **Not rewriting before differentiating.** You must express roots and reciprocals as powers of $x$ before applying the power rule. For example, $\sqrt{x} = x^{1/2}$ and $\frac{1}{x^3} = x^{-3}$.

---

## Worked Examples

> [!example] Example 1: Derivative of $\sqrt{x}$
> Rewrite: $\sqrt{x} = x^{1/2}$
>
> $$\frac{d}{dx}(x^{1/2}) = \frac{1}{2}x^{1/2 - 1} = \frac{1}{2}x^{-1/2} = \frac{1}{2\sqrt{x}}$$

> [!example] Example 2: Derivative of $x^{-2}$
> $$\frac{d}{dx}(x^{-2}) = -2x^{-2-1} = -2x^{-3} = \frac{-2}{x^3}$$

> [!example] Example 3: Derivative of $x^{2/3}$
> $$\frac{d}{dx}(x^{2/3}) = \frac{2}{3}x^{2/3 - 1} = \frac{2}{3}x^{-1/3} = \frac{2}{3\sqrt[3]{x}}$$

> [!example] Example 4: Derivative of $\dfrac{1}{\sqrt[3]{x}}$
> Rewrite: $\dfrac{1}{\sqrt[3]{x}} = x^{-1/3}$
>
> $$\frac{d}{dx}(x^{-1/3}) = -\frac{1}{3}x^{-1/3 - 1} = -\frac{1}{3}x^{-4/3} = \frac{-1}{3x^{4/3}}$$

> [!example] Example 5: Derivative of $x^{\pi}$
> Even irrational exponents work:
>
> $$\frac{d}{dx}(x^{\pi}) = \pi x^{\pi - 1}$$

---

## See Also

- [[2.3 Differentiation Rules]]
- [[Product and Quotient Rules]]
