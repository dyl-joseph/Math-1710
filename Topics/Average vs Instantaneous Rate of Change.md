---
section: "2.1"
date_covered:
textbook: "Stewart's Calculus, 9th Edition"
tags: [calculus, derivatives]
---

# Average vs Instantaneous Rate of Change

The derivative has a second major interpretation beyond tangent-line slopes: it measures **how fast a quantity is changing**. This section unpacks the difference between the average rate of change over an interval and the instantaneous rate of change at a single moment.

---

## Average Rate of Change

> [!def] Average Rate of Change
> The **average rate of change** of $f$ on the interval $[a, b]$ is
> $$\frac{\Delta y}{\Delta x} = \frac{f(b) - f(a)}{b - a}.$$
> Geometrically, this is the **slope of the secant line** through $(a, f(a))$ and $(b, f(b))$.

The average rate of change tells you how much $f$ changes **per unit of $x$**, on average, across the interval. It says nothing about what happens at any particular point inside.

---

## Instantaneous Rate of Change

> [!def] Instantaneous Rate of Change
> The **instantaneous rate of change** of $f$ at $x = a$ is
> $$\lim_{h \to 0} \frac{f(a+h) - f(a)}{h} = \lim_{x \to a} \frac{f(x) - f(a)}{x - a} = f'(a).$$
> This is the **derivative** of $f$ at $a$ — equivalently, the **slope of the tangent line** at $(a, f(a))$.

The instantaneous rate is the limit of average rates as the interval shrinks to zero width. It captures the rate of change **at a single instant**.

---

## Geometric Summary

| Quantity | Formula | Geometry |
|---|---|---|
| Average rate of change on $[a,b]$ | $\dfrac{f(b)-f(a)}{b-a}$ | Slope of **secant** line |
| Instantaneous rate of change at $a$ | $f'(a) = \lim_{h\to 0}\dfrac{f(a+h)-f(a)}{h}$ | Slope of **tangent** line |

See [[Tangent Lines and Secant Lines]] for more on the geometric picture.

---

## Units of the Derivative

> [!tip] Units
> If $y = f(x)$, the units of $f'(x)$ are
> $$\frac{\text{units of } y}{\text{units of } x}.$$
> For example, if $s(t)$ is position in meters and $t$ is in seconds, then $s'(t)$ has units $\text{m/s}$ (velocity).

Keeping track of units is one of the easiest ways to check whether your answer makes sense in applied problems.

---

## Real-World Interpretations

| Context | $f(x)$ | $x$ | $f'(x)$ means… | Units |
|---|---|---|---|---|
| Motion | position $s(t)$ | time | velocity | m/s |
| Population | population $P(t)$ | time | growth rate | people/yr |
| Economics | cost $C(q)$ | quantity | marginal cost | \$/unit |
| Chemistry | concentration $[A](t)$ | time | reaction rate | mol/(L$\cdot$s) |
| Temperature | temp $T(t)$ | time | rate of heating/cooling | °C/min |

In each case the derivative answers: **"How fast is the output changing per unit of input, right now?"**

---

## Worked Examples

> [!example] Example 1 — Average vs Instantaneous Velocity
> A ball is dropped from a tower. Its height (in meters) after $t$ seconds is
> $$s(t) = 100 - 4.9t^2.$$
>
> **(a)** Average velocity on $[1, 3]$:
> $$v_{\text{avg}} = \frac{s(3) - s(1)}{3 - 1} = \frac{(100 - 44.1) - (100 - 4.9)}{2} = \frac{55.9 - 95.1}{2} = \frac{-39.2}{2} = -19.6 \;\text{m/s}$$
>
> **(b)** Instantaneous velocity at $t = 2$:
> $$v(2) = s'(2) = \lim_{h\to 0}\frac{s(2+h)-s(2)}{h}$$
> $$= \lim_{h\to 0}\frac{[100-4.9(2+h)^2]-[100-4.9(4)]}{h}$$
> $$= \lim_{h\to 0}\frac{-4.9(4+4h+h^2)+19.6}{h} = \lim_{h\to 0}\frac{-19.6-19.6h-4.9h^2+19.6}{h}$$
> $$= \lim_{h\to 0}\frac{-19.6h - 4.9h^2}{h} = \lim_{h\to 0}(-19.6 - 4.9h) = -19.6\;\text{m/s}$$
>
> The negative sign indicates the ball is falling (height is decreasing).

> [!example] Example 2 — Marginal Cost
> A factory's cost to produce $q$ units is $C(q) = 5000 + 8q - 0.01q^2$ dollars.
>
> **(a)** Average rate of change of cost from $q = 100$ to $q = 150$:
> $$\frac{C(150)-C(100)}{150-100} = \frac{[5000+1200-225]-[5000+800-100]}{50} = \frac{5975-5700}{50} = \frac{275}{50} = 5.50\;\text{\$/unit}$$
>
> **(b)** Instantaneous rate (marginal cost) at $q = 100$:
> $$C'(100) = \lim_{h\to 0}\frac{C(100+h)-C(100)}{h}$$
> $$= \lim_{h\to 0}\frac{[5000+8(100+h)-0.01(100+h)^2]-5700}{h}$$
> $$= \lim_{h\to 0}\frac{5000+800+8h-0.01(10000+200h+h^2)-5700}{h}$$
> $$= \lim_{h\to 0}\frac{5800+8h-100-2h-0.01h^2-5700}{h} = \lim_{h\to 0}\frac{6h-0.01h^2}{h}$$
> $$= \lim_{h\to 0}(6-0.01h) = 6\;\text{\$/unit}$$
>
> The 101st unit costs approximately \$6 to produce.

> [!example] Example 3 — Estimating from a Table
> The population of a bacterial colony is recorded:
>
> | $t$ (hours) | 0 | 1 | 2 | 3 | 4 |
> |---|---|---|---|---|---|
> | $P(t)$ (thousands) | 50 | 65 | 86 | 114 | 152 |
>
> Estimate the instantaneous growth rate at $t = 2$.
>
> Use the intervals on either side of $t = 2$:
> $$\frac{P(2)-P(1)}{2-1} = \frac{86-65}{1} = 21 \quad\text{and}\quad \frac{P(3)-P(2)}{3-2} = \frac{114-86}{1} = 28$$
>
> A good estimate is the average of these two:
> $$P'(2) \approx \frac{21 + 28}{2} = 24.5 \;\text{thousand/hr}$$
>
> This is the **symmetric difference quotient** approach: $\dfrac{P(3)-P(1)}{3-1} = \dfrac{114-65}{2} = 24.5$.

---

## Tips

> [!tip] Common Mistakes
> - **Forgetting the limit.** The difference quotient $\frac{f(a+h)-f(a)}{h}$ by itself is the average rate. You need $\lim_{h\to 0}$ to get the instantaneous rate.
> - **Sign errors.** A negative derivative means the function is decreasing — don't drop the sign.
> - **Units.** Always state units. If $f$ is in gallons and $x$ is in minutes, then $f'$ is in gallons per minute.

---

## See Also

- [[2.1 Derivatives and Rates of Change]]
- [[Tangent Lines and Secant Lines]]
