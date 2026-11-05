#CS117 

# Inductively-Defined Sets

#### Inductive definition of a set
*An inductive definition of a set has three components (clauses):*

- The ***basis clause*** establishes that certain objects are in the set.
- These elements constitute the "building blocks" for constructing further elements in the set.
	- For example: *0 is a basic natural number*

- The ***inductive clause*** defines the ways in which elements of a set can be used to produce further elements which are also in the set.
	- For example: *if n is a natural number, then so is n+1*

- The ***extremal clause*** asserts that no object is an element of the set being defined unless it can be established from the first two clauses.

#### N: An Example Inductively-Defined Set
The set of natural numbers N can be defined as follows:
![[Pasted image 20261104111334.png|502]]

The basis clause (1) says that 0 (is an element of) N;
The inductive clause (2) says that from any natural number n we can produce another natural number n+1

In this way we can conclude that all values 0, 1, 2, 3, ... are in N:
![[Pasted image 20261104111502.png|397]]

#### The Extremal Clause

![[Pasted image 20261104112634.png|529]]

#### Inductively-Defined Subsets of N
**Example:** We can inductively define the set

![[Pasted image 20261104120907.png|526]]

![[Pasted image 20261104121122.png]]

The inductive rules say:
- 2 is an element of X
- if number is an element of X, then add 3, and add 5
So with a set of {0, 1, 2, 3, ... 20}

1. Start with 2
{2}
2. Add 3 to it.
{2, 5}
3. Add 5 to it.
{2, 5, 7}
4. Now we can begin on 5.
5. Add 3 to it.
{2, 5, 7, 8}
6. Add 5 to it.
{2, 5, 7, 10}
7. Now we can begin on 7.
8. Add 3 to it.
{2, 5, 7, 10} - Already in the set.
9. Add 5 to it.
{2, 5, 7, 10, 12}
... etc

In the end, you'll compute:
{2, 5, 7, 10, 12, 13, 14, 15, 16, 17, 18, 19, 20}

$$
X = \{n \in \mathbb{N} \mid \dots \}
$$

#### Inductively-Defined Sets of NxN
Example:
$$
W = \{(x, y) \in \mathbb{N} : x \geq y\}
$$
There are different ways to define W inductively.
For example, it could be defined to be the smallest set satisfying any one of the three pairs of clauses.

![[Pasted image 20261104124603.png|441]]

#### Example: Finite Powersets
Given a finite set S,  the powerset P(S) of S is the smallest set satisfying:
![[Pasted image 20261104124638.png|307]]

For example, if S = {1,2} then by the basis clause, 
![[Pasted image 20261104124702.png|85]]
and thus by one application of the inductive clause we get that the following sets are in P(S):
![[Pasted image 20261104124740.png|281]]

![[Pasted image 20261104124751.png|461]]

#### Alphabets and Words
Given a set A of letters (ie, an alphabet), A* represents the set of words (ie, arbitrary sequences of letters) that can be formed from letters taken from A, including the empty word ω consisting of no letters.

For example, if A = {a, b} then the following are all words in A*:
ω, a, b, aa, ab, ba, bb
aaa, aab, aba, abb, baa, bab, bba, bbb
:
..., bbabbaba, ...
:

The set A* of words over an alphabet A is defined inductively as the smallest set satisfying the following: 
![[Pasted image 20261104124952.png|311]]

