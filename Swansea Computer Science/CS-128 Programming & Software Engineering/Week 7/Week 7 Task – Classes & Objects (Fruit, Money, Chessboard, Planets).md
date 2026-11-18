---
tags: [CS128, lab-task]
lab: Lab Session 7
released: 2026-11-10
due: 2026-12-04
sign-off: Week 7 or Week 8 lab session only
submit: upload a .java file on Canvas
---
#CS128 

# Week 7 Task – Classes & Objects (Fruit, Money, Chessboard, Planets)
> [!info] Lab Session 7
> **Released:** Tue 10 Nov · **Canvas due date:** Fri 4 Dec, 18:00
> **Sign-off:** in the lab session of the week it's released or the week after — not later (not in extra support sessions).
> **Submission:** upload a `.java` file on Canvas (not submitted yet).

## Aim
The basics of **object-oriented programming** — write classes and create objects from them (Chapters 10 & 11). Most are simple "storage" classes: data plus get/set methods.
- Put your **test code in a separate class/file** so it can't accidentally rely on `private` members.

## Stages
- [ ] **1 – `Fruit`:** properties `name` and `colour`. Decide on constructor/methods — should a fruit be changeable after creation? (If not: set via constructor only, no setters.) Add a `main` that creates several fruits and prints results.
- [ ] **2 – `Money`:** currency name (`String`) + amount as `long` in the smallest unit (pence/cents). Getters, setters and a `toString` — e.g. `1000`, `Euro` → `"10.00 Euros"`.
	- Why not `double`? Floating-point maths isn't exact, so money gets "gained" or "lost". Use whole numbers or `BigDecimal`.
	- *Challenges:* use `BigDecimal` · print the symbol (€, £, $) in a general way · support non-1/100 minor units (e.g. Mauritania, Madagascar = 1/5) · use an **enum** of ISO 4217 codes (optional chapter *Enumerated Types*).
- [ ] **3 – `Chessboard`:** 8×8 board storing any `String` per square (no chess rules!). `setPiece(String, char col, int row)` and `getPiece(char col, int row)`; validate rows 1–8 and columns `a`–`h`.
	- Hint: 2D `String` array; row index = `row - 1`; column via `switch` or `(int) c - (int) 'a'`.
	- Test it from a **separate class in a separate file**.
	- *Challenges:* a `Chesspiece` class (name + colour stored separately) used by the board · a `ChessGame` class recording players' moves (unknown number → `ArrayList`) and working out which piece moved.

> [!success] Sign-off – Stage 3: Planets (and Stars)
> Refactor your **Lab 5** program (Lab 6 methods help) to use **classes**:
> - a class is a *thing*, a method is an *action*
> - there are **two** kinds of thing — the planet is obvious; one bit of data doesn't belong to it (hint: it's in **Lab 3** → the star)
> - write classes with sensible methods (read info, update data) plus test code showing it basically works (no C1 testing needed)
> - TAs have some discretion on interpretation, but it must follow the notes' guidance — and you'll need it for the final lab / [[Week 8 Coursework – Solar System Model|Solar System coursework]].

## Related
- [[Week 6 Task – Methods & Refactoring the Planet Program|Week 6 – Methods]] · [[Week 5 Task – Arrays, ArrayLists & the Planet Database|Week 5 – Planet Database]]
- Java Guide: Chapter 10 – Classes Part 1 · Chapter 11 – Classes Part 2

## My notes

