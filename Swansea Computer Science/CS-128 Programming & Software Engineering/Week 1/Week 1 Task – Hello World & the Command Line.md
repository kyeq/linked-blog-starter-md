---
tags: [CS128, lab-task]
lab: Lab Session 1
released: 2026-09-29
due: 2026-10-16
sign-off: Week 1 or Week 2 lab session only
---
#CS128 

# Week 1 Task – Hello World & the Command Line
> [!info] Lab Session 1
> **Released:** Tue 29 Sep · **Canvas due date:** Fri 16 Oct, 18:00
> **Sign-off:** in person, in the lab session of the week you get it or the week after — not later, and not in support sessions.

## Aim
Write and run very simple Java programs **using the command line tools** (not IntelliJ yet), and get used to reading and fixing compiler errors.

## Stages
- [ ] **1 – Before the lab:** read the lab prep guidance (Chapter 0) on running Java.
- [ ] **2 – Hello World:** type `Hello.java` in a plain text editor (BBEdit on Mac, not Word), then:
	- `javac Hello.java` → compiles, creates `Hello.class`
	- `java Hello` → runs it (no `.java` / `.class` on the end)
	- `ls` (Mac) / `dir` (Windows) to see the new `.class` file
- [ ] **3 – Compiler errors:** break it on purpose (remove a `;`, misspell `main`, extra `{`) and read the messages — line number, the error, and the `^` marker.
- [ ] **4 – Two lines:** print `Hello World!` and `Hello Friends!`.
- [ ] **5 – Expressions:** compare `println(4+3.5)` vs `println("4+3.5")`; print `17 * 1.75` (as a **new** program).
- [ ] **6 – Joining strings:** `"vanilla"+"icecream"` — why no space? Fix it; also try `print` then `println`.
- [ ] **7 – Strings + numbers:** the planets / Mars orbit examples (note what `687/365` gives you).
- [ ] **8 – Input:** get `HelloYou` (Scanner + `nextLine()`) compiling and working.
- [ ] **9 – Rename variables:** change `name` and `in` to other sensible names — Java doesn't care.
- [ ] **10 – Make it talk:** extend `HelloYou` into a short question-and-answer dialogue.

> [!success] Sign-off task
> Change the dialogue so each **answer appears on the same line as its question** (use `System.out.print`, and mind the space):
> `What is the name of your planet? Earth` ✅ — not `What is the name of your planet?Earth` ❌
> It must be **properly indented** and **commented**: one comment at the top saying what the program does, and one before each question/answer block (print question → read reply → print response).

## Optional extra
Miles ↔ km converter (1 mile = 1.609 km); then let the user choose which way to convert.

## Tips
- Case matters (`Println` ≠ `println`).
- Save every program separately with a sensible capitalised name — keep them all for the module.

## My notes

