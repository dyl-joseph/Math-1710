---
section: "1.8"
date_covered:
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, continuity]
---

# Intermediate Value Theorem

The Intermediate Value Theorem (IVT) is one of the most important consequences of continuity. It formalizes the intuitive idea that a continuous curve cannot "skip over" values.

---

## Theorem Statement

> [!thm] The Intermediate Value Theorem
> Suppose $f$ is **continuous on the closed interval** $[a,b]$ and let $N$ be any number between $f(a)$ and $f(b)$, where $f(a) \neq f(b)$. Then there exists at least one number $c \in (a,b)$ such that
> $$f(c) = N.$$

**Hypotheses (all are required):**
1. $f$ is continuous on $[a,b]$ — no breaks, holes, or jumps on the entire interval.
2. $N$ is strictly between $f(a)$ and $f(b)$ — that is, $\min(f(a),f(b)) < N < \max(f(a),f(b))$.

**Conclusion:** There is some $c$ in the open interval $(a,b)$ where $f$ hits the value $N$. There may be more than one such $c$ — the theorem only guarantees *at least one*.

---

## Why Continuity Is Required

> [!example] Counterexample — Discontinuous Function Violating IVT
> $$f(x) = \begin{cases} 1 & x \leq 1 \\ 3 & x > 1 \end{cases}$$
>
> On $[0,2]$: $f(0) = 1$ and $f(2) = 3$. Let $N = 2$, which is between $1$ and $3$.
>
> But there is **no** $c \in (0,2)$ with $f(c) = 2$, because $f$ only takes the values $1$ and $3$. The IVT fails because $f$ has a jump discontinuity at $x = 1$.

This shows that every hypothesis matters. If you skip the continuity check, you cannot invoke the theorem.

---

## Geometric Meaning

Think of the graph of $f$ as a continuous curve drawn from the point $(a, f(a))$ to the point $(b, f(b))$ **without lifting your pen**. The IVT says this curve must cross every horizontal line $y = N$ between $y = f(a)$ and $y = f(b)$ at least once.

Equivalently: if you start below a horizontal line and end above it (or vice versa), the continuous curve must cross that line somewhere in between.

---

## Proof Idea

The full proof uses the **completeness property** of the real numbers (the least upper bound axiom) and is beyond the scope of Calc I. But the intuition is:

Consider the set $S = \{x \in [a,b] : f(x) < N\}$. This set is nonempty (it contains $a$ if $f(a) < N$) and bounded above by $b$. By completeness, $S$ has a least upper bound $c$. Using continuity at $c$, one shows that $f(c)$ can be neither less than $N$ nor greater than $N$, so $f(c) = N$.

The key ingredient that makes this work is that the reals have no "gaps" — every bounded-above nonempty set has a supremum.

---

## Application: Proving a Root Exists

The most common Calc I application of IVT is showing that an equation $f(x) = 0$ has a solution in some interval.

> [!thm] Corollary — Root-Finding Version
> If $f$ is continuous on $[a,b]$ and $f(a)$ and $f(b)$ have **opposite signs** (one positive, one negative), then there exists at least one $c \in (a,b)$ such that $f(c) = 0$.

This is just the IVT with $N = 0$.

### Method
1. Define $f(x)$ so that the equation becomes $f(x) = 0$.
2. **Verify $f$ is continuous** on some interval $[a,b]$ (state why — polynomial, composition of continuous functions, etc.).
3. Compute $f(a)$ and $f(b)$ and check they have opposite signs.
4. Conclude by IVT: there exists $c \in (a,b)$ with $f(c) = 0$.

---

## Worked Examples

> [!example] Example 1 — Show $x^3 + x - 1 = 0$ has a root in $(0,1)$
> Let $f(x) = x^3 + x - 1$.
>
> **Continuity:** $f$ is a polynomial, so it is continuous everywhere — in particular, on $[0,1]$.
>
> **Sign check:**
> $$f(0) = 0 + 0 - 1 = -1 < 0$$
> $$f(1) = 1 + 1 - 1 = 1 > 0$$
>
> Since $f(0) < 0 < f(1)$ and $f$ is continuous on $[0,1]$, the IVT guarantees there exists at least one $c \in (0,1)$ such that $f(c) = 0$.

> [!example] Example 2 — Show $\cos x = x$ has a solution
> Rewrite as $f(x) = \cos x - x = 0$.
>
> **Continuity:** $\cos x$ is continuous everywhere and $x$ is continuous everywhere, so $f(x) = \cos x - x$ is continuous on any interval.
>
> **Find an interval where $f$ changes sign.** Try $[0, \pi/2]$:
> $$f(0) = \cos 0 - 0 = 1 > 0$$
> $$f(\pi/2) = \cos(\pi/2) - \pi/2 = 0 - \pi/2 \approx -1.571 < 0$$
>
> Since $f(0) > 0 > f(\pi/2)$ and $f$ is continuous on $[0, \pi/2]$, the IVT guarantees there exists $c \in (0, \pi/2)$ with $f(c) = 0$, i.e., $\cos c = c$.

> [!example] Example 3 — Show $e^x = 3 - 2x$ has a solution
> Let $f(x) = e^x - 3 + 2x$.
>
> **Continuity:** $e^x$ and $2x - 3$ are both continuous everywhere, so $f$ is continuous.
>
> **Sign check on $[0,1]$:**
> $$f(0) = 1 - 3 + 0 = -2 < 0$$
> $$f(1) = e - 3 + 2 \approx 2.718 - 1 = 1.718 > 0$$
>
> By IVT, there exists $c \in (0,1)$ with $f(c) = 0$, so $e^c = 3 - 2c$.

---

## The Bisection Method

The IVT doesn't just tell us a root exists — it suggests a way to *find* it numerically.

**Idea:** Starting with $[a,b]$ where $f(a)$ and $f(b)$ have opposite signs, evaluate $f$ at the midpoint $m = \frac{a+b}{2}$:

- If $f(m) = 0$, we found the root.
- If $f(a)$ and $f(m)$ have opposite signs, the root is in $[a,m]$. Replace $b$ with $m$.
- If $f(m)$ and $f(b)$ have opposite signs, the root is in $[m,b]$. Replace $a$ with $m$.

Repeat. Each step cuts the interval in half, so after $n$ steps the root is trapped in an interval of width $\frac{b-a}{2^n}$.

> [!example] Bisection applied to $x^3 + x - 1 = 0$ on $[0,1]$
> - $f(0) = -1$, $f(1) = 1$. Midpoint: $m = 0.5$, $f(0.5) = 0.125 + 0.5 - 1 = -0.375 < 0$.
> - Root in $[0.5, 1]$. Midpoint: $m = 0.75$, $f(0.75) = 0.4219 + 0.75 - 1 = 0.1719 > 0$.
> - Root in $[0.5, 0.75]$. Midpoint: $m = 0.625$, $f(0.625) \approx -0.1309 < 0$.
> - Root in $[0.625, 0.75]$. Already narrowed to an interval of width $0.125$.
>
> Continuing this process converges to $c \approx 0.6824$.

---

## Common Exam Mistakes

> [!tip] Mistakes to Avoid
> 1. **Forgetting to verify continuity.** You must explicitly state that $f$ is continuous on $[a,b]$ and say *why* (polynomial, rational with no zero in denominator, etc.). Without this, you cannot apply IVT.
> 2. **Forgetting to check opposite signs.** Compute $f(a)$ and $f(b)$ and explicitly note that one is positive and one is negative.
> 3. **Claiming IVT finds the root.** IVT only proves **existence**. It does not give the value of $c$ or tell you how many roots there are.
> 4. **Applying IVT when $N$ is not between $f(a)$ and $f(b)$.** The value $N$ must be strictly between the two endpoint values.
> 5. **Confusing IVT with the Mean Value Theorem.** IVT is about the function values; MVT (Section 4.2) is about the derivative.

---

## See Also

- [[1.8 Continuity]]
- [[Types of Discontinuity]]
- [[Limit Laws]]
