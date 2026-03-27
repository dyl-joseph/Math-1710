---
section: "1.5"
date_covered:
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, limits]
---

# One-Sided Limits

## Definitions

Sometimes we only care about what $f(x)$ does as $x$ approaches $a$ from **one particular side**.

> [!def] Left-Hand Limit
> We write
> $$\lim_{x \to a^-} f(x) = L$$
> and say "the left-hand limit of $f(x)$ as $x$ approaches $a$ equals $L$" if we can make $f(x)$ arbitrarily close to $L$ by taking $x$ sufficiently close to $a$ **with $x < a$**.

> [!def] Right-Hand Limit
> We write
> $$\lim_{x \to a^+} f(x) = L$$
> and say "the right-hand limit of $f(x)$ as $x$ approaches $a$ equals $L$" if we can make $f(x)$ arbitrarily close to $L$ by taking $x$ sufficiently close to $a$ **with $x > a$**.

The notation $x \to a^-$ means "$x$ approaches $a$ from the left (from below)." The notation $x \to a^+$ means "$x$ approaches $a$ from the right (from above)."

## Relationship to the Two-Sided Limit

> [!thm] One-Sided Limits and the Two-Sided Limit
> $$\lim_{x \to a} f(x) = L \quad \text{if and only if} \quad \lim_{x \to a^-} f(x) = L \;\;\text{and}\;\; \lim_{x \to a^+} f(x) = L$$

In other words, the two-sided limit exists **precisely when** both one-sided limits exist **and are equal**. If the one-sided limits differ, the two-sided limit **does not exist**.

This theorem is extremely useful: to show a limit exists, verify both one-sided limits match. To show a limit does **not** exist, show the one-sided limits disagree.

## Worked Examples

### Example 1: Piecewise Linear Function

> [!example] Piecewise Function
> Let
> $$f(x) = \begin{cases} 2x + 1 & \text{if } x < 1 \\ x^2 + 2 & \text{if } x \geq 1 \end{cases}$$
>
> Find $\displaystyle\lim_{x \to 1^-} f(x)$, $\displaystyle\lim_{x \to 1^+} f(x)$, and $\displaystyle\lim_{x \to 1} f(x)$.
>
> **Solution.**
> - **Left-hand limit:** For $x < 1$, use $f(x) = 2x + 1$:
>   $$\lim_{x \to 1^-} f(x) = 2(1) + 1 = 3$$
> - **Right-hand limit:** For $x > 1$ (and $x \geq 1$), use $f(x) = x^2 + 2$:
>   $$\lim_{x \to 1^+} f(x) = 1^2 + 2 = 3$$
> - **Two-sided limit:** Both one-sided limits equal $3$, so:
>   $$\lim_{x \to 1} f(x) = 3$$
>
> Note: $f(1) = 1^2 + 2 = 3$ as well, so the function is actually **continuous** at $x = 1$.

### Example 2: Piecewise with a Jump

> [!example] Jump Discontinuity
> Let
> $$g(x) = \begin{cases} x + 3 & \text{if } x < 2 \\ 1 & \text{if } x = 2 \\ x^2 - 1 & \text{if } x > 2 \end{cases}$$
>
> Find $\displaystyle\lim_{x \to 2^-} g(x)$, $\displaystyle\lim_{x \to 2^+} g(x)$, and $\displaystyle\lim_{x \to 2} g(x)$.
>
> **Solution.**
> - **Left-hand limit:** For $x < 2$, use $g(x) = x + 3$:
>   $$\lim_{x \to 2^-} g(x) = 2 + 3 = 5$$
> - **Right-hand limit:** For $x > 2$, use $g(x) = x^2 - 1$:
>   $$\lim_{x \to 2^+} g(x) = 4 - 1 = 3$$
> - **Two-sided limit:** $5 \neq 3$, so $\lim_{x \to 2} g(x)$ **does not exist**.
>
> Also note $g(2) = 1$, which differs from **both** one-sided limits.

### Example 3: The Greatest Integer (Floor) Function

> [!example] Floor Function $\lfloor x \rfloor$
> The **greatest integer function** $\lfloor x \rfloor$ returns the largest integer less than or equal to $x$.
>
> Examples: $\lfloor 2.7 \rfloor = 2$, $\lfloor 3 \rfloor = 3$, $\lfloor -1.2 \rfloor = -2$.
>
> Evaluate $\displaystyle\lim_{x \to 3^-} \lfloor x \rfloor$ and $\displaystyle\lim_{x \to 3^+} \lfloor x \rfloor$.
>
> **Solution.**
> - **Left-hand limit:** For $x$ slightly less than $3$ (e.g., $2.9, 2.99, 2.999, \ldots$), we have $\lfloor x \rfloor = 2$. So:
>   $$\lim_{x \to 3^-} \lfloor x \rfloor = 2$$
> - **Right-hand limit:** For $x$ slightly greater than $3$ (e.g., $3.01, 3.001, \ldots$), we have $\lfloor x \rfloor = 3$. So:
>   $$\lim_{x \to 3^+} \lfloor x \rfloor = 3$$
> - Since $2 \neq 3$, $\lim_{x \to 3} \lfloor x \rfloor$ **does not exist**.
>
> This pattern holds at **every integer**: the floor function has a jump discontinuity at each integer $n$, with left-hand limit $n - 1$ and right-hand limit $n$.

### Example 4: Absolute Value Piecewise

> [!example] $f(x) = \dfrac{|x|}{x}$
> Evaluate $\displaystyle\lim_{x \to 0^-} \frac{|x|}{x}$ and $\displaystyle\lim_{x \to 0^+} \frac{|x|}{x}$.
>
> **Solution.** Rewrite using the piecewise definition of $|x|$:
> $$\frac{|x|}{x} = \begin{cases} \dfrac{-x}{x} = -1 & \text{if } x < 0 \\[6pt] \dfrac{x}{x} = 1 & \text{if } x > 0 \end{cases}$$
>
> - $\displaystyle\lim_{x \to 0^-} \frac{|x|}{x} = -1$
> - $\displaystyle\lim_{x \to 0^+} \frac{|x|}{x} = 1$
> - Since $-1 \neq 1$, $\displaystyle\lim_{x \to 0} \frac{|x|}{x}$ **does not exist**.

## Tips for Evaluating One-Sided Limits

> [!tip] Strategy
> 1. **Identify which formula applies.** For piecewise functions, use the piece valid on the side you're approaching from.
> 2. **Plug in the approaching value** into that formula (direct substitution into the relevant piece).
> 3. **Compare left and right** to determine if the two-sided limit exists.
> 4. **Watch for absolute values** — rewrite $|x - a|$ piecewise and then take one-sided limits.
> 5. **At endpoints of a domain**, only one one-sided limit is relevant (e.g., $\lim_{x \to 0^+} \sqrt{x} = 0$).

## See Also

- [[1.5 Introduction to Limits]]
- [[Intuitive Idea of a Limit]]
- [[Infinite Limits and Vertical Asymptotes]]
