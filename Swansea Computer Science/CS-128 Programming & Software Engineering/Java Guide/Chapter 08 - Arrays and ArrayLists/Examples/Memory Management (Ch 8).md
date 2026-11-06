---
tags: [CS128, java-guide]
chapter: "Chapter 08 - Arrays and ArrayLists"
source: https://canvas.swansea.ac.uk/courses/68227/pages/memory-management
---
#CS128 #java-guide

# Memory Management
> [!info] From the CS-128 notes on Canvas — [open the original page](https://canvas.swansea.ac.uk/courses/68227/pages/memory-management)

This module contains two programs - one in Java and one in a programming language called C. The point is to illustrate that a program in Java will crash if you try to access an element outside the set size of an array. However, the one in C will not necessarily do that. Java has run time error checking, which looks for this kind of thing. Many languages do not - and provided you do not go outside the block of memory the operating system gives your program you can do whatever you want (a bit like the film 'Escape from New York' - which is probably too old for you to have heard of...). T **his is not a good thing and leads to nasty and hard to find bugs.**

- [CrashMem.c](https://canvas.swansea.ac.uk/courses/68227/files/11334090)
- [CrashMem.java](https://canvas.swansea.ac.uk/courses/68227/files/11334150)

**Compare the results of running the C and Java programs**  - do the exercise in the comment in the C program. To run C programs, your easiest option is [online](https://canvas.swansea.ac.uk/courses/68227/pages/0-dot-4-running-java-without-installing-anything)), cut and paste the C code into the window, make sure C is selected and 'run program' is checked, then click 'submit'.

---
← [[Other Array Examples (Ch 8)]] · [[Java Guide - Start Here|Contents]] · [[ArrayList Operations - The Most Useful Ones (Ch 8)]] →
