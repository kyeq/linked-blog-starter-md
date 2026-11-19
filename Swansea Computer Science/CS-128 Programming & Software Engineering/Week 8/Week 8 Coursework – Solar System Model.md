---
tags: [CS128, coursework]
assignment: Solar System Model
released: 2026-11-18
due: 2026-12-04
closes: 2026-12-11
points: 100
submit: .java files on Canvas AND csautograder (must be identical)
canvas: https://canvas.swansea.ac.uk/courses/68227/assignments/677344
---
#CS128 

# Week 8 Coursework – Solar System Model
> [!success] Released – Wed 18 Nov, 08:00
> **Due Fri 4 Dec, 14:00** (the 11 Dec "available until" date is only for extenuating-circumstances extensions — don't confuse it with the deadline).
> Worth **100 points**. Marked with **csautograder** — see the [[Week 4 Task – Loops & Planet Relative Orbits|Week 4 autograder practice]]. [Open on Canvas](https://canvas.swansea.ac.uk/courses/68227/assignments/677344)

> [!danger] Development log is compulsory
> No dev log = **0 for the whole coursework**. Keep a dated/timed list (e.g. `19/11/2026 - 18.30 - created level 1, submitted to Autograder`) in the block comment at the top of `SolarSystem`. Write entries as you go and submit to Autograder regularly so the timestamps line up.

## Rules to remember
- [ ] Canvas and Autograder submissions must be **identical** (otherwise 0).
- [ ] **No `main` method** needed — tests supply it (`AutoTestLevel1/2/3.java`).
- [ ] Max **4 files**, one class per file; **no class names starting with `A`**.
- [ ] **No inner classes** (static or otherwise) — heavy penalty.
- [ ] Only Java *language* features from the notes (library methods like `Math` are fine). Tested on **Java 17**.
- [ ] Re-read **6.8** on `break` / `continue`.
- [ ] `toString()` must **return** a String, not print.
- [ ] Penalty for non-working code from a higher level — only include what passes.
- [ ] Autograder: **20 submissions/day**, resets 08:00. Autograder is always right.
- AI: OK for explanations, critique and generating *test* code — **not** for code you submit.

## Model
A solar system has a name, a luminosity (Sun = 1.0) and zero or more planets. Each planet has a name, mass (Earths), radius (Earth radii) and distance (AU). Orbital period, surface gravity and habitability are **computed**, not passed in.

## Levels
- [ ] **Level 1 – Basic** (10/25 run marks): class `SolarSystem` with constructor `SolarSystem(String name)`; methods so `AutoTestLevel1.java` compiles. `toString()` returns:
	- `Star A has planets:` then for each planet `X is BAU from its star, and orbits in C years` (each line ends in a newline); B and C to 3 d.p. (Chapter 2.7 formatting).
- [ ] **Level 2 – Extra methods** (20/25): planet equality (same name + distance — not `==`), furthest planet, closest planet (can't assume add order). Think about which class each belongs in.
- [ ] **Level 3 – Luminosity, mass, radius, habitability** (25/25): add `SolarSystem(String name, double luminosity)` without breaking L1/L2. Per-planet line:
	- `X has a mass of A Earths with a surface gravity of Gg, is BAU from its star, and orbits in C years: could be habitable? Z` (yes/no)

## Formulas
- Period: `Math.sqrt(d * d * d)` (or `Math.pow(d, 1.5)` — 1.5 is a magic number → constant)
- Gravity: `mass / (radius * radius)`
- Habitable if `0.75·√L ≤ distance ≤ 2.0·√L` **and** `0.6 ≤ mass ≤ 7.0` → all magic numbers should be `static final` constants.
- Round as the **last** step (store rounded, or format on output).

## Rubric (100)
| Category | Max | Top band |
|---|---|---|
| Compiles | 5 | No warnings on Autograder (check `javac` on command line) |
| Runs correctly | 25 | Passes Level 3 |
| Style (checkstyle) | 10 | 0 errors on one of the two checkstyle files |
| OO principles | 20 | 15 = excellent; 20 = "surprise me" |
| Design & detail | 20 | 15 = no design problems; 20 = "surprise me" |
| Development log | 20 | Dated, aligns with Autograder history |

## Resources (download from Canvas)
- `CW2Pack.zip` – AutoTestLevel1/2/3.java (run: `javac *.java` then `java AutoTestLevelX`)
- `EdiblePlantTester.zip` and `Triangle.zip` – practice for how Autograder works (+ walkthrough videos)
- Similar examples: [[The Bank Example Code (Ch 12)|Bank example]] · [[The Lidl Examples (Ch 11)|Lidl examples]] (esp. Lidl2) · Book/Library lecture example — the "list of things" pattern.
- Build on: [[Week 7 Task – Classes & Objects (Fruit, Money, Chessboard, Planets)|Week 7 – Planets & Stars classes]] · [[Week 5 Task – Arrays, ArrayLists & the Planet Database|Week 5 – Planet Database]]

## Plan
- [ ] Download CW2Pack.zip and read the three test files
- [ ] Level 1 → submit to Autograder → back up
- [ ] Level 2 → submit → back up
- [ ] Level 3 → submit → back up
- [ ] Checkstyle clean · no compiler warnings · comments
- [ ] Same files to Canvas + Autograder before **Fri 4 Dec, 14:00**

## Development log (draft – copy into SolarSystem)

## My notes

