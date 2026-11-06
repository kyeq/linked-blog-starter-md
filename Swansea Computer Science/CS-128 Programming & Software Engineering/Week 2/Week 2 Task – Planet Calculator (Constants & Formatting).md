---
tags: [CS128, lab-task]
lab: Lab Session 2
released: 2026-10-06
due: 2026-10-23
sign-off: Week 2 or Week 3 lab session only
---
#CS128 

# Week 2 Task – Planet Calculator (Constants & Formatting)
> [!info] Lab Session 2
> **Released:** Tue 6 Oct · **Canvas due date:** Fri 23 Oct, 18:00
> **Sign-off:** in the lab session of the week it's released or the week after — not later.

## Aim
Build a complete **straight-line program** (no ifs or loops yet) from scratch, in stages. It's the start of the **planet program** that carries on through the later labs and the coursework — so keep every version.

Background: read **Chapter 2** — this works just like the *Swimming Pool* example.

## Formulas (Earth units)
```java
period  = Math.sqrt(distance * distance * distance); // years, distance in AU
gravity = mass / (radius * radius);                  // Earths, mass & radius in Earths
```
For Earth, all of these come out as **1.0**.

## Stages
- [ ] **1 – Understand the problem:** turn the words into the two expressions above.
- [ ] **2 – Into Java:** hard-code test values; check against real planets you look up.
- [ ] **3 – Input/output:** read name (`String`), distance, mass, radius (`double` via `in.nextDouble()`), then print:
	`Planet X is Y AU from its star, orbits in Z years, has a mass of A Earths, a radius of B Earths, and a gravity of C Earths.`
- [ ] **4 – Format:** every number to **3 decimal places** (section 2.7, String formatting).

> [!success] Assessed – Stage 5: Constants
> Convert units and print:
> `Planet X is Y km from its star, orbits in Z years, has a mass of A Yg, a radius of B km, and a gravity of C Earths.`
> | Constant | Value |
> |---|---|
> | km in 1 AU | 149597871 |
> | Earth radius (km) | 6371 |
> | Earth mass (Yg) | 5972 |
> Must be **`static final` constants**, still rounded to 3 d.p.

## More practice
Exercises in **section 2.10**.

## My notes

