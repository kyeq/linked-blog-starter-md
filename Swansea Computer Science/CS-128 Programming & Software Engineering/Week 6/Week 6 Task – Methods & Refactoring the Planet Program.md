---
tags: [CS128, lab-task]
lab: Lab Session 6
released: 2026-11-03
due: 2026-11-27
sign-off: Week 6 or Week 7 lab session only
submit: upload a .java file on Canvas
---
#CS128 

# Week 6 Task – Methods & Refactoring the Planet Program
> [!info] Lab Session 6
> **Released:** Tue 3 Nov · **Canvas due date:** Fri 27 Nov, 18:00
> **Sign-off:** in the lab session of the week it's released or the week after — not later.
> **Submission:** upload a `.java` file on Canvas (not submitted yet).

## Aim
Write **methods**, and break code into methods to make it clearer and cut repetition (Chapter 9). Every method needs a `main` that tests it.

## Stages
- [ ] **1 – `cube`:** `public static int cube(int num)`. Test with 0, a positive and a negative number.
	- *Mini challenge:* make it handle values bigger than an `int` can hold (max 2 147 483 647).
- [ ] **2 – `isCube(a, b)`:** return `true` if `a` is the cube of `b` — reuse `cube`.
- [ ] **3 – Box method:** takes length and height and prints a rectangle of `*`.
	- The sheet says reuse your boxes from *Lab 5 Stage 4* — that's actually **Lab 4, Stage 4**.
- [ ] **4 – Do one thing:** split Stage 3 into two methods plus `main`:
	1. read one integer **safely**, reject non-integers, require > 0; parameter = the prompt string (optional `maxVal`)
	2. print a box from height and width
	`main` calls the first twice (different prompts) and the second once.
- [ ] **5 – Comment properly:** a `/* … */` block above every method saying **what** it does (parameters, what's returned or printed), not **how**.

> [!success] Sign-off – Stage 6: Planet Methods
> Refactor your **Lab 5** program into methods:
> - methods for **orbital period**, **gravity**, **could be habitable**, **could have life** (formulas from Labs 2 & 3)
> - comment each one, and say when it **wouldn't work** for some parameter values (at least one method really needs this)
> - **safe input methods** for `double` and `boolean` (Chapter 7, like Lab 4), using parameters so you can reuse them

## Challenges
- **Recursive `gcd`:** `gcd(x, 0) = x`, otherwise `gcd(x, y) = gcd(y, x % y)`.
- **Non-recursive `gcd`** (Chapter 6 pseudocode) — compare the speed. It should be close, unlike Fibonacci, because `gcd` makes only one recursive call.

## My notes

