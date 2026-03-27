---
section: "1.6"
date_covered:
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, limits]
---

# The Squeeze Theorem

The Squeeze Theorem (also called the Sandwich Theorem or Pinching Theorem) handles limits where algebraic simplification is impossible — typically when oscillating functions like $\sin(1/x)$ or $\cos(1/x)$ are involved.

## Statement

> [!thm] The Squeeze Theorem
> If $f(x) \leq g(x) \leq h(x)$ for all $x$ in some open interval containing $a$ (except possibly at $a$ itself), and
> $$\lim_{x\to a} f(x) = \lim_{x\to a} h(x) = L,$$
> then
> $$\lim_{x\to a} g(x) = L.$$

## Geometric Intuition

Picture the graph of $g(x)$ trapped between the graphs of $f(x)$ and $h(x)$. As $x\to a$, the floor $f$ and the ceiling $h$ both converge to $L$. Since $g$ is sandwiched between them, it has nowhere to go except $L$.

Think of it like walking down a hallway that narrows to a single point — no matter how erratically you move side to side, you're forced through that point.

## Proof (Epsilon-Delta)

> [!thm] Proof
> **Given:** $f(x) \leq g(x) \leq h(x)$ near $a$, and $\lim_{x\to a}f(x) = \lim_{x\to a}h(x) = L$.
>
> **Goal:** Show $\lim_{x\to a}g(x) = L$.
>
> Let $\epsilon > 0$. Since $\lim_{x\to a}f(x)=L$, there exists $\delta_1>0$ such that
> $$0<|x-a|<\delta_1 \implies |f(x)-L|<\epsilon \implies L-\epsilon < f(x).$$
>
> Since $\lim_{x\to a}h(x)=L$, there exists $\delta_2>0$ such that
> $$0<|x-a|<\delta_2 \implies |h(x)-L|<\epsilon \implies h(x) < L+\epsilon.$$
>
> Also, there exists $\delta_3>0$ such that $f(x)\leq g(x)\leq h(x)$ whenever $0<|x-a|<\delta_3$.
>
> Let $\delta = \min(\delta_1,\delta_2,\delta_3)$. Then for $0<|x-a|<\delta$:
> $$L - \epsilon < f(x) \leq g(x) \leq h(x) < L + \epsilon$$
> $$\implies |g(x) - L| < \epsilon. \quad\blacksquare$$

## The Canonical Limit: $\lim_{x\to 0}\frac{\sin x}{x} = 1$

This is one of the most important limits in calculus. It cannot be evaluated by direct substitution (gives $\frac{0}{0}$) or algebraic manipulation. The proof uses the Squeeze Theorem together with a geometric argument.

> [!thm] Geometric Unit-Circle Argument
> Consider a unit circle centered at the origin, with a central angle $0 < x < \frac{\pi}{2}$.
>
> **Three areas to compare:**
> 1. **Triangle $OAB$ (inscribed):** Area $= \frac{1}{2}\sin x$
> 2. **Circular sector $OAB$:** Area $= \frac{1}{2}x$ (in radians)
> 3. **Triangle $OAT$ (circumscribed):** Area $= \frac{1}{2}\tan x$
>
> Since the inscribed triangle $\subseteq$ sector $\subseteq$ circumscribed triangle:
> $$\frac{1}{2}\sin x \leq \frac{1}{2}x \leq \frac{1}{2}\tan x$$
>
> Divide through by $\frac{1}{2}\sin x > 0$:
> $$1 \leq \frac{x}{\sin x} \leq \frac{1}{\cos x}$$
>
> Take reciprocals (flipping inequalities):
> $$\cos x \leq \frac{\sin x}{x} \leq 1$$
>
> Since $\lim_{x\to 0^+}\cos x = 1$ and $\lim_{x\to 0^+}1 = 1$, the Squeeze Theorem gives
> $$\lim_{x\to 0^+}\frac{\sin x}{x} = 1.$$
>
> Since $\frac{\sin x}{x}$ is an even function (because $\sin(-x)=-\sin x$), the left-hand limit equals the right-hand limit, so
> $$\lim_{x\to 0}\frac{\sin x}{x} = 1.$$

> [!tip] Related Limit
> From $\lim_{x\to 0}\frac{\sin x}{x}=1$, we can derive:
> $$\lim_{x\to 0}\frac{\cos x - 1}{x} = 0$$
> by writing $\cos x - 1 = \frac{-\sin^2 x}{1+\cos x}$ and using the $\sin x/x$ limit.

## Worked Examples

> [!example] Example 1 — The classic: $\lim_{x\to 0}x^2\sin(1/x)$
> We cannot compute $\lim_{x\to 0}\sin(1/x)$ because it oscillates wildly between $-1$ and $1$.
>
> But $-1 \leq \sin(1/x) \leq 1$ for all $x\neq 0$, so:
> $$-x^2 \leq x^2\sin(1/x) \leq x^2$$
>
> Since $\lim_{x\to 0}(-x^2) = 0$ and $\lim_{x\to 0}x^2 = 0$, the Squeeze Theorem gives:
> $$\lim_{x\to 0}x^2\sin(1/x) = 0.$$

> [!example] Example 2 — $\lim_{x\to 0}x^2\cos(1/x)$
> Same idea. Since $-1\leq\cos(1/x)\leq 1$:
> $$-x^2 \leq x^2\cos(1/x) \leq x^2$$
>
> Both bounds approach $0$, so:
> $$\lim_{x\to 0}x^2\cos(1/x) = 0.$$

> [!example] Example 3 — $\lim_{x\to\infty}\frac{\sin x}{x}$
> Since $-1\leq\sin x\leq 1$ for all $x$, dividing by $x>0$:
> $$-\frac{1}{x}\leq\frac{\sin x}{x}\leq\frac{1}{x}$$
>
> Since $\lim_{x\to\infty}\frac{1}{x}=0$ and $\lim_{x\to\infty}\left(-\frac{1}{x}\right)=0$:
> $$\lim_{x\to\infty}\frac{\sin x}{x} = 0.$$

> [!example] Example 4 — $\lim_{x\to 0}x\cos(e^{1/x^2})$
> No matter how wildly $e^{1/x^2}$ blows up, cosine keeps the output in $[-1,1]$:
> $$-|x| \leq x\cos(e^{1/x^2}) \leq |x|$$
>
> Both bounds $\to 0$, so the limit is $0$.

## When to Use the Squeeze Theorem

> [!tip] Recognition Checklist
> Use the Squeeze Theorem when you see:
> - A **bounded oscillating factor** like $\sin(\cdot)$ or $\cos(\cdot)$ multiplied by something going to $0$
> - A function trapped between two others that converge to the same value
> - A limit that resists all algebraic techniques (factoring, rationalizing, etc.)
>
> **General pattern:** If $|g(x)| \leq B$ for some bound $B$ and $\lim_{x\to a}f(x)=0$, then $\lim_{x\to a}f(x)\cdot g(x)=0$. This is actually a consequence of the Squeeze Theorem.

## See Also

- [[1.6 Calculating Limits]]
- [[Limit Laws]]
- [[Direct Substitution Property]]
