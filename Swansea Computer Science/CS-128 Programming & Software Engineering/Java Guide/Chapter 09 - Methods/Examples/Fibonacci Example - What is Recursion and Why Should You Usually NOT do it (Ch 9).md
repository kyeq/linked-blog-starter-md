---
tags: [CS128, java-guide]
chapter: "Chapter 09 - Methods"
source: https://canvas.swansea.ac.uk/courses/68227/pages/fibonacci-example-what-is-recursion-and-why-should-you-usually-not-do-it
---
#CS128 #java-guide

# Fibonacci Example - What is Recursion and Why Should You Usually NOT do it?
> [!info] From the CS-128 notes on Canvas — [open the original page](https://canvas.swansea.ac.uk/courses/68227/pages/fibonacci-example-what-is-recursion-and-why-should-you-usually-not-do-it)

Recursion is where a method calls itself - and it's a favourite technique of programmers trying to be clever. Some people really like it. Some people have been told it's a good idea.  **To be clear...**

- **It is HARDLY EVER a good idea.**
- **In this module it is NEVER a good idea.**

If you want to see one reason why not, download and run the program below - it computes Fibonacci numbers using a loop and recursion and compares them. As well as the very obvious problem when you do that, the recursive version uses a 'block' of extra memory for every extra Fibonacci number it computes: the other one doesn't. We aren't really short of memory - but this is a pointless waste of it.

[Fibonacci.java](https://canvas.swansea.ac.uk/courses/68227/files/11334177)

---
← [[Assorted Examples (Ch 9)]] · [[Java Guide - Start Here|Contents]] · [[More Method Examples (Ch 9)]] →
