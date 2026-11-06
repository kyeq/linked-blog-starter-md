---
tags: [CS128, java-guide]
chapter: "Chapter 11 - Classes Part 2"
source: https://canvas.swansea.ac.uk/courses/68227/pages/point-line-line-sequence
---
#CS128 #java-guide

# Point, Line, Line Sequence
> [!info] From the CS-128 notes on Canvas — [open the original page](https://canvas.swansea.ac.uk/courses/68227/pages/point-line-line-sequence)

This is a new example showing a hierarchy of classes:

- A Point is a point in 2D space - it has an X and and Y coordinate
- A Line is a line in 2D space - it has a starting Point and an end Point (using the Point class)
- A LineSequence is a 'list' of lines in 2D space, consisting of a number of Line object 'segments;

The example show how you can use a series of classes to abstract away from details, and how 'lower level' classes can simplify the code of 'higher level' ones (for example, look at how we check if Points are equal and then how we check if a LineSequence forms a path or a polygon; and how we handle printing out a Line and LineSequence using toString - each toString method relies on the one in the "class below"

Please Note

- I have not tested this:-) - and there isn't even a main method anywhere. An  **exercise**  is to add one and see if it all works correctly (and fix it if it doesn't). It does all compile though.
- I have embedded Javadoc comments in the code - these are in the (optional) Chapter 14. You can if you want ignore them at this stage - but if you are comfortable with all the material so far, then please read that chapter and see how you can generate documentation for your code in a (fairly) painless way.

- [Point.java](https://canvas.swansea.ac.uk/courses/68227/files/11334081)
- [Line.java](https://canvas.swansea.ac.uk/courses/68227/files/11333996)
- [LineSequence.java](https://canvas.swansea.ac.uk/courses/68227/files/11334057)

---
← [[Card Classes 7-10 (Ch 11)]] · [[Java Guide - Start Here|Contents]] · [[Cash Register, Menu (Ch 11)]] →
