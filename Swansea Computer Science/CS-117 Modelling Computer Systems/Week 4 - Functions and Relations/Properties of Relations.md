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

----
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

----
### Part 2: Symmetric
Symmetric means every arrow has a return arrow. if $x\to y$, then $y\to x$ must be there too.

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

----
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

----
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

----
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
	 A partial order needs all three properties.
- *Not a total order* because a total order has to be a partial order first.
	 You and a random stranger aren't ancestors of each other in either directions, so you're unconnected.

#### Example, with n on $\mathbb{N}$
$0\to0$
$1\to1$
$2\to2$
$3\to3$
$\dots$

With the set of n on $\mathbb{N}$, each number is related to **only itself.**
This set is:
- **Reflexive** – every element has an arrow to itself.
- **Antisymmetric** – there's no return arrows between different elements.
- **Transitive** – the shortcut needed $1\to1\dots$ so, every shortcut is there.

That makes it a **partial order.**

#### Example, with the relations $\mathbb{U}$
>Note: $\mathbb{U}$ is the universal relation – its a set where every number has an arrow to every number, including itself.

The set of $\mathbb{U}$ is:
- **Reflexive** – every element has an arrow to itself.
- **Symmetric** – every element of $x$ is related to $y$.
- **Transitive** – every element is related to one another, each shortcut is present.

Because it's reflexive, **not** antisymmetric, and transitive – it's not a **partial order**, or a **total order** as a set must be partial before it's a full order.

#### Example, with the relations $\mathbb{P}$
>Note: $\mathbb{P}$ (parity, P) is the relation where two numbers are related if they're **both even** or **both odd**.
>$2 \to 4,\ 4 \to 2,\ 1 \to 3,\ 3 \to 1,\ 2 \to 2,\ \dots$ but NOT $1 \rightarrow 2$

parity, $\mathbb{P}$ is:
- **Reflexive** – every number has the same parity as itself. 2 is even and 2 is even, so $2\to2$ works.
- **Symmetric** – every element connected has an arrow connected back.
- **Transitive** – $2\to4$ means 2 and 4 are both even, $4\to6$ means 4 and 6 are both even, so 2 and 6 must be both even too, giving the shortcut $2\to6$!

parity, $\mathbb{P}$ isn't antisymmetric though – $2\to4$ and $4\to2$ is a return arrow between different numbers.

This means that parity, $\mathbb{P}$ is not a partial order, and so not a to

----
### Part 5: Equivalence relations

**Equivalence relation = reflexive + symmetric + transitive**
You can compare that with a partial order:
- **Partial order:** reflexive + antisymmetric + transitive, which puts things in order.
- **Equivalence:** reflexive + symmetric + transitive, which groups things that match.

An equivalence relation is like saying "is the same kind as". 
Things that are related belong in the same group.

1. **Identity** (I) 
	 **Reflexive:** every number has a loop ($1\to1$, $2\to2$, $\dots$)
	 **Symmetric:** the only arrows are loops, and a loop is its own return arrow.
	 **Transitive:** the only two-step paths are like $1\to1\to1$, and the shortcut $1\to1$ exists.

2. **Universal (U)**
	 **Reflexive:** every number is related to everything, including itself.
	 **Symmetric:** every possible arrow exists, so every return arrow exists too.
	 **Transitive:** every possible arrow exists, so every shortcut exists.
3. **Parity (P)**
	 **Reflexive:** every number has the same parity as itself.
	 **Symmetric:** if x and y are both even (or both odd), then y and x are too.
	 **Transitive:** if x matches y and y matches z, then x matches z.

**Why they're all equivalences**
- **Identity:** every number is in its own group, like $\{0\}, \{1\}, \{2\}\dots$
- **Universal:** all numbers are in **one big group.**
- **Parity: two groups**, the evens and the odds.

----

### Part 6: Partitions
A partition is **splitting a set into groups**, and the groups must follow three rules:
1. **No empty groups.** Every group has at least one thing in it.
2. **No overlaps.** Nothing appears in two groups.
3. **Nothing left out.** Everything in the set is in some group.

*Example*
For $A=\{1,2,3,4\}$
**Partitions:**
- $\{1,2\}\;\{3,4\}$
- $\{1,3,4\}\;\{2\}$

**Not partitions:**
- $\{1\}, \{3,4\}$, because **2 is left out**
- $\{1,2\}\;\{2,3,4\}$ because **2 is in two groups**

##### How this links to equivalence relations
Every equivalence relation **splits a set into groups,** and every partition gives you an equivalence relation, where things are related if they're in the same group.
- **Parity** splits $\mathbb{N}$ into {evens} and {odds},
- **Same month of birth** splits people into up to 12 groups, one per month.

Each group is called an **equivalence class**.

*Exercise*
Which of these are partitions of $A=\{a,b,c,d\}$?
1. $\{a\}, \{b, c\}, \{d\}$ – **partition of $A$**
2. $\{a, c\}, \{b,d\}$ – **partition of $A$**
3. $\{a,c\}, \{b\}$ – **not a partition of $A$** – not every element in the set is in some group.
4. $\{a,b,c,d\}$ – **partition of $A$**
5. $\{a,c\}, \{b\}, \{c,d\}$ – **not a partition of $A$** – c is in a group twice.
6. $\{a\}, \{b\}, \{c\}, \{d\}$ – **partition of $A$**

*Exercise*
How many partitions are in the set $A=\{1, 2, 3\}$?
1. $\{1, 2, 3\}$
2. $\{1\}, \{2\}, \{3\}$
3. $\{1, 2\}, \{3\}$
4. $\{1\}, \{2, 3\}$
5. $\{1, 3\}, \{2\}$

There are a total of 5 different partitions.
**Never forget that the whole set on its own, (e.g. $\{1, 2, 3\}$) is a set on its own!**

