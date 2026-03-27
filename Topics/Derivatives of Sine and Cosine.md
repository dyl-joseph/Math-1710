---
section: "2.4"
date_covered:
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, derivatives, trigonometry]
---

# Derivatives of Sine and Cosine

## Overview

The derivatives of $\sin x$ and $\cos x$ are the foundation for all trigonometric differentiation. Both proofs rely on the limit definition of the derivative and two key limits from [[1.6 Calculating Limits|Section 1.6]]:

$$\lim_{h \to 0} \frac{\sin h}{h} = 1 \qquad \lim_{h \to 0} \frac{\cos h - 1}{h} = 0$$

---

## Proof: $\frac{d}{dx}(\sin x) = \cos x$

> [!thm] Derivative of Sine
> $$\frac{d}{dx}(\sin x) = \cos x$$

**Proof.** Apply the limit definition of the derivative:

$$\frac{d}{dx}(\sin x) = \lim_{h \to 0} \frac{\sin(x+h) - \sin x}{h}$$

**Step 1 — Angle addition formula.** Expand $\sin(x+h)$:

$$\sin(x+h) = \sin x \cos h + \cos x \sin h$$

**Step 2 — Substitute and rearrange:**

$$= \lim_{h \to 0} \frac{\sin x \cos h + \cos x \sin h - \sin x}{h}$$

**Step 3 — Group terms:**

$$= \lim_{h \to 0} \frac{\sin x (\cos h - 1) + \cos x \sin h}{h}$$

**Step 4 — Split the fraction:**

$$= \lim_{h \to 0} \left[\sin x \cdot \frac{\cos h - 1}{h} + \cos x \cdot \frac{\sin h}{h}\right]$$

**Step 5 — Apply the two key limits:**

$$= \sin x \cdot 0 + \cos x \cdot 1 = \cos x$$

$$\boxed{\frac{d}{dx}(\sin x) = \cos x} \qquad \blacksquare$$

---

## Proof: $\frac{d}{dx}(\cos x) = -\sin x$

> [!thm] Derivative of Cosine
> $$\frac{d}{dx}(\cos x) = -\sin x$$

**Proof.** Apply the limit definition:

$$\frac{d}{dx}(\cos x) = \lim_{h \to 0} \frac{\cos(x+h) - \cos x}{h}$$

**Step 1 — Angle addition formula.** Expand $\cos(x+h)$:

$$\cos(x+h) = \cos x \cos h - \sin x \sin h$$

**Step 2 — Substitute and rearrange:**

$$= \lim_{h \to 0} \frac{\cos x \cos h - \sin x \sin h - \cos x}{h}$$

**Step 3 — Group terms:**

$$= \lim_{h \to 0} \frac{\cos x(\cos h - 1) - \sin x \sin h}{h}$$

**Step 4 — Split the fraction:**

$$= \lim_{h \to 0} \left[\cos x \cdot \frac{\cos h - 1}{h} - \sin x \cdot \frac{\sin h}{h}\right]$$

**Step 5 — Apply the two key limits:**

$$= \cos x \cdot 0 - \sin x \cdot 1 = -\sin x$$

$$\boxed{\frac{d}{dx}(\cos x) = -\sin x} \qquad \blacksquare$$

---

## Alternative: Deriving $\frac{d}{dx}(\cos x)$ from $\frac{d}{dx}(\sin x)$

Using the cofunction identity $\cos x = \sin\!\left(\frac{\pi}{2} - x\right)$ and a preview of the [[Power Rule|chain rule]]:

$$\frac{d}{dx}(\cos x) = \frac{d}{dx}\sin\!\left(\frac{\pi}{2} - x\right) = \cos\!\left(\frac{\pi}{2} - x\right) \cdot (-1) = -\sin x$$

This shortcut works once you know the chain rule (Section 2.5).

---

## Graphical Verification

Check that the slope of $\sin x$ matches $\cos x$ at key points:

| $x$ | $\sin x$ | Slope of $\sin x$ | $\cos x$ |
|---|---|---|---|
| $0$ | $0$ | $1$ (increasing steeply) | $1$ |
| $\pi/2$ | $1$ | $0$ (horizontal max) | $0$ |
| $\pi$ | $0$ | $-1$ (decreasing steeply) | $-1$ |
| $3\pi/2$ | $-1$ | $0$ (horizontal min) | $0$ |
| $2\pi$ | $0$ | $1$ (increasing steeply) | $1$ |

The slope of the sine curve at every point equals the value of the cosine curve — exactly as the derivative predicts.

---

## The Cyclic Pattern of Derivatives

Repeated differentiation of $\sin x$ and $\cos x$ produces a cycle of period 4:

$$\sin x \xrightarrow{\frac{d}{dx}} \cos x \xrightarrow{\frac{d}{dx}} -\sin x \xrightarrow{\frac{d}{dx}} -\cos x \xrightarrow{\frac{d}{dx}} \sin x$$

| $n$ | $\frac{d^n}{dx^n}(\sin x)$ | $\frac{d^n}{dx^n}(\cos x)$ |
|---|---|---|
| $0$ | $\sin x$ | $\cos x$ |
| $1$ | $\cos x$ | $-\sin x$ |
| $2$ | $-\sin x$ | $-\cos x$ |
| $3$ | $-\cos x$ | $\sin x$ |
| $4$ | $\sin x$ | $\cos x$ |

> [!tip] Finding the $n$th derivative
> To find $\frac{d^n}{dx^n}(\sin x)$, compute $n \mod 4$:
> - Remainder $0$: $\sin x$
> - Remainder $1$: $\cos x$
> - Remainder $2$: $-\sin x$
> - Remainder $3$: $-\cos x$
>
> The same idea works for $\cos x$ — just start the cycle at $\cos x$.

---

## Higher Derivative Examples

> [!example] Example 1 — High-order derivative
> Find $\frac{d^{99}}{dx^{99}}(\cos x)$.
>
> $99 \div 4 = 24$ remainder $3$. Starting from $\cos x$, three derivatives forward:
>
> $$\cos x \to -\sin x \to -\cos x \to \sin x$$
>
> $$\frac{d^{99}}{dx^{99}}(\cos x) = \sin x$$

> [!example] Example 2 — High-order derivative
> Find $\frac{d^{50}}{dx^{50}}(\sin x)$.
>
> $50 \div 4 = 12$ remainder $2$. Two derivatives forward from $\sin x$:
>
> $$\sin x \to \cos x \to -\sin x$$
>
> $$\frac{d^{50}}{dx^{50}}(\sin x) = -\sin x$$

---

## See Also

- [[2.4 Derivatives of Trigonometric Functions]]
- [[Derivatives of Other Trig Functions]]
- [[Power Rule]]
