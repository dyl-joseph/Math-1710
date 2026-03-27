---
section: "2.5"
date_covered: "2026-02-02"
textbook: "Stewart Calculus 9e"
tags: [calculus, derivatives, chain-rule]
---

# Chain Rule

> [!info] Deep Dive — The Chain Rule
> Supporting topic for [[2.5 The Chain Rule]].

## Formal Statement

> [!thm] The Chain Rule
> If $g$ is differentiable at $x$ and $f$ is differentiable at $g(x)$, then the composite function $F = f \circ g$ defined by $F(x) = f(g(x))$ is differentiable at $x$, and
> $$F'(x) = f'(g(x)) \cdot g'(x)$$
> In Leibniz notation, if $y = f(u)$ and $u = g(x)$ are both differentiable, then
> $$\frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dx}$$

## Proof

The naive approach — writing $\frac{\Delta y}{\Delta x} = \frac{\Delta y}{\Delta u} \cdot \frac{\Delta u}{\Delta x}$ and taking limits — fails because $\Delta u$ could be zero. The rigorous proof uses an error-term reformulation.

**Setup.** If $f$ is differentiable at $u = g(a)$, define the error function:

$$\varepsilon(\Delta u) = \begin{cases} \frac{f(u + \Delta u) - f(u)}{\Delta u} - f'(u) & \text{if } \Delta u \neq 0 \\ 0 & \text{if } \Delta u = 0 \end{cases}$$

Then $\varepsilon(\Delta u) \to 0$ as $\Delta u \to 0$ (this is just differentiability of $f$), and we can write:

$$f(u + \Delta u) - f(u) = [f'(u) + \varepsilon(\Delta u)] \cdot \Delta u$$

**Proof.** Let $\Delta u = g(x + h) - g(x)$. Then:

$$\frac{F(x+h) - F(x)}{h} = \frac{f(g(x+h)) - f(g(x))}{h} = [f'(g(x)) + \varepsilon(\Delta u)] \cdot \frac{g(x+h) - g(x)}{h}$$

As $h \to 0$: since $g$ is continuous (differentiable $\Rightarrow$ continuous), $\Delta u \to 0$, so $\varepsilon(\Delta u) \to 0$. Also $\frac{g(x+h)-g(x)}{h} \to g'(x)$. Therefore:

$$F'(x) = [f'(g(x)) + 0] \cdot g'(x) = f'(g(x)) \cdot g'(x) \quad \blacksquare$$

## Leibniz Notation Intuition

The Leibniz form $\frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dx}$ looks like "the $du$'s cancel." This is a useful mnemonic but **not** a valid proof — $\frac{dy}{dx}$ is not literally a fraction. The proof above is what makes it rigorous.

## Identifying Inner and Outer Functions

| Composite $F(x)$ | Outer $f(u)$ | Inner $u = g(x)$ |
|---|---|---|
| $(3x+1)^7$ | $u^7$ | $3x+1$ |
| $\sin(x^2)$ | $\sin u$ | $x^2$ |
| $e^{\cos x}$ | $e^u$ | $\cos x$ |
| $\sqrt{\tan x}$ | $\sqrt{u}$ | $\tan x$ |
| $\cos^4(x)$ | $u^4$ | $\cos x$ |

> [!tip] How to Identify
> Ask: "What is the **last** operation I would perform if I were evaluating this?" That is the outer function. Everything inside it is the inner function.

## The General Power Rule

A direct consequence of the chain rule with $f(u) = u^n$:

> [!thm] General Power Rule
> If $g$ is differentiable and $n$ is any real number, then
> $$\frac{d}{dx}[g(x)]^n = n[g(x)]^{n-1} \cdot g'(x)$$

## Repeated Application

For triple (or deeper) compositions like $f(g(h(x)))$, apply chain rule from the outside in:

$$\frac{d}{dx} f(g(h(x))) = f'(g(h(x))) \cdot g'(h(x)) \cdot h'(x)$$

In Leibniz notation with $y = f(u)$, $u = g(v)$, $v = h(x)$:

$$\frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dv} \cdot \frac{dv}{dx}$$

## Common Mistakes

| Mistake | Correction |
|---|---|
| $\frac{d}{dx}\sin(x^2) = \cos(x^2)$ | Missing inner derivative: $\cos(x^2) \cdot 2x$ |
| $\frac{d}{dx}(3x+1)^5 = 5(3x+1)^4$ | Missing $\cdot 3$: answer is $15(3x+1)^4$ |
| Applying chain rule to $x^5$ | Not a composition — just use power rule |
| $\frac{d}{dx}e^{x^2} = e^{x^2}$ | Missing inner: $e^{x^2} \cdot 2x$ |

## Practice Problems

> [!example] Practice 1
> Find $\frac{d}{dx}(4x^2 - 3x + 1)^{10}$.
>
> **Solution.** General power rule with $g(x) = 4x^2 - 3x + 1$, $n = 10$:
> $$10(4x^2 - 3x + 1)^9 \cdot (8x - 3)$$

> [!example] Practice 2
> Find $\frac{d}{dx}\cos(\ln x)$. *(Assumes knowledge of $\frac{d}{dx}\ln x = \frac{1}{x}$.)*
>
> **Solution.** Outer: $\cos u$, inner: $u = \ln x$.
> $$-\sin(\ln x) \cdot \frac{1}{x} = -\frac{\sin(\ln x)}{x}$$

> [!example] Practice 3
> Find $\frac{d}{dx}\sqrt{1 + e^{2x}}$.
>
> **Solution.** Rewrite as $(1 + e^{2x})^{1/2}$. Two layers of chain rule:
> $$\frac{1}{2}(1 + e^{2x})^{-1/2} \cdot e^{2x} \cdot 2 = \frac{e^{2x}}{\sqrt{1 + e^{2x}}}$$

> [!example] Practice 4
> Find $\frac{d}{dx}\tan^3(2x)$.
>
> **Solution.** Three layers: power, tan, and $2x$.
> $$3\tan^2(2x) \cdot \sec^2(2x) \cdot 2 = 6\tan^2(2x)\sec^2(2x)$$

## See Also
- [[2.5 The Chain Rule]]
- [[Product and Quotient Rules]]
- [[Power Rule]]
