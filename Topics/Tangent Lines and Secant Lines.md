---
section: "2.1"
date_covered:
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, derivatives]
---

# Tangent Lines and Secant Lines

The tangent line problem — finding the line that just touches a curve at a single point — is one of the two foundational problems of calculus (the other being the area problem). Solving it requires limits, and the answer turns out to be the **derivative**.

---

## Secant Lines

> [!def] Secant Line
> A **secant line** to a curve $y = f(x)$ is a line that passes through two distinct points on the curve:
> $$(a,\, f(a)) \quad\text{and}\quad (b,\, f(b)).$$
> Its slope is
> $$m_{\text{sec}} = \frac{f(b) - f(a)}{b - a}.$$

This ratio $\dfrac{\Delta y}{\Delta x}$ is also called a **difference quotient**. Writing $b = a + h$, the slope becomes

$$m_{\text{sec}} = \frac{f(a+h) - f(a)}{h}, \qquad h \neq 0.$$

---

## From Secant to Tangent

Imagine sliding the second point along the curve toward the first. As $b \to a$ (or equivalently $h \to 0$), the secant line rotates and approaches a limiting position — the **tangent line**.

> [!def] Tangent Line
> The **tangent line** to the curve $y = f(x)$ at the point $(a, f(a))$ is the line through $(a, f(a))$ with slope
> $$m = \lim_{x \to a} \frac{f(x) - f(a)}{x - a} = \lim_{h \to 0} \frac{f(a+h) - f(a)}{h}$$
> provided this limit exists.

The tangent line is the best linear approximation to the curve near $x = a$. It touches the curve at $(a, f(a))$ and has the same "direction" as the curve at that point.

> [!tip] Two Equivalent Forms
> **$x$-form:** Let the moving point be $(x, f(x))$ and take $x \to a$.
> $$m = \lim_{x \to a} \frac{f(x) - f(a)}{x - a}$$
> **$h$-form:** Let $h = x - a$ so that $x = a + h$ and $h \to 0$.
> $$m = \lim_{h \to 0} \frac{f(a+h) - f(a)}{h}$$
> Both give the same result. Choose whichever makes the algebra simpler.

---

## Equation of the Tangent Line

Once you know the slope $m$ and the point $(a, f(a))$, use **point-slope form**:

$$y - f(a) = m(x - a)$$

---

## Normal Lines

> [!def] Normal Line
> The **normal line** to a curve at a point is the line **perpendicular** to the tangent line at that point. If the tangent has slope $m \neq 0$, the normal has slope
> $$m_{\perp} = -\frac{1}{m}.$$

If the tangent is horizontal ($m = 0$), the normal is vertical: $x = a$. If the tangent is vertical, the normal is horizontal.

---

## Worked Examples

> [!example] Example 1 — Tangent to a Parabola
> Find the equation of the tangent line to $f(x) = x^2$ at the point $(1, 1)$.
>
> **Slope (h-form):**
> $$m = \lim_{h \to 0} \frac{(1+h)^2 - 1}{h} = \lim_{h \to 0} \frac{1 + 2h + h^2 - 1}{h} = \lim_{h \to 0} \frac{2h + h^2}{h}$$
> $$= \lim_{h \to 0} (2 + h) = 2$$
>
> **Tangent line:** $y - 1 = 2(x - 1)$, so $y = 2x - 1$.

> [!example] Example 2 — Tangent and Normal to $f(x) = \dfrac{1}{x}$
> Find the tangent and normal lines at $(2, \tfrac{1}{2})$.
>
> **Slope (x-form):**
> $$m = \lim_{x \to 2} \frac{\frac{1}{x} - \frac{1}{2}}{x - 2} = \lim_{x \to 2} \frac{\frac{2 - x}{2x}}{x - 2} = \lim_{x \to 2} \frac{-(x-2)}{2x(x-2)} = \lim_{x \to 2} \frac{-1}{2x} = -\frac{1}{4}$$
>
> **Tangent:** $y - \tfrac{1}{2} = -\tfrac{1}{4}(x - 2)$, i.e. $y = -\tfrac{1}{4}x + 1$.
>
> **Normal:** slope $= -\dfrac{1}{-1/4} = 4$, so $y - \tfrac{1}{2} = 4(x - 2)$, i.e. $y = 4x - \tfrac{15}{2}$.

> [!example] Example 3 — Tangent to $f(x) = \sqrt{x+1}$ at $x = 3$
> **Point:** $(3, 2)$.
>
> **Slope (h-form):**
> $$m = \lim_{h \to 0} \frac{\sqrt{4+h} - 2}{h}$$
> Rationalize the numerator:
> $$= \lim_{h \to 0} \frac{(4+h) - 4}{h(\sqrt{4+h}+2)} = \lim_{h \to 0} \frac{1}{\sqrt{4+h}+2} = \frac{1}{4}$$
>
> **Tangent:** $y - 2 = \tfrac{1}{4}(x - 3)$, i.e. $y = \tfrac{1}{4}x + \tfrac{5}{4}$.

---

## Tips and Common Mistakes

> [!tip] Algebra Strategies
> - For square-root functions, **rationalize the numerator** by multiplying by the conjugate.
> - For rational functions, **combine fractions** in the numerator before cancelling $h$ (or $x - a$).
> - Always **cancel the factor that makes the denominator zero** before substituting. If you can't cancel it, re-check your algebra.

---

## See Also

- [[2.1 Derivatives and Rates of Change]]
- [[Average vs Instantaneous Rate of Change]]
