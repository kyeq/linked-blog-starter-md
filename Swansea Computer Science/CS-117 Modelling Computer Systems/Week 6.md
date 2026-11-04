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
The extremal clause (3) above says that an element of N ***must*** be either 0 (from the basis clause) or the successor of (ie, one plus) another element of n.

