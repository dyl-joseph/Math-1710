---
section: "2.6"
date_covered: "2026-02-03"
textbook: "Stewart Calculus 9e"
tags: [calculus, derivatives, implicit-differentiation]
---

# Implicit Differentiation

> [!info] Deep Dive — Implicit Differentiation
> Supporting topic for [[2.6 Implicit Differentiation]].

## Why We Need It

Many curves cannot be written as $y = f(x)$. For example:
- Circle: $x^2 + y^2 = 25$ (not a function — fails vertical line test)
- Folium of Descartes: $x^3 + y^3 = 6xy$
- Ellipse: $\frac{x^2}{4} + \frac{y^2}{9} = 1$

Even when we *can* solve for $y$, it may be easier not to. Implicit differentiation lets us find $\frac{dy}{dx}$ directly from the equation.

## The Chain Rule Connection

The key insight: treat $y$ as a function of $x$ (even if we don't know the formula). Then by the chain rule:

$$\frac{d}{dx}[f(y)] = f'(y) \cdot \frac{dy}{dx}$$

For example:
- $\frac{d}{dx}(y^2) = 2y \cdot \frac{dy}{dx}$
- $\frac{d}{dx}(\sin y) = \cos y \cdot \frac{dy}{dx}$
- $\frac{d}{dx}(e^y) = e^y \cdot \frac{dy}{dx}$

## Step-by-Step Procedure

> [!def] Algorithm for Implicit Differentiation
> 1. **Differentiate both sides** of the equation with respect to $x$
> 2. Apply the chain rule: every time you differentiate a $y$-term, **attach** $\frac{dy}{dx}$
> 3. Apply product/quotient rules where $x$ and $y$ are multiplied/divided
> 4. **Collect** all $\frac{dy}{dx}$ terms on one side
> 5. **Factor out** $\frac{dy}{dx}$
> 6. **Solve** for $\frac{dy}{dx}$

## Tangent and Normal Lines

Once you have $\frac{dy}{dx}$, substitute the point $(x_0, y_0)$ to get the slope $m$:
- **Tangent line:** $y - y_0 = m(x - x_0)$
- **Normal line** (perpendicular to tangent): $y - y_0 = -\frac{1}{m}(x - x_0)$

## Second Derivatives

To find $\frac{d^2y}{dx^2}$, differentiate $\frac{dy}{dx}$ implicitly again. The result will usually contain $\frac{dy}{dx}$ — substitute the expression you already found.

> [!example] Second Derivative of $x^2 + y^2 = 25$
> We found $\frac{dy}{dx} = -\frac{x}{y}$. Differentiate again:
> $$\frac{d^2y}{dx^2} = -\frac{y \cdot 1 - x \cdot \frac{dy}{dx}}{y^2} = -\frac{y - x\left(-\frac{x}{y}\right)}{y^2} = -\frac{y + \frac{x^2}{y}}{y^2} = -\frac{y^2 + x^2}{y^3} = -\frac{25}{y^3}$$

## Logarithmic Differentiation

A special technique using implicit differentiation after taking $\ln$ of both sides. Useful for:
- Products/quotients of many factors
- Variable base with variable exponent

**Procedure:**
1. Write $y = f(x)$
2. Take $\ln$ of both sides: $\ln y = \ln f(x)$
3. Simplify using log rules
4. Differentiate implicitly
5. Solve for $y'$ and substitute $y = f(x)$

> [!example] Differentiate $y = x^x$
> Take $\ln$: $\ln y = x \ln x$
>
> Differentiate: $\frac{1}{y} \cdot y' = \ln x + x \cdot \frac{1}{x} = \ln x + 1$
>
> Solve: $y' = y(\ln x + 1) = x^x(\ln x + 1)$

> [!example] Differentiate $y = \frac{x^{3/4}\sqrt{x^2+1}}{(3x+2)^5}$
> Take $\ln$: $\ln y = \frac{3}{4}\ln x + \frac{1}{2}\ln(x^2+1) - 5\ln(3x+2)$
>
> Differentiate: $\frac{y'}{y} = \frac{3}{4x} + \frac{x}{x^2+1} - \frac{15}{3x+2}$
>
> Solve: $y' = \frac{x^{3/4}\sqrt{x^2+1}}{(3x+2)^5}\left(\frac{3}{4x} + \frac{x}{x^2+1} - \frac{15}{3x+2}\right)$

## Practice Problems

> [!example] Practice 1
> Find $\frac{dy}{dx}$ for $x^2y + xy^2 = 6$.
>
> **Solution.** Differentiate: $2xy + x^2y' + y^2 + 2xyy' = 0$
>
> Factor: $y'(x^2 + 2xy) = -2xy - y^2$
>
> $$y' = \frac{-2xy - y^2}{x^2 + 2xy}$$

> [!example] Practice 2
> Find $\frac{dy}{dx}$ for $\cos(xy) = 1 + \sin y$.
>
> **Solution.** Differentiate: $-\sin(xy) \cdot (y + xy') = y'\cos y$
>
> Expand: $-y\sin(xy) - x\sin(xy) \cdot y' = y'\cos y$
>
> Collect: $y'[-x\sin(xy) - \cos y] = y\sin(xy)$
>
> $$y' = \frac{-y\sin(xy)}{x\sin(xy) + \cos y}$$

> [!example] Practice 3
> Differentiate $y = (\sin x)^x$ using logarithmic differentiation.
>
> **Solution.** $\ln y = x\ln(\sin x)$
>
> $\frac{y'}{y} = \ln(\sin x) + x \cdot \frac{\cos x}{\sin x} = \ln(\sin x) + x\cot x$
>
> $y' = (\sin x)^x[\ln(\sin x) + x\cot x]$

## See Also
- [[2.6 Implicit Differentiation]]
- [[Chain Rule]]
- [[Product and Quotient Rules]]
