#CS117 

**What's in this note:**
- Reflexive / irreflexive
- Symmetric / antisymmetric
- Transitive
- Orders (partial and total)
- Equivalence relations
- Partitions and equivalence classes

#### What's a relation?
A function was arrows where each input has exactly one arrow.
A relationship is just arrows with no rules. Something can have no arrows, one arrow, or lots of arrows.

We write $xRy$ to mean "x is related to y", or simply "there's an arrow from x to y"

### Part 1: Reflexive

**Reflexive** means everything has an arrow to itself. A loop on every element.
*Example:* the relation "is the same height as". Everyone is the same height as themselves, so it's reflexive!

**Irreflexive** is the opposite: nothing has an arrow to itself. No loops anywhere.
*Example:* "is taller than". Nobody is taller than *themselves*, so it's irreflexive!

> A relation can be neither, if *some* things have loops and others don't.

$\text{Take the set }A=\{1,2,3\}$

$A)\:1\to1\quad2\to2\quad3\to3\quad1\to2$
$B)\:1\to2\quad2\to3$
$C)\:1\to1\quad1\to3$

- A: 1, 2 and 3 all have loops – so it's **reflexive**.
- B: there's no loops at all, so it's **irreflexive**.
- 1 has a loop but 2 and 3 don't, so it's **neither**.

### Part 2: Symmetric
Symmetric means every arrow has a return arrow. if $x\to y$, then
$y\to x$ must be there too.

*Example:* "is a sibling of". If Sam is Jo's sibling, then Jo is sam's sibling, so the arrows always come in pairs. It's symmetric!

Antisymmetric means there are no return arrows between different things. If $x\to y$, then $y\to x$ is not allowed, unless x and y are the same thing. Loops are fine.

*Example:* "is less than or equal to" $(\leq)$. If $2\leq 5$, then $5\leq 2$ is false, so there's no return arrow. it's antisymmetric!

$\text{Take the set } A=\{1, 2, 3\}$

$A)\:1\to2\quad2\to1\quad3\to3$
$B)\:1\to2\quad2\to3$
$C)\:1\to2\quad2\to1\quad2\to3$

- A: $1\to2$ has its return $2\to1$, and $3\to3$ is a loop, which counts as its own return. That makes it **symmetric**.
- B: $1\to2$ has no $2\to1$, and $2\to3$ has no $3\to2$, so there are no return arrows anywhere. It's **antisymmetric**.
- C: $1\to2$ and $2\to1$ are a pair, but $2\to3$ has no $3\to2$. One arrow is missing its return, so it's not symmetric. And because 1 and 2 point at each other, it's not antisymmetric either. It's **neither**.

### Part 3: Transitive
Transitive means that if you can get somewhere in two steps, there must be a direct shortcut. If $x\to y$ and $y\to z$, then $x\to z$ must be there too.

*Example:* "is taller than". If Sam is taller than Jo, and Jo is taller than Ali, then Sam is taller than Ali. The shortcut always exists, so it's transitive.

> How to check it: Look for every **two-step path** ($x\to y\to z$) and make sure the shortcut ($x\to z$) is there. If even one shortcut is missing, it's not transitive.

$\text{Take the set } A=\{1, 2, 3\}$

$A)\:1\to2\quad2\to3\quad1\to3$
$B)\:1\to2\quad2\to3$
$C)\:1\to2\quad2\to1\quad1\to1\quad2\to2$

- A: A is transitive, there's only one two-step path ($1\to2\to3$) and it's shortcut ($1\to3$) is there (the only shortcut needed), so it's **transitive**.
- B: B isn't transitive, it's the same two-step path as A ($1\to2\to3$), but the shortcut ($1\to3$) is missing, so it's **not transitive**.
- C: Because 1 and 2 point at each other, *and* each has a loop, there are lots of two-step paths. *Every shortcut is there*, so it's **transitive.**

#### Exercise 1 (check all 5 properties)

Take the set:
$A=\{cat, dog, bird, rat\}$
The relation: $x$ is related to $y$ if they share a letter.

***Step 1: find the arrows***
Take each pair of words and check whether they have a letter in common. Don't forget each word compared with itself.

*The words that share letter(s):*
$cat\to rat$
$rat\to cat$
$dog\to bird$
$bird\to dog$
$bird\to rat$
$rat\to bird$

*The full list (all words that share letters as a list):*
$cat\to cat\quad dog\to dog\quad bird\to bird\quad rat\to rat$
$cat\to rat\quad rat\to cat$
$dog\to bird\quad bird\to dog$
$bird\to rat\quad rat\to bird$

- It's reflexive – every word has a loop.
	- Every word shares a letter with itself.
- It's symmetric – every word has a return arrow.
	- If cat shares a letter with rat, then rat shares that same letter wth cat. The letter doesn't care which word you start from.
- No, it's not transitive
	- dog has d, o, g and rat has r, a, t so they share nothing.

A quick way to spot these: read the rule out loud.
- **Reflexive:** does "x shares a letter with x" always make sense? *Yes*
- **Symmetric:** does swapping x and y change the meaning of "x shares a letter with y"? *No*

#### Exercise 2 (check all 5 properties)
Take an ancestor – for example, a dad, a grandad

An ancestor:
- Reflexive – **no**
	- Reflexive needs everyone to be their own ancestor.
	- An ancestor is someone born before you, and nobody is born before themselves, so nobody has a loop, and it's not reflexive.
- Irreflexive – **yes**
	- Irreflexive needs nobody to be their own ancestor. Since no one is born before themselves, nobody has a loop.
- Symmetric – **no**
	- Symmetric needs every arrow to have a return arrow. if x is y's ancestor, x was born before y. For the return arrow, y would have to be born before x as well, which is impossible.
- Antisymmetric – **yes**
	- Antisymmetric needs there to be no return arrows between different people. That's the same reason again. Two different people can't each be born before the other, so return arrows never happen.
- Transitive – **yes**
	- Transitive needs every two-step path to have a shortcut. If x is y's ancestor and y is z's ancestor, then x is further back up z's family line, so x is z's ancestor too. The shortcut always exists.

### Part 4: Orders
An order is just a relation that has a particular combination of the properties you already know.

$\text{Partial order}=\text{reflexive}+\text{antisymmetric}+\text{transitive}$
All three are needed. If even one is missing, it's not a partial order.

$\text{Total order}=\text{a partial order where every pair is connected}$
For any two different things $x$ and $y$, there must be an arrow one way or the other: $x\to y$ or $y\to x$. Nothing is left unconnected.

$\leq\text{on}\:\mathbb{Z}$ – **partial order ✅ & total order ✅** – any two numbers can be compared.
$=\text{on}\:\mathbb{Z}$ – **partial order ✅ & total order ❌** – 3 and 7 aren't equal either way, so they're unconnected.
$<\text{on}\:\mathbb{Z}$ – **partial order ❌ & total order ❌** – not reflexive since $3<3$ is false.
$\subseteq\text{on}\:\text{sets}$ – **partial order ✅ & total order ❌** – {1} and {2} aren't subsets of each other.

>Note: $\subseteq$ means *a subset of*

#### Example, with "is an ancestor of"
"is an ancestor of"
- *Not a partial order* because it's not reflexive.
	- A partial order needs all three properties.
- *Not a total order* because a total order has to be a partial order first.
	- You and a random stranger aren't ancestors of each other in either directed, so you're unconnected.





