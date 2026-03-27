---
section: "1.5"
date_covered:
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, limits]
---

# Intuitive Idea of a Limit

## The Central Question

The limit is the most fundamental concept in calculus — derivatives, integrals, and continuity are **all** defined using limits. The intuitive idea is simple:

> [!def] Informal Definition of a Limit
> We write
> $$\lim_{x \to a} f(x) = L$$
> and say "the limit of $f(x)$, as $x$ approaches $a$, equals $L$" if we can make the values of $f(x)$ **arbitrarily close** to $L$ by restricting $x$ to be sufficiently close to $a$ (on either side) **but not equal to** $a$.

The key phrase is *but not equal to $a$*. A limit asks: **what is $f(x)$ approaching?** — not **what does $f(x)$ equal?**

## Why $f(a)$ Doesn't Matter

The value $f(a)$ — or whether $f(a)$ even exists — is completely irrelevant to $\lim_{x \to a} f(x)$. Consider three scenarios:

### Scenario 1: Limit equals function value

Let $f(x) = x^2$. Then $\lim_{x \to 3} f(x) = 9$ and $f(3) = 9$. The limit and the function value agree — this is the "nice" case.

### Scenario 2: Function undefined at $a$, but limit exists

Let $g(x) = \dfrac{x^2 - 1}{x - 1}$. This function is **undefined** at $x = 1$ (division by zero). But for $x \neq 1$:
$$g(x) = \frac{(x-1)(x+1)}{x-1} = x + 1$$

So as $x \to 1$, $g(x) \to 2$. The limit is $2$ even though $g(1)$ does not exist.

### Scenario 3: Function defined at $a$, but limit is different

Define:
$$h(x) = \begin{cases} x + 1 & \text{if } x \neq 1 \\ 5 & \text{if } x = 1 \end{cases}$$

Here $h(1) = 5$, but $\lim_{x \to 1} h(x) = 2$ because as $x$ approaches $1$, the formula $x + 1$ gives values approaching $2$. The single assigned value $h(1) = 5$ doesn't affect the limit.

> [!tip] Core Principle
> The limit examines the **trend** of $f(x)$ near $a$, ignoring what happens **at** $a$ itself.

## Estimating Limits from Tables

One way to guess a limit is to compute $f(x)$ for values of $x$ approaching $a$ from both sides.

> [!example] Table Estimation
> Estimate $\displaystyle\lim_{x \to 1} \frac{x^2 - 1}{x - 1}$.
>
> | $x$ | $f(x)$ |
> |---|---|
> | $0.9$ | $1.9$ |
> | $0.99$ | $1.99$ |
> | $0.999$ | $1.999$ |
> | $1.001$ | $2.001$ |
> | $1.01$ | $2.01$ |
> | $1.1$ | $2.1$ |
>
> From both sides, $f(x)$ approaches $2$. So $\displaystyle\lim_{x \to 1} \frac{x^2 - 1}{x - 1} = 2$.

> [!tip] Warning About Tables
> Tables can be **misleading**. They only show finitely many values and can miss oscillatory or other pathological behavior. Tables give evidence, not proof.

## Estimating Limits from Graphs

On a graph, $\lim_{x \to a} f(x) = L$ means: as you trace the curve from **both sides** toward $x = a$, the $y$-values approach $L$.

> [!example] Reading a Graph
> Imagine the graph of $f(x) = \dfrac{\sin x}{x}$ near $x = 0$:
> - The function is undefined at $x = 0$ (there's a **hole** in the graph).
> - As $x \to 0$ from either side, the curve approaches $y = 1$.
> - Therefore $\displaystyle\lim_{x \to 0} \frac{\sin x}{x} = 1$.
>
> This is one of the most important limits in calculus. It's used later to derive the derivative of $\sin x$.

> [!example] Graph with a Hole Filled Incorrectly
> Suppose a graph shows a curve approaching $y = 3$ from both sides as $x \to 2$, but there is a **solid dot** at $(2, 1)$ (meaning $f(2) = 1$) and an **open circle** at $(2, 3)$.
>
> The limit is $3$, **not** $1$. The solid dot tells you the function value; the open circle and the approaching curve tell you the limit.

## When Limits Fail to Exist

A limit $\lim_{x \to a} f(x)$ **does not exist (DNE)** in three common situations:

### 1. Different One-Sided Limits

If $f(x)$ approaches different values from the left and right, the two-sided limit does not exist.

> [!example] Jump Discontinuity
> The **Heaviside function**:
> $$H(t) = \begin{cases} 0 & \text{if } t < 0 \\ 1 & \text{if } t \geq 0 \end{cases}$$
>
> As $t \to 0^-$, $H(t) = 0$. As $t \to 0^+$, $H(t) = 1$. Since $0 \neq 1$, $\lim_{t \to 0} H(t)$ **DNE**.

### 2. Unbounded Behavior

If $f(x) \to \infty$ or $f(x) \to -\infty$ as $x \to a$, the limit does not exist (in the strict sense). We sometimes write $\lim_{x \to a} f(x) = \infty$ as a descriptive shorthand, but $\infty$ is not a real number.

> [!example] Unbounded Near a Point
> $f(x) = \dfrac{1}{x^2}$ near $x = 0$: as $x \to 0$, $f(x)$ grows without bound. We write $\lim_{x \to 0} \frac{1}{x^2} = \infty$, but the limit does not exist in the finite sense.

### 3. Oscillation

If $f(x)$ oscillates indefinitely as $x \to a$ without settling on a single value, the limit does not exist.

> [!example] Oscillation
> $f(x) = \sin\!\left(\dfrac{1}{x}\right)$ near $x = 0$: as $x \to 0$, the argument $1/x \to \pm\infty$ and $\sin$ oscillates between $-1$ and $1$ infinitely often. The function never settles on a single value, so $\lim_{x \to 0} \sin\!\left(\frac{1}{x}\right)$ **DNE**.

## Common Misconceptions

| Misconception | Reality |
|---|---|
| "The limit is $f(a)$." | The limit may differ from $f(a)$, or $f(a)$ may not exist. |
| "If $f(a)$ is undefined, the limit DNE." | False — limits often exist where the function is undefined (e.g., $\frac{x^2-1}{x-1}$ at $x=1$). |
| "The limit is the value $f$ gets closer and closer to but never reaches." | Sometimes $f$ does equal the limit at nearby points. "Never reaches" is not part of the definition. |
| "If the graph has a hole, the limit DNE." | A hole at $(a, L)$ typically means $\lim_{x \to a} f(x) = L$. |

## See Also

- [[1.5 Introduction to Limits]]
- [[One-Sided Limits]]
- [[Infinite Limits and Vertical Asymptotes]]
