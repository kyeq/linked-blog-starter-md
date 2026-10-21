#CS117 

A function f: A → B maps elements from set A to elements in another set B.

We'll delve into more detail about more general relationships between elements than simple mappings.
##### For example...
- “parenthood” amongst the set of people 
- (“x is parent of y”)

- “divisibility” amongst the set of integers
- (“x divides evenly into y”)

- relationships between different sets:
- “enrolment” relating the sets of students and courses
- (“student s takes course c”)

- relationships between more than two sets:
- “grade” relating students, courses and grades
- (“students s got a grade of g in course c”)

#### Example
Consider the predicate:
Mark(x, y, z) = "student x, in course y, scored grade z"

Let S, C and G be the sets of students, courses, and grades, respectively. The
truth set of Mark is a subset Grades of the Cartesian product S→C→G given as

![[Pasted image 20261021113711.png|271]]

An n-***ary relation*** R is a subset of n-tuples.

![[Pasted image 20261021113814.png|321]]

E.g., Grades is a ternary (that is, 3-ary) relation over S→C→G.