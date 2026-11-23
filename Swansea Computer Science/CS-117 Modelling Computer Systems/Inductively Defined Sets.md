#CS117 

*(this document is in reference to Modelling Computer Systems (book))*
#### The Three Clauses
An inductive definition has a set of three clauses:
- **The basis clause** (establishes that certain objects are in the set. These elements constitute the 'building blocks' for further elements in the set.)
- **The inductive clause** (defines the ways in which elements of a set can be used to produce further elements which are also in the set.)
- **The extremal clause** (asserts that no object is an element of a set unless its membership can be defined by the first two clauses.)

**Example**
$0\in\mathbb{N}$ – *the basis clause*
$(n+1)\in\mathbb{N}\text{ whenever }n\in\mathbb{N}$ – *the inductive clause*
Nothing else is in $\mathbb{N}$. That is, nothing is in $\mathbb{N}$ unless it can be constructed from the first two clauses. In other words, $\mathbb{N}$ is the smallest set satisfying the first two clauses. – *the extremal clause*

**Exercise 8.1 (Solution on page 440)**
> Explain, using this inductive definition of $\mathbb{N}$, why 4 $\in\mathbb{N}$,
   while 4.5 $\notin\mathbb{N}$.

$0\in\mathbb{N}$
$(n+1)\in\mathbb{N}\text{ whenever }n\in\mathbb{N}$
Nothing else is in $\mathbb{N}$ (extremal clause). 

We can show $4\in\mathbb{N}$ as follows:
- $0\in\mathbb{N}$ by the basis clause
- so 0+1 = 1 $\in\mathbb{N}$ by the inductive clause
- so 1+1 = 2 $\in\mathbb{N}$ by the inductive clause
- so 2+1 = 3 $\in\mathbb{N}$ by the inductive clause
- so 3+1 = 4 $\in\mathbb{N}$ by the inductive clause

However, $4.5\notin\mathbb{N}$. Every element produced by the basis and inductive clauses is a whole number, since 0 is one and adding 1 to a whole number gives another. 4.5 is not a whole number, so it can't be produced by these clauses. By the extremal clause, $4.5\notin\mathbb{N}$.

**Example (Abbreviating extremal clause)**
$1\in\text{ODD}$
if $n\in\text{ODD then }(n+2)\in\text{ODD}$

*Note: in this example, we incorporated the extremal clause into the preamble of the definition, by defining the set to be the smallest set satisfying the basis and the inductive clauses.*



