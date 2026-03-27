---
section: "3.1"
date_covered: "2026-02-17"
textbook: "Stewart Calculus 9e"
tags: [calculus, derivatives, extrema, theorems]
---

# Extreme Value Theorem and Fermat's Theorem

> [!info] Deep Dive — Key Theorems for Extrema
> Supporting topic for [[3.1 Maximum and Minimum Values]].

## The Extreme Value Theorem

> [!thm] Extreme Value Theorem (EVT)
> If $f$ is **continuous** on a **closed interval** $[a, b]$, then $f$ attains an **absolute maximum** and an **absolute minimum** on $[a, b]$.
>
> That is, there exist $c, d \in [a, b]$ such that $f(c) \le f(x) \le f(d)$ for all $x \in [a, b]$.

### Why Both Hypotheses Matter

**Continuity is required:**
- $f(x) = \begin{cases} x & 0 \le x < 1 \\ 0 & x = 1 \end{cases}$ on $[0, 1]$: gets arbitrarily close to 1 but never reaches it. No absolute max.

**Closed interval is required:**
- $f(x) = x$ on $(0, 1)$: no absolute max or min (endpoints not included).
- $f(x) = \frac{1}{x}$ on $(0, 1]$: unbounded as $x \to 0^+$, no absolute max.

> [!tip] The EVT guarantees existence but doesn't tell you where the extrema are. That's what Fermat's Theorem and the Closed Interval Method are for.

## Fermat's Theorem

> [!thm] Fermat's Theorem
> If $f$ has a local maximum or minimum at $c$, and if $f'(c)$ exists, then $f'(c) = 0$.

**Contrapositive:** If $f'(c) \neq 0$, then $f$ does NOT have a local extremum at $c$.

### Proof (for local maximum)

Suppose $f$ has a local max at $c$ and $f'(c)$ exists.

Since $f(c) \ge f(x)$ for $x$ near $c$:

**From the right** ($h > 0$):
$$\frac{f(c+h) - f(c)}{h} \le 0 \implies f'(c) = \lim_{h \to 0^+} \frac{f(c+h) - f(c)}{h} \le 0$$

**From the left** ($h < 0$):
$$\frac{f(c+h) - f(c)}{h} \ge 0 \implies f'(c) = \lim_{h \to 0^-} \frac{f(c+h) - f(c)}{h} \ge 0$$

Since $f'(c) \le 0$ and $f'(c) \ge 0$, we conclude $f'(c) = 0$. $\blacksquare$

### What Fermat's Theorem Does NOT Say

> [!tip] Common Misinterpretation
> Fermat's Theorem says: local extremum $\implies$ $f'(c) = 0$ or $f'(c)$ DNE.
>
> It does **NOT** say: $f'(c) = 0$ $\implies$ local extremum.
>
> Counterexample: $f(x) = x^3$, $f'(0) = 0$, but no extremum at $x = 0$.

The theorem tells us where to **look** (critical numbers), not that we'll **find** an extremum there.

## The Closed Interval Method

Combining EVT and Fermat's Theorem gives a procedure for finding absolute extrema on $[a, b]$:

> [!def] Closed Interval Method
> To find the absolute max and min of a continuous function $f$ on $[a, b]$:
> 1. Find all **critical numbers** of $f$ in $(a, b)$
> 2. Evaluate $f$ at each critical number
> 3. Evaluate $f$ at the **endpoints** $a$ and $b$
> 4. The **largest** value is the absolute max; the **smallest** is the absolute min

> [!example] Example
> Find absolute extrema of $f(x) = x^3 - 3x + 1$ on $[-2, 2]$.
>
> $f'(x) = 3x^2 - 3 = 3(x-1)(x+1) = 0 \implies x = \pm 1$
>
> | $x$ | $f(x)$ |
> |---|---|
> | $-2$ | $-8 + 6 + 1 = -1$ |
> | $-1$ | $-1 + 3 + 1 = 3$ |
> | $1$ | $1 - 3 + 1 = -1$ |
> | $2$ | $8 - 6 + 1 = 3$ |
>
> Absolute max: $3$ (at $x = -1$ and $x = 2$). Absolute min: $-1$ (at $x = -2$ and $x = 1$).

## See Also
- [[3.1 Maximum and Minimum Values]]
- [[Critical Numbers]]
- [[Intermediate Value Theorem]] — another existence theorem requiring continuity on $[a,b]$
