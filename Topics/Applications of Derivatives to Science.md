---
section: "2.7"
date_covered: "2026-02-05"
textbook: "Stewart Calculus 9e"
tags: [calculus, derivatives, applications]
---

# Applications of Derivatives to Science

> [!info] Deep Dive — Applications of Derivatives
> Supporting topic for [[2.7 Rates of Change in the Sciences]].

## The General Principle

> [!def] Derivative as Rate of Change
> If $y = f(x)$, then $f'(x)$ is the **instantaneous rate of change** of $y$ with respect to $x$. The units of $f'(x)$ are:
> $$\text{units of } f'(x) = \frac{\text{units of } y}{\text{units of } x}$$

This single idea applies across every scientific discipline.

## Physics: Motion

**Rectilinear motion** (motion along a line):

| Quantity | Symbol | Relationship |
|---|---|---|
| Position | $s(t)$ | Given |
| Velocity | $v(t)$ | $v(t) = s'(t)$ |
| Speed | $\|v(t)\|$ | Magnitude of velocity |
| Acceleration | $a(t)$ | $a(t) = v'(t) = s''(t)$ |

**Free fall** near Earth's surface (ignoring air resistance):
$$s(t) = -\frac{1}{2}gt^2 + v_0t + s_0$$
where $g \approx 9.8$ m/s² (or $32$ ft/s²), $v_0$ = initial velocity, $s_0$ = initial height.

> [!example] Projectile Example
> A ball is thrown upward from 80 ft with initial velocity 64 ft/s: $s(t) = -16t^2 + 64t + 80$.
>
> - $v(t) = -32t + 64$
> - $a(t) = -32$ ft/s² (constant)
> - Maximum height at $v(t) = 0$: $t = 2$ s, $s(2) = 144$ ft
> - Hits ground when $s(t) = 0$: $t = 5$ s, $v(5) = -96$ ft/s (downward)

**Speeding up vs slowing down:**
- Speeding up: $v(t)$ and $a(t)$ have the **same sign**
- Slowing down: $v(t)$ and $a(t)$ have **opposite signs**

## Physics: Other Quantities

| Quantity | Rate | Units |
|---|---|---|
| Charge $Q(t)$ | Current $I = \frac{dQ}{dt}$ | amperes (C/s) |
| Work $W(t)$ | Power $P = \frac{dW}{dt}$ | watts (J/s) |
| Mass $m(x)$ on a rod | Linear density $\rho = \frac{dm}{dx}$ | kg/m |

> [!example] Linear Density
> A rod has mass $m(x) = \sqrt{x}$ kg for $0 \le x \le 4$ (meters from left end).
>
> Linear density: $\rho(x) = \frac{1}{2\sqrt{x}}$ kg/m
>
> At $x = 1$: $\rho = 0.5$ kg/m. At $x = 4$: $\rho = 0.25$ kg/m. The rod is denser near the left end.

## Biology: Population Growth

If $P(t)$ is population at time $t$:
- **Growth rate:** $\frac{dP}{dt}$ (individuals per unit time)
- **Relative growth rate:** $\frac{1}{P}\frac{dP}{dt}$ (per capita rate)

> [!example] Bacterial Growth
> A population grows as $P(t) = 1000e^{0.5t}$ (cells, $t$ in hours).
>
> $\frac{dP}{dt} = 500e^{0.5t}$. At $t = 2$: growth rate $= 500e \approx 1359$ cells/hr.
>
> Relative growth rate $= \frac{500e^{0.5t}}{1000e^{0.5t}} = 0.5$ per hour (constant — exponential growth).

## Chemistry: Reaction Rates

If $[A](t)$ is the concentration of reactant $A$:
$$\text{Rate of reaction} = -\frac{d[A]}{dt}$$
(negative because concentration decreases). For products, the sign is positive.

> [!example] Decomposition
> $[A](t) = \frac{2}{t+1}$ mol/L. Rate $= -\frac{d[A]}{dt} = \frac{2}{(t+1)^2}$ mol/(L·s).
>
> At $t = 0$: rate $= 2$. At $t = 3$: rate $= 0.125$. Reaction slows over time.

## Economics: Marginal Analysis

If $C(x)$ = cost of producing $x$ units:
- **Marginal cost:** $C'(x) \approx$ cost of one more unit
- **Marginal revenue:** $R'(x)$
- **Marginal profit:** $P'(x) = R'(x) - C'(x)$

Profit is maximized when $R'(x) = C'(x)$ (marginal revenue = marginal cost).

> [!example] Marginal Cost
> $C(x) = 5000 + 10x + 0.05x^2$ dollars for $x$ units.
>
> $C'(x) = 10 + 0.1x$
>
> At $x = 100$: $C'(100) = 20$ $/unit. Producing the 101st unit costs approximately $20.
>
> Compare: exact cost of 101st unit $= C(101) - C(100) = \$20.05$.

## Unit Analysis

> [!tip] Always Check Units
> The derivative $\frac{dy}{dx}$ always has units $\frac{[\text{units of } y]}{[\text{units of } x]}$. If your answer has wrong units, something went wrong. This is the easiest way to catch errors.

## See Also
- [[2.7 Rates of Change in the Sciences]]
- [[Average vs Instantaneous Rate of Change]]
- [[Higher-Order Derivatives]]
