---
section: "1.7"
date_covered:
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, limits, epsilon-delta]
---

# Epsilon-Delta Proof Strategies

Every epsilon-delta proof follows the same two-phase workflow: **scratch work** (figuring out what $\delta$ should be) and then a **formal proof** (presenting it cleanly). This note covers strategies for different function types.

---

## The Universal Template

Every $\varepsilon$-$\delta$ proof has the same skeleton:

> [!tip] Proof Template
> **Let** $\varepsilon > 0$ be given.
>
> **Choose** $\delta = \text{(some expression involving } \varepsilon\text{)}$.
>
> **Suppose** $0 < |x - a| < \delta$.
>
> **Then** (chain of inequalities showing $|f(x) - L| < \varepsilon$).
>
> **Therefore** $\lim_{x \to a} f(x) = L$. $\blacksquare$

---

## The Two-Phase Workflow

### Phase 1: Scratch Work (Discovery)

This is where you figure out $\delta$. It is **not** part of the final proof, but it is essential.

1. **Write down** $|f(x) - L|$.
2. **Simplify/factor** until it looks like (something) $\cdot$ $|x - a|$ or can be bounded by (something) $\cdot$ $|x - a|$.
3. **Control** the "something" — if it depends on $x$, you'll need to bound it by restricting $\delta$.
4. **Solve** for $\delta$ in terms of $\varepsilon$.

### Phase 2: Formal Proof (Presentation)

Write the proof forward: start with "Let $\varepsilon > 0$," state your $\delta$, assume $0 < |x - a| < \delta$, and show $|f(x) - L| < \varepsilon$.

> [!tip] Important
> Scratch work goes **backward** (from goal to $\delta$). The formal proof goes **forward** (from $\delta$ to goal). This is normal — every epsilon-delta proof is written this way.

---

## Strategy 1: Linear Functions

**Goal:** Prove $\lim_{x \to a}(mx + b) = ma + b$.

This is the simplest case because $|f(x) - L|$ reduces directly to a multiple of $|x - a|$.

**Scratch work:**
$$|f(x) - L| = |(mx + b) - (ma + b)| = |m(x - a)| = |m| \cdot |x - a|$$

We need $|m| \cdot |x - a| < \varepsilon$, so $|x - a| < \frac{\varepsilon}{|m|}$.

**Choose:** $\delta = \dfrac{\varepsilon}{|m|}$ (assuming $m \neq 0$; if $m = 0$, any $\delta$ works).

> [!tip] Linear Shortcut
> For $\lim_{x \to a}(mx + b)$, always choose $\delta = \frac{\varepsilon}{|m|}$. Done.

---

## Strategy 2: Quadratic / Polynomial Functions

**Goal:** Prove $\lim_{x \to a} x^2 = a^2$ (or similar).

The key challenge: after factoring, you get a term that depends on $x$.

**Scratch work:**
$$|x^2 - a^2| = |x - a| \cdot |x + a|$$

The factor $|x + a|$ depends on $x$, so we can't directly solve for $\delta$. We need to **bound** $|x + a|$ by a constant.

### The $\delta \leq 1$ Trick

> [!def] The min$(1, \ldots)$ Trick
> To bound a factor that depends on $x$:
> 1. **Restrict** $\delta \leq 1$ (so $|x - a| < 1$, meaning $x \in (a-1, a+1)$).
> 2. **Use** $x \in (a-1, a+1)$ to get an upper bound on the troublesome factor.
> 3. **Choose** $\delta = \min\!\left(1, \frac{\varepsilon}{\text{bound}}\right)$.
>
> The $\min$ ensures **both** restrictions hold simultaneously.

**Why $\min$?** We need two things to be true at once:
- $\delta \leq 1$ (so our bound on the extra factor is valid)
- $\delta \leq \frac{\varepsilon}{\text{bound}}$ (so the final inequality works)

Taking $\delta = \min(1, \ldots)$ guarantees both.

**Detailed example for** $|x + a|$: If $\delta \leq 1$, then $|x - a| < 1$, so $a - 1 < x < a + 1$, meaning:
$$|x + a| \leq |x| + |a| < (|a| + 1) + |a| = 2|a| + 1$$

So $|x^2 - a^2| = |x - a| \cdot |x + a| < |x - a| \cdot (2|a| + 1)$.

Choose $\delta = \min\!\left(1, \dfrac{\varepsilon}{2|a| + 1}\right)$.

> [!tip] General Polynomial Strategy
> For any polynomial, factor out $|x - a|$, restrict $\delta \leq 1$, bound remaining factors using triangle inequality, then take $\delta = \min(1, \varepsilon / \text{bound})$.

---

## Strategy 3: Rational Functions

**Goal:** Prove limits of the form $\lim_{x \to a} \frac{p(x)}{q(x)}$.

Rational functions combine the polynomial challenge with **bounding the denominator away from zero**.

**Key idea:** You need $|q(x)|$ bounded below (not approaching 0), so restrict $\delta$ to ensure $x$ stays in a region where $|q(x)| \geq$ some positive constant.

**Scratch work for** $\lim_{x \to a} \frac{1}{x} = \frac{1}{a}$ (with $a \neq 0$):

$$\left|\frac{1}{x} - \frac{1}{a}\right| = \left|\frac{a - x}{ax}\right| = \frac{|x - a|}{|a| \cdot |x|}$$

We need a lower bound on $|x|$. Restrict $\delta \leq \frac{|a|}{2}$:
$$|x - a| < \frac{|a|}{2} \implies |x| > |a| - \frac{|a|}{2} = \frac{|a|}{2}$$

So $\frac{1}{|x|} < \frac{2}{|a|}$, and:
$$\frac{|x - a|}{|a| \cdot |x|} < \frac{|x - a| \cdot 2}{|a|^2}$$

Need this $< \varepsilon$, so $|x - a| < \frac{|a|^2 \varepsilon}{2}$.

**Choose:** $\delta = \min\!\left(\dfrac{|a|}{2},\; \dfrac{|a|^2\varepsilon}{2}\right)$.

> [!tip] Rational Function Strategy
> 1. Combine fractions and simplify $|f(x) - L|$.
> 2. Restrict $\delta$ to keep the denominator bounded away from zero.
> 3. Bound everything else.
> 4. Use $\min$ to combine all restrictions.

---

## Strategy 4: Square Root Functions

**Goal:** Prove limits like $\lim_{x \to a} \sqrt{x} = \sqrt{a}$.

**Key technique: Rationalize** (multiply by conjugate).

**Scratch work:**
$$|\sqrt{x} - \sqrt{a}| = \frac{|x - a|}{|\sqrt{x} + \sqrt{a}|}$$

Since $\sqrt{x} + \sqrt{a} \geq \sqrt{a}$ (for $x \geq 0$), we have:
$$|\sqrt{x} - \sqrt{a}| \leq \frac{|x - a|}{\sqrt{a}}$$

Need this $< \varepsilon$, so $|x - a| < \varepsilon\sqrt{a}$.

**Choose:** $\delta = \varepsilon\sqrt{a}$ (for $a > 0$).

> [!tip] Square Root Strategy
> Multiply and divide by the conjugate $\sqrt{x} + \sqrt{a}$. Then bound $\frac{1}{\sqrt{x} + \sqrt{a}}$ from above (usually $\leq \frac{1}{\sqrt{a}}$ works directly).

---

## Common Mistakes to Avoid

| Mistake | Why It's Wrong | Fix |
|---|---|---|
| Starting the proof with "$\delta = \ldots$" without knowing what it should be | You can't choose $\delta$ without doing scratch work first | Always do scratch work separately |
| Letting $\delta$ depend on $x$ | $\delta$ must be chosen **before** $x$ is specified — it can only depend on $\varepsilon$ (and constants like $a$) | Bound all $x$-dependent terms using $\delta \leq 1$ or similar |
| Forgetting $0 < \lvert x - a \rvert$ | Without this, the proof doesn't exclude $x = a$ | Always write the full condition |
| Using $\delta \leq 1$ but forgetting to take $\min$ | If $\varepsilon$ is large, $\frac{\varepsilon}{\text{bound}}$ might exceed 1, violating your restriction | Always write $\delta = \min(1, \ldots)$ |
| Writing the proof in discovery order | The formal proof should read forward from hypothesis to conclusion | Rearrange scratch work into a clean forward argument |
| Circular reasoning: assuming $\lvert f(x) - L \rvert < \varepsilon$ to derive it | You must derive the conclusion from the hypothesis, not assume it | Work from $0 < \lvert x - a \rvert < \delta$ toward $\lvert f(x) - L \rvert < \varepsilon$ |

---

## Practice Problems with Full Solutions

### Problem 1

**Prove** $\lim_{x \to 5}(3x + 1) = 16$.

**Scratch work:**
$$|f(x) - L| = |(3x + 1) - 16| = |3x - 15| = 3|x - 5|$$
Need $3|x - 5| < \varepsilon$, so $|x - 5| < \frac{\varepsilon}{3}$. Choose $\delta = \frac{\varepsilon}{3}$.

> [!example] Formal Proof
> Let $\varepsilon > 0$ be given. Choose $\delta = \frac{\varepsilon}{3}$.
>
> Suppose $0 < |x - 5| < \delta = \frac{\varepsilon}{3}$. Then:
> $$|(3x + 1) - 16| = |3x - 15| = 3|x - 5| < 3 \cdot \frac{\varepsilon}{3} = \varepsilon.$$
>
> Therefore $\lim_{x \to 5}(3x + 1) = 16$. $\blacksquare$

---

### Problem 2

**Prove** $\lim_{x \to 3} x^2 = 9$.

**Scratch work:**
$$|x^2 - 9| = |x - 3||x + 3|$$
Restrict $\delta \leq 1$: then $|x - 3| < 1$, so $2 < x < 4$, so $5 < x + 3 < 7$, so $|x + 3| < 7$.

Thus $|x^2 - 9| < 7|x - 3|$. Need $7|x - 3| < \varepsilon$, so $|x - 3| < \frac{\varepsilon}{7}$.

Choose $\delta = \min\!\left(1, \frac{\varepsilon}{7}\right)$.

> [!example] Formal Proof
> Let $\varepsilon > 0$ be given. Choose $\delta = \min\!\left(1, \frac{\varepsilon}{7}\right)$.
>
> Suppose $0 < |x - 3| < \delta$. Since $\delta \leq 1$, we have $|x - 3| < 1$, so $2 < x < 4$, hence $|x + 3| < 7$.
>
> Then:
> $$|x^2 - 9| = |x - 3| \cdot |x + 3| < \frac{\varepsilon}{7} \cdot 7 = \varepsilon.$$
>
> Therefore $\lim_{x \to 3} x^2 = 9$. $\blacksquare$

---

### Problem 3

**Prove** $\lim_{x \to 1} \frac{1}{x} = 1$.

**Scratch work:**
$$\left|\frac{1}{x} - 1\right| = \left|\frac{1 - x}{x}\right| = \frac{|x - 1|}{|x|}$$
Restrict $\delta \leq \frac{1}{2}$: then $|x - 1| < \frac{1}{2}$, so $\frac{1}{2} < x < \frac{3}{2}$, so $|x| > \frac{1}{2}$, so $\frac{1}{|x|} < 2$.

Thus $\frac{|x-1|}{|x|} < 2|x - 1|$. Need $2|x - 1| < \varepsilon$, so $|x - 1| < \frac{\varepsilon}{2}$.

Choose $\delta = \min\!\left(\frac{1}{2}, \frac{\varepsilon}{2}\right)$.

> [!example] Formal Proof
> Let $\varepsilon > 0$ be given. Choose $\delta = \min\!\left(\frac{1}{2}, \frac{\varepsilon}{2}\right)$.
>
> Suppose $0 < |x - 1| < \delta$. Since $\delta \leq \frac{1}{2}$, we have $\frac{1}{2} < x < \frac{3}{2}$, so $|x| > \frac{1}{2}$.
>
> Then:
> $$\left|\frac{1}{x} - 1\right| = \frac{|x - 1|}{|x|} < 2|x - 1| < 2 \cdot \frac{\varepsilon}{2} = \varepsilon.$$
>
> Therefore $\lim_{x \to 1} \frac{1}{x} = 1$. $\blacksquare$

---

### Problem 4

**Prove** $\lim_{x \to 9} \sqrt{x} = 3$.

**Scratch work:**
$$|\sqrt{x} - 3| = \frac{|x - 9|}{|\sqrt{x} + 3|}$$
Since $\sqrt{x} \geq 0$ for $x \geq 0$, we have $\sqrt{x} + 3 \geq 3$, so $\frac{1}{\sqrt{x} + 3} \leq \frac{1}{3}$.

Thus $|\sqrt{x} - 3| \leq \frac{|x - 9|}{3}$. Need $\frac{|x - 9|}{3} < \varepsilon$, so $|x - 9| < 3\varepsilon$.

Choose $\delta = 3\varepsilon$.

> [!example] Formal Proof
> Let $\varepsilon > 0$ be given. Choose $\delta = 3\varepsilon$.
>
> Suppose $0 < |x - 9| < \delta = 3\varepsilon$ (and $x > 0$ so $\sqrt{x}$ is defined). Then $\sqrt{x} + 3 \geq 3 > 0$, so:
> $$|\sqrt{x} - 3| = \frac{|x - 9|}{\sqrt{x} + 3} \leq \frac{|x - 9|}{3} < \frac{3\varepsilon}{3} = \varepsilon.$$
>
> Therefore $\lim_{x \to 9} \sqrt{x} = 3$. $\blacksquare$

---

## See Also

- [[Epsilon-Delta Definition]] — deep dive into the definition itself
- [[1.7 Precise Definition of a Limit]] — main section notes with more worked proofs
