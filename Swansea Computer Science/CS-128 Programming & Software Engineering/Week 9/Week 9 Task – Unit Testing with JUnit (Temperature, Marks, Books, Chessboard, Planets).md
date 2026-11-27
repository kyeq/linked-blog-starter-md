---
tags: [CS128, lab-task]
lab: Lab Session 8
released: 2026-11-26
due: 2026-12-11
sign-off: Week 9 or Week 10 lab session only
submit: upload a .java file on Canvas
---
#CS128 

# Week 9 Task – Unit Testing with JUnit (Temperature, Marks, Books, Chessboard, Planets)
> [!info] Lab Session 8
> **Released:** Thu 26 Nov · **Canvas due date:** Fri 11 Dec, 18:00 · [Canvas assignment](https://canvas.swansea.ac.uk/courses/68227/assignments/660205)
> **Sign-off:** in a lab session up to the final one before the deadline (Week 9 or Week 10) — not in extra support sessions. Can't finish? Contact the lecturer, **not** the extenuating circumstances team.
> **Submission:** upload a `.java` file on Canvas (not submitted yet).

## Aim
Write **automated JUnit tests** instead of eyeballing printed output (Chapter 14 – Unit Testing). The focus this week is *testing* classes, not writing them.
- Easiest setup: create a **Maven project in IntelliJ** (as in the notes) so JUnit is available.
- For each stage: write the class (if needed) → write a **separate** JUnit test class → test both working cases *and* cases that might fail → run tests often.
- A good test has one clear purpose, tests one thing, has a meaningful name, and uses **assertions** (not `println`).
- Shared test data can go in a method annotated `@BeforeEach`.

```java
@Test
public void testAddition() {
    Assertions.assertEquals(5, 2 + 3);
}
```

## Stages
- [ ] **1 – `TemperatureConverter`:** `celsiusToFahrenheit(double)` and `fahrenheitToCelsius(double)` — °F = (°C × 9/5) + 32, °C = (°F − 32) × 5/9.
	- `TemperatureConverterTest` checks: 0°C→32°F · 100°C→212°F · 32°F→0°C · 212°F→100°C.
	- Doubles need a **tolerance**: `Assertions.assertEquals(32.0, result, 0.001, "Conversion of Freezing Point from C to F Failed");`
	- *Challenge:* negative temps — −40°C → −40°F and −40°F → −40°C.
- [ ] **2 – `StudentMark`:** stores a name + integer mark 0–100; set/get the mark; `hasPassed()` is true when mark ≥ 40. e.g. `new StudentMark("Alice", 57)`.
	- `StudentMarkTest` checks: 0 stored · 100 stored · 39% fails · 40% passes · 41% passes · updating a mark changes it.
	- 40% is a **boundary value** — a classic spot for off-by-one mistakes.
	- *Challenge:* reject invalid marks (−1, −20, 101, 500) by throwing an exception or refusing to store them; test it.
	- *Challenge:* `getGrade()` → 70–100 Distinction · 60–69 Merit · 40–59 Pass · 0–39 Fail; test every boundary.
- [ ] **3 – `Book`:** title, author, number of pages; `isLongBook()` true when pages ≥ 500.
	- `BookTest` checks: 300 pages → not long · 500 → long · 1000 → long (think about exactly 500).
	- *Challenge:* stop negative page counts and test it.
- [ ] **4 – `Chessboard` tests** (from [[Week 7 Task – Classes & Objects (Fruit, Money, Chessboard, Planets)|Lab 7]]): piece stored & retrieved · two pieces on different squares · empty square returns `null` (or your value) · row < 1 rejected · row > 8 rejected · column before `a` rejected · column after `h` rejected.
	- *Challenge:* how many **categories** of input can you find? (valid rows, rows too small, rows too large, … what else?)

> [!success] Sign-off – Stage 6: Testing Planets (and Stars)
> Build a JUnit test suite for your **Planet** and **Star** classes from [[Week 7 Task – Classes & Objects (Fruit, Money, Chessboard, Planets)|Lab 7]] (improve them if needed). Cover:
> - **Object creation** – new objects store their data (planet name, mass, distance from star, star name… or your equivalents)
> - **Getters & setters** – values read and update correctly
> - **Calculations** – e.g. orbital period, habitability, distance conversions (only methods you actually have)
> - **Invalid data** – negative masses/distances, empty names; reject or handle them, but show you've thought about it
>
> You may need to tweak your code to have things to test (e.g. make `setDistance` reject negatives). The point is writing **sensible tests**, not necessarily passing them.
>
> **Minimum for sign-off:** at least **8** `@Test` methods · meaningful names · real assertions (printing values isn't enough).
> **Be ready to explain:** why you chose each test, and which ones check normal behaviour, boundary cases and invalid input.

## Related
- [[Week 7 Task – Classes & Objects (Fruit, Money, Chessboard, Planets)|Week 7 – Classes & Objects]] · [[Week 8 Coursework – Solar System Model|Solar System coursework]]
- Java Guide: Chapter 14 – Unit Testing

## My notes

