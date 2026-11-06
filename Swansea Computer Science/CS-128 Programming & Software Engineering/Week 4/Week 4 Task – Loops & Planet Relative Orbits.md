---
tags: [CS128, lab-task]
lab: Lab Session 4
released: 2026-10-20
due: 2026-11-13
sign-off: Week 4 or Week 5 lab session only
status: submitted to Canvas 22 Oct (LabTask4.java)
---
#CS128 

# Week 4 Task – Loops & Planet Relative Orbits
> [!info] Lab Session 4
> **Released:** Tue 20 Oct · **Canvas due date:** Fri 13 Nov, 18:00
> **Sign-off:** in the lab session of the week it's released or the week after — not later.
> **Status:** `LabTask4.java` uploaded on Canvas, 22 Oct ✅

## Aim
Write and use loops, choose the **right kind** of loop (`for` vs `while`), and practise designing programs with loops (Chapter 6).

## Stages
- [ ] **1 – while → for:** rewrite the count-to-100 `while` loop as a `for` loop (see the Chapter 6 *Investment* examples).
- [ ] **2 – for → while:** the "enter numbers until 50" loop should be a `while`.
	- *Mini challenge:* change `int count = 0;` to `int count;` — why the compiler error?
- [ ] **3 – Sum of odd numbers** 1 + 3 + … + 19. Two ways: `if (n % 2 == 1)` inside the loop, or step by 2 (shorter).
- [ ] **4 – Nested loops:** read length and height and print a filled rectangle of `*`.
- [ ] **5 – Empty box:** same but hollow (4 loops done simply). *Challenge:* triangles.
- [ ] **6 – Planet relative orbits** (hard-code the two periods first):
	```java
	thetaInner = (thetaInner + 360.0 / periodInner) % 360;
	thetaOuter = (thetaOuter + 360.0 / periodOuter) % 360;
	delta = Math.abs(thetaInner - thetaOuter);
	```
	- `delta <= 90` → outer planet in **day** sky, inner is a **crescent**
	- `delta > 90` → outer planet in **night** sky, inner is **gibbous**
	- Loop once per day for one **outer** year; only print every **30 days**. Recalculate at the start of each loop, then print.
	- Check: outer = 180, inner = 50 → first line `Delta 5.20: day 0: inner angle: 7.20 outer angle 2.00: outer planet - day sky; inner planet - crescent`

> [!success] Assessed – Stage 7
> Extend Stage 6 to:
> - ask for **planet 1** and **planet 2** (not "inner/outer") and work out which is inner — the longer period is the outer
> - read input **safely** (Chapter 7) so typing `lemon` doesn't crash it, and only accept **positive** periods
> - keep variable **scope** as small as possible (Chapter 5)
> - follow good layout and commenting practice

> [!warning] Autograder practice (important for the coursework)
> Submit to **csautograder**:
> - file must be called **`LabTask4.java`**
> - prompts must be exactly `Enter the period of planet 1: ` and `Enter the period of planet 2: ` — **with a space at the end**
> - output has to match exactly (spaces, case) — "no mercy"

## More practice
Exercises in **section 6.9**.

## My notes

