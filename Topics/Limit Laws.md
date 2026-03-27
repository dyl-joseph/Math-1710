---
section: "1.6"
date_covered:
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, limits]
---

# Limit Laws

The Limit Laws are the algebraic backbone of limit computation. They let us break a complicated limit into simple pieces, evaluate each piece, and recombine.

## The Laws

Suppose $\lim_{x\to a} f(x) = L$ and $\lim_{x\to a} g(x) = M$ both exist. Let $c$ be a constant. Then:

> [!thm] Law 1 — Sum Law
> $$\lim_{x\to a}[f(x)+g(x)] = L + M$$
> The limit of a sum is the sum of the limits.

> [!thm] Law 2 — Difference Law
> $$\lim_{x\to a}[f(x)-g(x)] = L - M$$
> The limit of a difference is the difference of the limits.

> [!thm] Law 3 — Constant Multiple Law
> $$\lim_{x\to a}[c\cdot f(x)] = c\cdot L$$
> Constants factor out of limits.

> [!thm] Law 4 — Product Law
> $$\lim_{x\to a}[f(x)\cdot g(x)] = L\cdot M$$
> The limit of a product is the product of the limits.

> [!thm] Law 5 — Quotient Law
> $$\lim_{x\to a}\frac{f(x)}{g(x)} = \frac{L}{M}, \quad \text{provided } M \neq 0$$
> The limit of a quotient is the quotient of the limits, **as long as the denominator limit is not zero**.

> [!thm] Law 6 — Power Law
> $$\lim_{x\to a}[f(x)]^n = L^n$$
> where $n$ is a positive integer.

> [!thm] Law 7 — Root Law
> $$\lim_{x\to a}\sqrt[n]{f(x)} = \sqrt[n]{L}$$
> where $n$ is a positive integer. If $n$ is even, we additionally require $L > 0$ (or $L \geq 0$ if we want the limit to exist in the usual real-valued sense).

## Why the Laws Matter

Every polynomial and rational function is built by adding, subtracting, multiplying, and dividing constants and the variable $x$. The Limit Laws guarantee that we can evaluate limits of such functions by simply plugging in — this is the [[Direct Substitution Property]].

More broadly, the laws let us decompose any limit built from known pieces:

$$\lim_{x\to a}\bigl[3f(x)^2 - 2g(x) + 7\bigr] = 3L^2 - 2M + 7$$

without needing an epsilon-delta argument each time.

## Proof of the Sum Law (Epsilon-Delta)

> [!thm] Proof — Sum Law
> **Claim:** If $\lim_{x\to a} f(x) = L$ and $\lim_{x\to a} g(x) = M$, then $\lim_{x\to a}[f(x)+g(x)] = L+M$.
>
> **Proof.** Let $\epsilon > 0$ be given. We need $\delta > 0$ such that
> $$0 < |x-a| < \delta \implies |[f(x)+g(x)]-(L+M)| < \epsilon.$$
>
> Since $\lim_{x\to a} f(x) = L$, there exists $\delta_1 > 0$ such that
> $$0 < |x-a| < \delta_1 \implies |f(x)-L| < \frac{\epsilon}{2}.$$
>
> Since $\lim_{x\to a} g(x) = M$, there exists $\delta_2 > 0$ such that
> $$0 < |x-a| < \delta_2 \implies |g(x)-M| < \frac{\epsilon}{2}.$$
>
> Choose $\delta = \min(\delta_1, \delta_2)$. Then for $0 < |x-a| < \delta$:
> $$|[f(x)+g(x)]-(L+M)| = |[f(x)-L]+[g(x)-M]|$$
> $$\leq |f(x)-L| + |g(x)-M| < \frac{\epsilon}{2} + \frac{\epsilon}{2} = \epsilon. \quad\blacksquare$$

> [!tip] Triangle Inequality
> The key move is the **triangle inequality**: $|A+B| \leq |A|+|B|$. Splitting $\epsilon$ into $\epsilon/2 + \epsilon/2$ is a standard trick. This proof structure previews the epsilon-delta ideas of [[1.6 Calculating Limits|Section 1.7]].

## Worked Examples

> [!example] Example 1 — Applying multiple laws
> Evaluate $\lim_{x\to 2}(3x^2 - 4x + 5)$.
>
> $$\lim_{x\to 2}(3x^2 - 4x + 5) = 3\lim_{x\to 2}x^2 - 4\lim_{x\to 2}x + \lim_{x\to 2}5$$
>
> by the Sum/Difference and Constant Multiple Laws. Now by the Power Law and basic limits:
>
> $$= 3(2)^2 - 4(2) + 5 = 12 - 8 + 5 = 9.$$

> [!example] Example 2 — Quotient Law with verification
> Evaluate $\displaystyle\lim_{x\to 3}\frac{x^2+1}{x-1}$.
>
> First check: $\lim_{x\to 3}(x-1) = 2 \neq 0$, so the Quotient Law applies.
>
> $$\lim_{x\to 3}\frac{x^2+1}{x-1} = \frac{\lim_{x\to 3}(x^2+1)}{\lim_{x\to 3}(x-1)} = \frac{9+1}{3-1} = \frac{10}{2} = 5.$$

> [!example] Example 3 — Root Law
> Evaluate $\displaystyle\lim_{x\to 4}\sqrt{2x+1}$.
>
> $$\lim_{x\to 4}\sqrt{2x+1} = \sqrt{\lim_{x\to 4}(2x+1)} = \sqrt{2(4)+1} = \sqrt{9} = 3.$$
>
> The Root Law applies because $n=2$ (even) and $\lim_{x\to 4}(2x+1) = 9 > 0$.

> [!example] Example 4 — When the Quotient Law fails
> Consider $\displaystyle\lim_{x\to 1}\frac{x^2-1}{x-1}$.
>
> Here $\lim_{x\to 1}(x-1) = 0$, so the **Quotient Law does not apply**. The numerator also approaches $0$, giving the indeterminate form $\frac{0}{0}$. We must use algebraic techniques (factoring):
>
> $$\lim_{x\to 1}\frac{x^2-1}{x-1} = \lim_{x\to 1}\frac{(x-1)(x+1)}{x-1} = \lim_{x\to 1}(x+1) = 2.$$
>
> See [[1.6 Calculating Limits]] for more on handling $\frac{0}{0}$.

## See Also

- [[1.6 Calculating Limits]]
- [[Direct Substitution Property]]
- [[The Squeeze Theorem]]
