---
section: "2.3"
date_covered: [2026-01-27, 2026-01-29]
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, derivatives, differentiation-rules]
---

# Product and Quotient Rules

When a function is a product or quotient of two pieces, you cannot just differentiate each piece separately. These rules tell you how to handle that correctly.

---

## The Product Rule

> [!thm] Product Rule
> If $f$ and $g$ are both differentiable, then
> $$\frac{d}{dx}[f(x)\,g(x)] = f'(x)\,g(x) + f(x)\,g'(x)$$
> In compact notation: $(fg)' = f'g + fg'$.

In words: *the derivative of a product is the derivative of the first times the second, plus the first times the derivative of the second.*

### Proof from the Limit Definition

$$\frac{d}{dx}[f(x)g(x)] = \lim_{h\to 0}\frac{f(x+h)g(x+h) - f(x)g(x)}{h}$$

The key trick is to **add and subtract** $f(x+h)g(x)$ in the numerator:

$$= \lim_{h\to 0}\frac{f(x+h)g(x+h) - f(x+h)g(x) + f(x+h)g(x) - f(x)g(x)}{h}$$

$$= \lim_{h\to 0}\left[f(x+h)\cdot\frac{g(x+h)-g(x)}{h} + g(x)\cdot\frac{f(x+h)-f(x)}{h}\right]$$

Now take limits. Since $f$ is differentiable it is continuous, so $\lim_{h\to 0}f(x+h) = f(x)$:

$$= f(x)\,g'(x) + g(x)\,f'(x) = f'(x)\,g(x) + f(x)\,g'(x) \quad\blacksquare$$

---

### Why $(fg)' \neq f'g'$

> [!tip] The derivative of a product is NOT the product of the derivatives
> This is one of the most common calculus errors. A quick counterexample kills it:
>
> Let $f(x) = x$ and $g(x) = x$. Then $f(x)g(x) = x^2$.
> - Correct (product rule): $(x^2)' = 2x$
> - Wrong ($f'g'$): $f'(x)\cdot g'(x) = 1\cdot 1 = 1$
>
> $2x \neq 1$, so the "naive" rule fails.

---

### Extended Product Rule (Three Factors)

> [!thm] Product Rule for Three Functions
> If $f$, $g$, and $h$ are all differentiable, then
> $$(fgh)' = f'gh + fg'h + fgh'$$

**Derivation:** Group as $f\cdot(gh)$ and apply the product rule twice:

$$(f\cdot gh)' = f'\cdot(gh) + f\cdot(gh)' = f'gh + f(g'h + gh') = f'gh + fg'h + fgh'$$

The pattern generalizes: differentiate one factor at a time, leave the others alone, and add up all the terms.

---

## The Quotient Rule

> [!thm] Quotient Rule
> If $f$ and $g$ are differentiable and $g(x)\neq 0$, then
> $$\frac{d}{dx}\left[\frac{f(x)}{g(x)}\right] = \frac{f'(x)\,g(x) - f(x)\,g'(x)}{[g(x)]^2}$$
> In compact notation: $\left(\dfrac{f}{g}\right)' = \dfrac{f'g - fg'}{g^2}$.

### The Mnemonic

> [!tip] "Lo d-Hi minus Hi d-Lo over Lo-Lo"
> Let **Hi** $= f(x)$ (numerator) and **Lo** $= g(x)$ (denominator):
> $$\frac{d}{dx}\left(\frac{\text{Hi}}{\text{Lo}}\right) = \frac{\text{Lo}\cdot d(\text{Hi}) - \text{Hi}\cdot d(\text{Lo})}{\text{Lo}\cdot\text{Lo}}$$
> The minus sign is critical — the quotient rule is **not** symmetric. The numerator's derivative comes first when multiplied by the denominator.

### Proof from the Limit Definition

$$\frac{d}{dx}\left[\frac{f(x)}{g(x)}\right] = \lim_{h\to 0}\frac{\dfrac{f(x+h)}{g(x+h)} - \dfrac{f(x)}{g(x)}}{h}$$

Combine the fractions in the numerator:

$$= \lim_{h\to 0}\frac{f(x+h)g(x) - f(x)g(x+h)}{h\,g(x+h)\,g(x)}$$

Add and subtract $f(x)g(x)$ in the numerator:

$$= \lim_{h\to 0}\frac{[f(x+h)g(x) - f(x)g(x)] - [f(x)g(x+h) - f(x)g(x)]}{h\,g(x+h)\,g(x)}$$

$$= \lim_{h\to 0}\frac{g(x)\cdot\dfrac{f(x+h)-f(x)}{h} - f(x)\cdot\dfrac{g(x+h)-g(x)}{h}}{g(x+h)\,g(x)}$$

Taking limits (using continuity of $g$: $\lim_{h\to 0}g(x+h)=g(x)$):

$$= \frac{g(x)\,f'(x) - f(x)\,g'(x)}{[g(x)]^2} = \frac{f'(x)\,g(x) - f(x)\,g'(x)}{[g(x)]^2} \quad\blacksquare$$

---

## When NOT to Use These Rules

> [!tip] Simplify first when possible
> If you can rewrite a quotient as a sum of power functions, do it — the algebra is easier and less error-prone.
>
> **Example:** To differentiate $\dfrac{x^3 + 2x}{x}$, do NOT use the quotient rule. Just simplify:
> $$\frac{x^3 + 2x}{x} = x^2 + 2 \implies \frac{d}{dx}(x^2 + 2) = 2x$$
>
> Similarly, $\dfrac{3x^5 - x^2}{x^2} = 3x^3 - 1$ is much easier to differentiate directly.

---

## Worked Examples

> [!example] Example 1: Product Rule
> Find $\frac{d}{dx}\left[(x^2 + 1)(x^3 - 4x)\right]$.
>
> Let $f(x) = x^2 + 1$ and $g(x) = x^3 - 4x$.
>
> $$f'(x) = 2x, \qquad g'(x) = 3x^2 - 4$$
>
> $$(fg)' = f'g + fg' = 2x(x^3 - 4x) + (x^2+1)(3x^2-4)$$
>
> $$= 2x^4 - 8x^2 + 3x^4 - 4x^2 + 3x^2 - 4 = 5x^4 - 9x^2 - 4$$
>
> *Check:* Expanding first gives $(x^2+1)(x^3-4x) = x^5 - 3x^3 - 4x$, whose derivative is $5x^4 - 9x^2 - 4$. $\checkmark$

> [!example] Example 2: Quotient Rule
> Find $\frac{d}{dx}\left(\dfrac{x^2 + x - 2}{x^3 + 6}\right)$.
>
> Let $f = x^2 + x - 2$ and $g = x^3 + 6$.
>
> $$f' = 2x + 1, \qquad g' = 3x^2$$
>
> $$\frac{d}{dx}\left(\frac{f}{g}\right) = \frac{(2x+1)(x^3+6) - (x^2+x-2)(3x^2)}{(x^3+6)^2}$$
>
> Expand the numerator:
>
> $$(2x+1)(x^3+6) = 2x^4 + x^3 + 12x + 6$$
>
> $$(x^2+x-2)(3x^2) = 3x^4 + 3x^3 - 6x^2$$
>
> Numerator: $2x^4 + x^3 + 12x + 6 - 3x^4 - 3x^3 + 6x^2 = -x^4 - 2x^3 + 6x^2 + 12x + 6$
>
> $$\frac{d}{dx}\left(\frac{x^2+x-2}{x^3+6}\right) = \frac{-x^4-2x^3+6x^2+12x+6}{(x^3+6)^2}$$

> [!example] Example 3: Product Rule with Radicals
> Find $\frac{d}{dx}\left(\sqrt{x}\,(x^2 - 1)\right)$.
>
> Let $f(x) = x^{1/2}$ and $g(x) = x^2 - 1$.
>
> $$f'(x) = \tfrac{1}{2}x^{-1/2}, \qquad g'(x) = 2x$$
>
> $$(fg)' = \tfrac{1}{2}x^{-1/2}(x^2-1) + x^{1/2}(2x)$$
>
> $$= \frac{x^2-1}{2\sqrt{x}} + 2x\sqrt{x} = \frac{x^2-1}{2\sqrt{x}} + \frac{4x^2}{2\sqrt{x}} = \frac{5x^2 - 1}{2\sqrt{x}}$$

> [!example] Example 4: Simplify Instead of Quotient Rule
> Find $\frac{d}{dx}\left(\dfrac{t^2 - 3\sqrt{t}}{t}\right)$.
>
> Simplify first:
> $$\frac{t^2 - 3\sqrt{t}}{t} = t - 3t^{-1/2}$$
>
> Now differentiate term by term:
> $$\frac{d}{dt}\left(t - 3t^{-1/2}\right) = 1 - 3\left(-\tfrac{1}{2}\right)t^{-3/2} = 1 + \frac{3}{2t^{3/2}}$$

---

## See Also

- [[2.3 Differentiation Rules]]
- [[Power Rule]]
