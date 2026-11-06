---
tags: [CS128, lab-task]
lab: Lab Session 3
released: 2026-10-13
due: 2026-11-06
sign-off: Week 3 or Week 4 lab session only
---
#CS128 

# Week 3 Task – Conditionals & Planet Habitability
> [!info] Lab Session 3
> **Released:** Tue 13 Oct · **Canvas due date:** Fri 6 Nov, 18:00
> **Sign-off:** in the lab session of the week it's released or the week after — not later.

## Aim
Start writing conditional code: `if`, `if-else` and `switch` (Chapter 4). Solve the problem in front of you before moving to the next (advice in 4.4).

## Stages
- [ ] **0 – Switch to IntelliJ** if you haven't already.
- [ ] **1 – Morning, afternoon or night:** read an hour 1–24 and say which it is (you decide when night starts). Test the `if` with fixed values first, then add the Scanner.
- [ ] **2 – Richter (or Beaufort) scale:** read a `double` and print the description for ~4 levels. Mostly an `if … else if … else` chain.
	- Copy-pasted curly quotes cause `illegal character “` errors — retype them as plain `"`.
- [ ] **4 – Switch:** birds → raptor / wader / seabird / passerine (e.g. eagle → raptor, crow → passerine).

> [!success] Assessed – Stage 5: Planet Habitability
> Extend your **Lab 2** program. Also read:
> - star **luminosity** (`double`, Sun = 1.0)
> - **life-sign gases detected** (`boolean` via `in.nextBoolean()`)
>
> ```java
> luminosityFactor = Math.sqrt(luminosity);
> // habitable if BOTH:
> //   0.75 * luminosityFactor <= distance <= 2.0 * luminosityFactor
> //   0.6 <= mass <= 7.0
> // could have life = habitable AND life signs detected
> ```
> Output:
> `Planet X is Y km from its star, orbits in Z years, has a mass of A MT, a radius of B km, and a gravity of C Earths. Could be habitable? D; Could have life? E.`
> D and E are the booleans.
>
> ⚠️ The sheet says mass in **MT** here, but Lab 2 used **Yg** — worth checking which one is wanted.

### Test data
| Planet | Distance | Mass | Radius | Luminosity | Life signs |
|---|---|---|---|---|---|
| Earth | 1 | 1 | 1 | 1 | true |
| Pluto | 40 | 0.002 | 0.19 | 1 | false |
| K2-18 | 0.159 | 1.35 | 2.6 | 0.023 | true |

## Challenge
Read the section on **coverage** and design test data that reaches **C1 coverage**.

## More practice
Exercises in **section 4.8**.

## My notes

