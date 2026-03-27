---
section: "2.8"
date_covered: "2026-02-09"
textbook: "Stewart Calculus 9e"
tags: [calculus, derivatives, related-rates]
---

# Related Rates Problem-Solving Strategy

> [!info] Deep Dive — Related Rates Strategy
> Supporting topic for [[2.8 Related Rates]].

## Step-by-Step Algorithm

> [!def] The Related Rates Procedure
> 1. **Read** the problem carefully. Identify all given quantities and the unknown rate.
> 2. **Draw a diagram.** Label all variables (not numbers yet — variables that change with time).
> 3. **Write given rates** using derivative notation: $\frac{dr}{dt} = 5$, etc.
> 4. **Identify** what you need to find: $\frac{d?}{dt} = ?$
> 5. **Find an equation** relating the variables (geometry, trig, Pythagorean theorem, etc.)
> 6. **Eliminate extra variables** if needed (use constraints like similar triangles)
> 7. **Differentiate** both sides with respect to $t$ (implicit differentiation)
> 8. **Substitute** all known values at the specific instant
> 9. **Solve** for the unknown rate
> 10. **Check:** Do the sign and magnitude make sense?

## Common Geometric Formulas

### Circles and Spheres
| Shape | Formula |
|---|---|
| Circle area | $A = \pi r^2$ |
| Circle circumference | $C = 2\pi r$ |
| Sphere volume | $V = \frac{4}{3}\pi r^3$ |
| Sphere surface area | $SA = 4\pi r^2$ |

### Cones and Cylinders
| Shape | Formula |
|---|---|
| Cone volume | $V = \frac{1}{3}\pi r^2 h$ |
| Cylinder volume | $V = \pi r^2 h$ |

### Triangles and Rectangles
| Shape | Formula |
|---|---|
| Pythagorean theorem | $a^2 + b^2 = c^2$ |
| Triangle area | $A = \frac{1}{2}bh$ |
| Rectangle area | $A = lw$ |
| Similar triangles | $\frac{a_1}{b_1} = \frac{a_2}{b_2}$ |

### Trigonometry
$$\tan\theta = \frac{\text{opposite}}{\text{adjacent}}, \quad \sin\theta = \frac{\text{opposite}}{\text{hypotenuse}}$$

## The Similar Triangles Technique

Many problems involve a cone or triangle where both $r$ and $h$ change. The volume formula $V = \frac{1}{3}\pi r^2 h$ has **two** changing variables. Use similar triangles to eliminate one.

> [!example] Cone Example
> A conical tank has height 10 ft and top radius 4 ft. Water fills to depth $h$ with water-surface radius $r$.
>
> By similar triangles: $\frac{r}{h} = \frac{4}{10} = \frac{2}{5}$, so $r = \frac{2h}{5}$.
>
> Substitute into volume: $V = \frac{1}{3}\pi\left(\frac{2h}{5}\right)^2 h = \frac{4\pi h^3}{75}$
>
> Now differentiate — only one variable ($h$) remains.

## Critical Rules

> [!tip] The Golden Rules of Related Rates
> 1. **Never plug in numbers before differentiating.** Numbers are constants — their derivatives are zero. You'll lose the rate you need.
> 2. **Draw a picture every time.** Even for "simple" problems.
> 3. **Constants stay constant.** If a dimension doesn't change with time, it stays as a number in the equation (e.g., the fixed radius of a cone).
> 4. **Variables change.** If a quantity changes with time, it must be a variable when you differentiate.

## Practice Problems

> [!example] Practice 1 — Expanding Oil Slick
> Oil spills in a circular pattern. Area increases at $6$ m²/min. How fast is the radius increasing when $r = 10$ m?
>
> **Solution.** $A = \pi r^2$. Differentiate: $\frac{dA}{dt} = 2\pi r\frac{dr}{dt}$
>
> $6 = 2\pi(10)\frac{dr}{dt}$, so $\frac{dr}{dt} = \frac{6}{20\pi} = \frac{3}{10\pi} \approx 0.095$ m/min.

> [!example] Practice 2 — Sliding Ladder (Pythagorean)
> A 13-ft ladder leans against a wall. Bottom slides away at 2 ft/s. How fast is the top sliding down when the bottom is 5 ft from the wall?
>
> **Solution.** Let $x$ = distance from wall to bottom, $y$ = height of top.
>
> $x^2 + y^2 = 169$. When $x = 5$: $y = 12$.
>
> Differentiate: $2x\frac{dx}{dt} + 2y\frac{dy}{dt} = 0$
>
> $2(5)(2) + 2(12)\frac{dy}{dt} = 0$, so $\frac{dy}{dt} = -\frac{20}{24} = -\frac{5}{6}$ ft/s.
>
> Top slides down at $\frac{5}{6}$ ft/s.

> [!example] Practice 3 — Trig Approach
> A camera 200 m from a launch pad tracks a rocket rising at 300 m/s. How fast must the camera angle change when the rocket is 400 m high?
>
> **Solution.** Let $h$ = rocket height, $\theta$ = camera angle.
>
> $\tan\theta = \frac{h}{200}$. Differentiate: $\sec^2\theta \cdot \frac{d\theta}{dt} = \frac{1}{200}\frac{dh}{dt}$
>
> When $h = 400$: $\tan\theta = 2$, so $\sec^2\theta = 1 + \tan^2\theta = 5$.
>
> $5 \cdot \frac{d\theta}{dt} = \frac{300}{200} = 1.5$, so $\frac{d\theta}{dt} = 0.3$ rad/s.

## See Also
- [[2.8 Related Rates]]
- [[Implicit Differentiation]]
- [[Chain Rule]]
