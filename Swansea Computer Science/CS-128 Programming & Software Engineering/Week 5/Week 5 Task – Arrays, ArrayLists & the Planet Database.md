---
tags: [CS128, lab-task]
lab: Lab Session 5
released: 2026-10-27
due: 2026-11-20
sign-off: Week 5 or Week 6 lab session only
submit: upload a .java file on Canvas
---
#CS128 

# Week 5 Task – Arrays, ArrayLists & the Planet Database
> [!info] Lab Session 5
> **Released:** Tue 27 Oct · **Canvas due date:** Fri 20 Nov, 18:00
> **Sign-off:** in the lab session of the week it's released or the week after — not later.
> **Submission:** upload a `.java` file on Canvas (not submitted yet).

## Aim
Create, fill, read and change **arrays** and **ArrayLists** (Chapter 8), with more loop and conditional practice.

## Stages
- [ ] **1 – Simple arrays:** the `Squares` program fills `squares[i] = i*i` — add a **second** loop to print it.
- [ ] **2 – Largest & smallest** in `{1, 7, -3, 14, 19, 0, 2, -8, 6, 11, 3}` — must work for any length (`numbers.length`).
- [ ] **3 – ArrayLists:** redo Stage 1 with an `ArrayList` (`import java.util.ArrayList;`).
	- *Challenge:* turn `{1,2,4,5,8}` into an ArrayList and insert the missing numbers (3, 6, 7) — for any array.
- [ ] **4 – Planets in arrays:** parallel arrays for the 8 planets (names, masses, radii, distances, life signs); print each in your **Lab 3** format.
- [ ] **5 – Look up a planet:** ask for a name, find its index, use that index in the other arrays.

> [!success] Assessed – Stage 6: Adding More Planets
> Switch Stage 5 to **ArrayLists**:
> ```java
> ArrayList<String> planetNamesList = new ArrayList<>(Arrays.asList(planetNames));
> ```
> Let the user **add planets** (name, mass, radius, distance, life signs). When they type **`done`** as the name, print every stored planet in the Lab 3 format — and don't then ask for the details of a planet called "done".

## Challenge
Read numbers until **-99** and insert each into an ArrayList in **sorted position**, then print it.

## More practice
Exercises in **section 8.10**.

## My notes

