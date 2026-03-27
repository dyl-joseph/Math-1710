---
section: "2.2"
date_covered:
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, derivatives]
---

# Differentiability

A function is **differentiable** at a point when its derivative exists there — that is, when the limit defining $f'(a)$ converges to a finite number. Differentiability is a stronger condition than continuity: every differentiable function is continuous, but not every continuous function is differentiable.

---

## Definition

> [!def] Differentiable at a Point
> A function $f$ is **differentiable at** $a$ if
> $$f'(a) = \lim_{h\to 0}\frac{f(a+h)-f(a)}{h}$$
> exists (as a finite number).

> [!def] Differentiable on an Interval
> - $f$ is **differentiable on an open interval** $(a,b)$ if it is differentiable at every point in $(a,b)$.
> - $f$ is **differentiable on a closed interval** $[a,b]$ if it is differentiable on $(a,b)$ and the appropriate one-sided derivatives exist at the endpoints:
>   $$f'(a^+) = \lim_{h\to 0^+}\frac{f(a+h)-f(a)}{h}, \qquad f'(b^-) = \lim_{h\to 0^-}\frac{f(b+h)-f(b)}{h}.$$

---

## Three Ways Differentiability Fails

If $f$ is continuous at $a$ but $f'(a)$ does not exist, one of the following is occurring.

### 1. Corner or Cusp

The graph has a sharp change in direction. The left-hand and right-hand derivatives exist but are not equal.

> [!example] Corner — $f(x)=|x|$ at $x=0$
> Left-hand derivative:
> $$\lim_{h\to 0^-}\frac{|0+h|-|0|}{h}=\lim_{h\to 0^-}\frac{-h}{h}=-1$$
> Right-hand derivative:
> $$\lim_{h\to 0^+}\frac{|0+h|-|0|}{h}=\lim_{h\to 0^+}\frac{h}{h}=1$$
> Since $-1\neq 1$, the derivative does not exist at $0$. The graph has a **corner** there.

### 2. Vertical Tangent

The tangent line becomes vertical — the derivative tends to $\pm\infty$.

> [!example] Vertical Tangent — $f(x)=\sqrt[3]{x}$ at $x=0$
> $$f'(0)=\lim_{h\to 0}\frac{h^{1/3}}{h}=\lim_{h\to 0}\frac{1}{h^{2/3}}=\infty$$
> The limit is infinite, so $f'(0)$ does not exist. The graph has a **vertical tangent** at the origin.

### 3. Discontinuity

If $f$ is not continuous at $a$, then $f$ cannot be differentiable at $a$ (this follows from the theorem below). Any jump, removable, or infinite discontinuity automatically prevents differentiability.

---

## Differentiable Implies Continuous

> [!thm] Differentiable ⟹ Continuous
> If $f$ is differentiable at $a$, then $f$ is continuous at $a$.

**Proof.** We need to show $\lim_{x\to a}f(x)=f(a)$, i.e., $\lim_{x\to a}[f(x)-f(a)]=0$.

Write:
$$f(x)-f(a)=\frac{f(x)-f(a)}{x-a}\cdot(x-a)$$

Taking the limit as $x\to a$:
$$\lim_{x\to a}[f(x)-f(a)]=\lim_{x\to a}\frac{f(x)-f(a)}{x-a}\cdot\lim_{x\to a}(x-a)=f'(a)\cdot 0=0$$

The product-law step is valid because both limits exist ($f'(a)$ exists by hypothesis). Therefore $\lim_{x\to a}f(x)=f(a)$, so $f$ is continuous at $a$. $\blacksquare$

---

## The Converse Is False

> [!tip] Continuous Does NOT Imply Differentiable
> $f(x)=|x|$ is continuous everywhere (including $x=0$) but is **not** differentiable at $x=0$ — there is a corner. So continuity alone is not enough.

---

## Examples of Checking Differentiability

> [!example] Example 1 — Piecewise Function
> $$f(x)=\begin{cases} x^2 & x\le 1 \\ 2x-1 & x>1 \end{cases}$$
>
> **Continuity at $x=1$:** $\lim_{x\to 1^-}x^2=1$ and $\lim_{x\to 1^+}(2x-1)=1$, and $f(1)=1$. Continuous. ✓
>
> **Left-hand derivative:** $\lim_{h\to 0^-}\frac{(1+h)^2-1}{h}=\lim_{h\to 0^-}(2+h)=2$
>
> **Right-hand derivative:** $\lim_{h\to 0^+}\frac{[2(1+h)-1]-1}{h}=\lim_{h\to 0^+}\frac{2h}{h}=2$
>
> Both one-sided derivatives equal $2$, so $f'(1)=2$. The function **is differentiable** at $x=1$.

> [!example] Example 2 — Piecewise Function with a Corner
> $$g(x)=\begin{cases} x^2 & x\le 1 \\ 3x-2 & x>1 \end{cases}$$
>
> **Continuity at $x=1$:** $\lim_{x\to 1^-}x^2=1$ and $\lim_{x\to 1^+}(3x-2)=1$, and $g(1)=1$. Continuous. ✓
>
> **Left-hand derivative:** $\lim_{h\to 0^-}\frac{(1+h)^2-1}{h}=2$
>
> **Right-hand derivative:** $\lim_{h\to 0^+}\frac{[3(1+h)-2]-1}{h}=\lim_{h\to 0^+}\frac{3h}{h}=3$
>
> Since $2\neq 3$, $g'(1)$ **does not exist** — there is a corner at $x=1$.

> [!example] Example 3 — Checking $f(x)=x^{1/3}$ at $x=0$
> $$f'(0)=\lim_{h\to 0}\frac{h^{1/3}-0}{h}=\lim_{h\to 0}\frac{1}{h^{2/3}}=\infty$$
> The limit is infinite, so $f$ is **not differentiable** at $0$ (vertical tangent).

---

## See Also

- [[2.2 The Derivative as a Function]] — the derivative as a function, notation, and examples
- [[Higher-Order Derivatives]] — second and higher-order derivatives
- [[1.8 Continuity]] — the continuity condition that differentiability implies
