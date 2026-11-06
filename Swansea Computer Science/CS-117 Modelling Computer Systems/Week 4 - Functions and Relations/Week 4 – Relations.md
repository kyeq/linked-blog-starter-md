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

#### Example #2

**The IMDb Database – James Bond Films**

![[Pasted image 20261021114013.png]]

A small part of the Internet Movie Database (IMDb) representing James Bond
Films is presented on the previous slide.

The database can be viewed as a 5-ary relation:

![[Pasted image 20261021114301.png|501]]

where:
	Titles = set of film titles in the database
	Names = set of names of people in the database

An element in the database associates a title with a year of release, the actor
playing James Bond, its screenwriters, and its director.

For example...
> r10 = (The Man With the Golden Gun, 1974, Roger Moore,
> {Richard Maibaum, Tom Mankiewicz}, Guy Hamilton)

![[Pasted image 20261021114708.png]] 
![[Pasted image 20261021114733.png]]

#### Visualising Relations
Binary relations from a set A to a set B can be visualised as above by drawing
arrows from elements of the set A to related elements in the set B.

For homogeneous relations on a set A, we need only draw the set A once and
add the relation arrows.

![[Pasted image 20261021114826.png|457]]

![[Pasted image 20261021115049.png]]

![[Pasted image 20261021115058.png]]

![[Pasted image 20261021115106.png]]

![[Pasted image 20261021115115.png]]

![[Pasted image 20261021115124.png]]