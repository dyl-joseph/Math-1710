---
section: "1.8"
date_covered:
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, continuity]
---

# Types of Discontinuity

A function $f$ is **discontinuous** at $x = a$ when at least one of the three continuity conditions fails:

1. $f(a)$ is defined
2. $\lim_{x\to a} f(x)$ exists
3. $\lim_{x\to a} f(x) = f(a)$

The *way* the condition fails determines the type of discontinuity.

---

## Removable Discontinuity

> [!def] Removable Discontinuity
> A function $f$ has a **removable discontinuity** at $x = a$ if $\lim_{x\to a} f(x)$ exists but either:
> - $f(a)$ is not defined, or
> - $f(a) \neq \lim_{x\to a} f(x)$.

**Visual picture:** There is a "hole" in the graph at the point $(a, L)$ where $L = \lim_{x\to a} f(x)$. The curve approaches $L$ from both sides, but the function value is either missing or placed somewhere else.

**How to "remove" the discontinuity:** Redefine $f(a) = \lim_{x\to a} f(x)$. This fills the hole and makes $f$ continuous at $a$.

> [!example] Example 1
> $$f(x) = \frac{x^2 - 4}{x - 2}$$
>
> At $x = 2$: the function is undefined (division by zero). But:
> $$\lim_{x\to 2}\frac{x^2-4}{x-2} = \lim_{x\to 2}\frac{(x-2)(x+2)}{x-2} = \lim_{x\to 2}(x+2) = 4$$
>
> The limit exists, so this is a **removable discontinuity**. Redefine $f(2) = 4$ to make $f$ continuous.

> [!example] Example 2
> $$g(x) = \begin{cases} x^2 & x \neq 1 \\ 5 & x = 1 \end{cases}$$
>
> Here $\lim_{x\to 1} g(x) = 1$ but $g(1) = 5 \neq 1$. The limit exists but does not equal the function value — **removable discontinuity** at $x = 1$.

---

## Jump Discontinuity

> [!def] Jump Discontinuity
> A function $f$ has a **jump discontinuity** at $x = a$ if both one-sided limits exist but are not equal:
> $$\lim_{x\to a^-} f(x) \neq \lim_{x\to a^+} f(x)$$

**Visual picture:** The graph "jumps" from one value to another at $x = a$. There is a break where the left-hand piece ends at one height and the right-hand piece starts at a different height.

Jump discontinuities are **not removable** — no single value of $f(a)$ can bridge the gap between two different one-sided limits.

> [!example] Example 3
> The greatest integer function (floor function):
> $$f(x) = \lfloor x \rfloor$$
>
> At every integer $n$:
> $$\lim_{x\to n^-} \lfloor x \rfloor = n-1, \qquad \lim_{x\to n^+} \lfloor x \rfloor = n$$
>
> The one-sided limits differ, so there is a **jump discontinuity** at every integer.

> [!example] Example 4
> $$h(x) = \begin{cases} x + 1 & x < 3 \\ x^2 - 5 & x \geq 3 \end{cases}$$
>
> $$\lim_{x\to 3^-} h(x) = 3 + 1 = 4, \qquad \lim_{x\to 3^+} h(x) = 9 - 5 = 4$$
>
> The one-sided limits are equal, so this is actually **continuous** at $x = 3$ (not a jump). Always compute before classifying!

---

## Infinite Discontinuity

> [!def] Infinite Discontinuity
> A function $f$ has an **infinite discontinuity** at $x = a$ if at least one of the one-sided limits is $+\infty$ or $-\infty$.

**Visual picture:** There is a vertical asymptote at $x = a$. The graph shoots off to infinity (up or down) on at least one side.

> [!example] Example 5
> $$f(x) = \frac{1}{x-3}$$
>
> At $x = 3$:
> $$\lim_{x\to 3^-}\frac{1}{x-3} = -\infty, \qquad \lim_{x\to 3^+}\frac{1}{x-3} = +\infty$$
>
> At least one one-sided limit is infinite — **infinite discontinuity** at $x = 3$.

> [!example] Example 6
> $$f(x) = \frac{1}{(x+1)^2}$$
>
> At $x = -1$:
> $$\lim_{x\to -1^-}\frac{1}{(x+1)^2} = +\infty, \qquad \lim_{x\to -1^+}\frac{1}{(x+1)^2} = +\infty$$
>
> Both sides blow up to $+\infty$ — **infinite discontinuity** at $x = -1$.

---

## Oscillating Discontinuity (Brief Mention)

> [!def] Oscillating Discontinuity
> A function has an **oscillating discontinuity** at $x = a$ if it oscillates too wildly for any limit (even one-sided) to exist, and the behavior is not infinite.

The classic example is $f(x) = \sin\!\left(\frac{1}{x}\right)$ near $x = 0$. As $x \to 0$, the function oscillates between $-1$ and $1$ infinitely often, so $\lim_{x\to 0}\sin(1/x)$ does not exist. This type rarely appears in Calc I exams but is worth knowing.

---

## How to Classify Discontinuities — Systematic Approach

Given $f(x)$ and a point $x = a$:

1. **Check if $f(a)$ is defined.** If not, there is a discontinuity — continue to classify.
2. **Compute $\lim_{x\to a^-} f(x)$ and $\lim_{x\to a^+} f(x)$.**
3. **If either one-sided limit is $\pm\infty$:** infinite discontinuity.
4. **If both one-sided limits are finite but unequal:** jump discontinuity.
5. **If both one-sided limits are finite and equal** (so $\lim_{x\to a} f(x) = L$ exists):
   - If $f(a)$ is undefined or $f(a) \neq L$: removable discontinuity.
   - If $f(a) = L$: the function is actually continuous at $a$ — no discontinuity.

> [!tip] Quick Identification from a Formula
> - Rational functions: factor and cancel. If a factor cancels completely, the discontinuity is **removable**. If a factor remains in the denominator, it is **infinite**.
> - Piecewise functions: compute both one-sided limits at the boundary. Different values means **jump**; same value means check $f(a)$ for removable or continuous.

---

## See Also

- [[1.8 Continuity]]
- [[Intermediate Value Theorem]]
- [[Limit Laws]]
