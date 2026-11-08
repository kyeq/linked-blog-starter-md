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
- C: 