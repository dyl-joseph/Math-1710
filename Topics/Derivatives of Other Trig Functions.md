---
section: "2.4"
date_covered:
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, derivatives, trigonometry]
---

# Derivatives of Other Trig Functions

## Overview

Once we know $\frac{d}{dx}(\sin x) = \cos x$ and $\frac{d}{dx}(\cos x) = -\sin x$ (see [[Derivatives of Sine and Cosine]]), we derive the remaining four trig derivatives using the quotient rule. Each of the four — $\tan x$, $\cot x$, $\sec x$, $\csc x$ — is a ratio of sine and cosine.

---

## Proof: $\frac{d}{dx}(\tan x) = \sec^2 x$

> [!thm] Derivative of Tangent
> $$\frac{d}{dx}(\tan x) = \sec^2 x$$

**Proof.** Write $\tan x = \dfrac{\sin x}{\cos x}$ and apply the quotient rule:

$$\frac{d}{dx}(\tan x) = \frac{\cos x \cdot \cos x - \sin x \cdot (-\sin x)}{\cos^2 x}$$

$$= \frac{\cos^2 x + \sin^2 x}{\cos^2 x}$$

By the Pythagorean identity $\cos^2 x + \sin^2 x = 1$:

$$= \frac{1}{\cos^2 x} = \sec^2 x \qquad \blacksquare$$

---

## Proof: $\frac{d}{dx}(\sec x) = \sec x \tan x$

> [!thm] Derivative of Secant
> $$\frac{d}{dx}(\sec x) = \sec x \tan x$$

**Proof.** Write $\sec x = \dfrac{1}{\cos x}$ and apply the quotient rule:

$$\frac{d}{dx}(\sec x) = \frac{0 \cdot \cos x - 1 \cdot (-\sin x)}{\cos^2 x}$$

$$= \frac{\sin x}{\cos^2 x} = \frac{1}{\cos x} \cdot \frac{\sin x}{\cos x} = \sec x \tan x \qquad \blacksquare$$

---

## Proof: $\frac{d}{dx}(\cot x) = -\csc^2 x$

> [!thm] Derivative of Cotangent
> $$\frac{d}{dx}(\cot x) = -\csc^2 x$$

**Proof.** Write $\cot x = \dfrac{\cos x}{\sin x}$ and apply the quotient rule:

$$\frac{d}{dx}(\cot x) = \frac{(-\sin x) \cdot \sin x - \cos x \cdot \cos x}{\sin^2 x}$$

$$= \frac{-\sin^2 x - \cos^2 x}{\sin^2 x} = \frac{-(\sin^2 x + \cos^2 x)}{\sin^2 x}$$

$$= \frac{-1}{\sin^2 x} = -\csc^2 x \qquad \blacksquare$$

---

## Proof: $\frac{d}{dx}(\csc x) = -\csc x \cot x$

> [!thm] Derivative of Cosecant
> $$\frac{d}{dx}(\csc x) = -\csc x \cot x$$

**Proof.** Write $\csc x = \dfrac{1}{\sin x}$ and apply the quotient rule:

$$\frac{d}{dx}(\csc x) = \frac{0 \cdot \sin x - 1 \cdot \cos x}{\sin^2 x}$$

$$= \frac{-\cos x}{\sin^2 x} = -\frac{1}{\sin x} \cdot \frac{\cos x}{\sin x} = -\csc x \cot x \qquad \blacksquare$$

---

## Domain Restrictions

Each derivative is defined wherever the original function is defined:

| Function | Undefined at | Derivative undefined at |
|---|---|---|
| $\tan x$ | $x = \frac{\pi}{2} + n\pi$ | same |
| $\sec x$ | $x = \frac{\pi}{2} + n\pi$ | same |
| $\cot x$ | $x = n\pi$ | same |
| $\csc x$ | $x = n\pi$ | same |

where $n$ is any integer. At these points, the original function has vertical asymptotes, so the derivative does not exist.

---

## Relationship Between the Pairs

The six trig functions naturally group into three pairs, each pair linked by cofunctions:

| Pair | Derivatives | Pattern |
|---|---|---|
| $(\sin x, \cos x)$ | $\cos x$, $-\sin x$ | Cofunction gets negative |
| $(\tan x, \sec x)$ | $\sec^2 x$, $\sec x \tan x$ | Both involve $\sec$ |
| $(\cot x, \csc x)$ | $-\csc^2 x$, $-\csc x \cot x$ | Both involve $\csc$, both negative |

> [!tip] The co-function rule
> Compare $\tan$ and $\cot$: the derivative of $\cot x$ looks like the derivative of $\tan x$ but with "co-" versions and a negative sign. The same pattern relates $\sec$ and $\csc$. **Every "co-" derivative carries a negative sign.**

---

## Useful Trig Identities for Simplification

These come up frequently when working with trig derivatives:

| Identity | Formula |
|---|---|
| Pythagorean | $\sin^2 x + \cos^2 x = 1$ |
| Pythagorean (tan/sec) | $1 + \tan^2 x = \sec^2 x$ |
| Pythagorean (cot/csc) | $1 + \cot^2 x = \csc^2 x$ |
| Double angle (sin) | $\sin 2x = 2\sin x \cos x$ |
| Double angle (cos) | $\cos 2x = \cos^2 x - \sin^2 x$ |

---

## Examples

> [!example] Example 1 — Product rule with $\tan$ and $\sec$
> Differentiate $f(x) = x \tan x$.
>
> $$f'(x) = (1)(\tan x) + x(\sec^2 x) = \tan x + x\sec^2 x$$

> [!example] Example 2 — Quotient rule with $\csc$
> Differentiate $g(x) = \dfrac{\csc x}{x}$.
>
> $$g'(x) = \frac{(-\csc x \cot x)(x) - \csc x (1)}{x^2} = \frac{-x\csc x \cot x - \csc x}{x^2}$$
>
> Factor out $-\csc x$:
>
> $$= \frac{-\csc x(x\cot x + 1)}{x^2}$$

> [!example] Example 3 — Simplifying with identities
> Differentiate $h(x) = \sec^2 x - \tan^2 x$.
>
> Before differentiating, notice the Pythagorean identity: $\sec^2 x - \tan^2 x = 1$.
>
> So $h(x) = 1$, and $h'(x) = 0$.
>
> (You can verify by differentiating term by term — the terms cancel.)

---

## See Also

- [[Derivatives of Sine and Cosine]]
- [[2.4 Derivatives of Trigonometric Functions]]
- [[Power Rule]]
