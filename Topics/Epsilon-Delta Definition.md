---
section: "1.7"
date_covered:
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, limits, epsilon-delta]
---

# Epsilon-Delta Definition

The **epsilon-delta definition** is the rigorous, formal definition of a limit. It replaces the vague phrase "f(x) gets close to L" with a precise, quantified statement that can be used in mathematical proofs.

---

## The Formal Definition

> [!def] Precise Definition of a Limit
> Let $f$ be a function defined on some open interval containing $a$, except possibly at $a$ itself. Then we say
> $$\lim_{x \to a} f(x) = L$$
> if **for every** $\varepsilon > 0$ **there exists** a $\delta > 0$ such that
> $$0 < |x - a| < \delta \implies |f(x) - L| < \varepsilon.$$

---

## Dissecting the Definition Piece by Piece

### "$\text{For every } \varepsilon > 0$"

- $\varepsilon$ (epsilon) represents an **arbitrary positive tolerance** around the output value $L$.
- "For every" means this must work no matter how small $\varepsilon$ is. Someone could pick $\varepsilon = 0.1$, or $\varepsilon = 0.001$, or $\varepsilon = 10^{-100}$ — your argument must handle all of them.
- **Plain English:** "No matter how tight the accuracy requirement on the output..."

### "$\text{there exists } \delta > 0$"

- $\delta$ (delta) is a positive number that controls how close $x$ must be to $a$.
- "There exists" means you need to **find** (or prove the existence of) at least one such $\delta$. It can (and usually does) depend on $\varepsilon$.
- **Plain English:** "...we can find a closeness requirement on the input..."

### "$0 < |x - a| < \delta$"

- $|x - a| < \delta$ means $x$ is within distance $\delta$ of $a$, i.e., $x \in (a - \delta, a + \delta)$.
- The condition $0 < |x - a|$ means $x \neq a$. We explicitly **exclude** the point $a$ itself — we care about what happens *near* $a$, not *at* $a$.
- **Plain English:** "...such that whenever the input is within $\delta$ of $a$ (but not equal to $a$)..."

### "$|f(x) - L| < \varepsilon$"

- This says the output $f(x)$ is within distance $\varepsilon$ of $L$, i.e., $f(x) \in (L - \varepsilon, L + \varepsilon)$.
- **Plain English:** "...the output is within $\varepsilon$ of the limit value $L$."

### Putting It All Together (Plain English)

> No matter how tight the accuracy requirement on the output ($\varepsilon$), we can always find a closeness requirement on the input ($\delta$) that guarantees the output lands within $\varepsilon$ of $L$, as long as the input is within $\delta$ of $a$ (but not equal to $a$).

---

## The $\varepsilon$-$\delta$ "Game" Metaphor

Think of the definition as a **two-player game** between a Skeptic and a Prover:

| Round | Who Acts | What They Do |
|---|---|---|
| 1 | **Skeptic** | Picks any $\varepsilon > 0$ (an accuracy challenge) |
| 2 | **Prover** | Responds with a $\delta > 0$ (a closeness guarantee) |
| 3 | **Verification** | Check: does $0 < \lvert x - a \rvert < \delta$ always imply $\lvert f(x) - L \rvert < \varepsilon$? |

- If the **Prover can always win** — no matter what $\varepsilon$ the Skeptic throws — then $\lim_{x \to a} f(x) = L$.
- If the **Skeptic can find even one** $\varepsilon$ for which the Prover has no valid response, the limit either doesn't equal $L$ or doesn't exist.

> [!tip] Key Insight
> The Prover's $\delta$ is allowed to depend on $\varepsilon$. A smaller $\varepsilon$ (tighter challenge) typically requires a smaller $\delta$ (closer input). The Prover just needs a **rule** that produces a valid $\delta$ for every possible $\varepsilon$.

---

## Graphical Interpretation

Imagine the graph of $y = f(x)$:

1. Draw a **horizontal band** of width $2\varepsilon$ centered at $y = L$: the strip from $y = L - \varepsilon$ to $y = L + \varepsilon$.
2. Now find a **vertical band** of width $2\delta$ centered at $x = a$: the strip from $x = a - \delta$ to $x = a + \delta$.
3. The definition says: for **any** horizontal band (any $\varepsilon > 0$), you can find a vertical band (some $\delta > 0$) such that the graph of $f$, within the vertical band (excluding $x = a$), stays entirely inside the horizontal band.

> [!tip] Visual Checkpoint
> If you can always "trap" the curve inside the $\varepsilon$-band by making the $\delta$-band narrow enough, the limit is $L$.

---

## Why We Require $0 < |x - a|$

The strict inequality $0 < |x - a|$ (equivalently, $x \neq a$) is essential because:

- The limit describes the **behavior of $f$ near $a$**, not at $a$.
- $f(a)$ might not even be defined (e.g., $\frac{\sin x}{x}$ at $x = 0$).
- Even if $f(a)$ is defined, it might not equal $L$ (removable discontinuity).
- The limit is about the **trend** as $x$ approaches $a$, regardless of what happens at $a$ itself.

> [!example] Illustration
> Define $f(x) = \begin{cases} x^2 & x \neq 1 \\ 5 & x = 1 \end{cases}$. Then $\lim_{x \to 1} f(x) = 1$, even though $f(1) = 5$. The $0 < |x - a|$ condition ensures the value at $a$ is irrelevant.

---

## Negation of the Definition

To prove a limit does **not** equal $L$, we negate the definition:

> [!def] Negation — Limit Does Not Equal $L$
> $\lim_{x \to a} f(x) \neq L$ means: **there exists** $\varepsilon_0 > 0$ such that **for every** $\delta > 0$, **there exists** $x$ with
> $$0 < |x - a| < \delta \quad \text{and} \quad |f(x) - L| \geq \varepsilon_0.$$

In the game metaphor: the Skeptic can find **one specific** $\varepsilon_0$ that the Prover can never beat — no matter how small $\delta$ is, there will always be some "bad" $x$ within $\delta$ of $a$ whose output is at least $\varepsilon_0$ away from $L$.

### How to Use the Negation

1. **Propose** a specific $\varepsilon_0 > 0$.
2. **Let** $\delta > 0$ be arbitrary.
3. **Find** a specific $x$ satisfying $0 < |x - a| < \delta$ but $|f(x) - L| \geq \varepsilon_0$.

If you can do this for every $\delta$, the limit is not $L$.

> [!example] Proving a Limit Does Not Exist
> **Claim:** $\lim_{x \to 0} \sin\!\left(\frac{1}{x}\right)$ does not exist.
>
> **Proof:** Suppose for contradiction that $\lim_{x \to 0} \sin(1/x) = L$ for some $L$.
>
> Choose $\varepsilon_0 = \frac{1}{2}$.
>
> Let $\delta > 0$ be given. We need to find $x$ with $0 < |x| < \delta$ such that $|\sin(1/x) - L| \geq \frac{1}{2}$.
>
> Within any interval $(-\delta, \delta) \setminus \{0\}$, we can find:
> - $x_1$ such that $\sin(1/x_1) = 1$ (take $x_1 = \frac{1}{2n\pi + \pi/2}$ for large $n$)
> - $x_2$ such that $\sin(1/x_2) = -1$ (take $x_2 = \frac{1}{2n\pi - \pi/2}$ for large $n$)
>
> Since $|\sin(1/x_1) - \sin(1/x_2)| = |1 - (-1)| = 2$, by the triangle inequality, at least one of $|\sin(1/x_1) - L|$ or $|\sin(1/x_2) - L|$ must be $\geq 1 > \frac{1}{2}$.
>
> So for any proposed $L$, we found $\varepsilon_0 = \frac{1}{2}$ that cannot be satisfied. Therefore the limit does not exist. $\blacksquare$

---

## See Also

- [[1.7 Precise Definition of a Limit]] — main section notes with worked proofs
- [[Epsilon-Delta Proof Strategies]] — step-by-step techniques for writing proofs
