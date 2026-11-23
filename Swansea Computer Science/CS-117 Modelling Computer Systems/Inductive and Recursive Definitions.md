**Modelling Computer Systems** #CS117 

##### Section 8.1: What does 'inductively defined' even mean?
Some sets are infinite, so you can't list their members. 
Writing $\{0, 1, 2, 3, ...\}$ relies on the reader guessing what "..." means.
An inductive definition replaces the "..." with exact rules.

Every inductive definition has **three clauses:**
- **Basis clause:** the starting elements that are in the set without any conditions.
- **Inductive clause:** how to build new elements from ones you already have.
- **Extremal clause:** nothing else is in the set. Only things you can build using the first two clauses count.

**Key concepts**
Here's an example, with the natural numbers $\mathbb{N}$:
1. $0\in\mathbb{N}$
2. If $n\in\mathbb{N},\text{then }n+1\in\mathbb{N}$
3. Nothing else is in $\mathbb{N}$

>**💡Knowledge Check**
> Why does the extremal clause mean that $-1\notin\mathbb{N}$?
> *$-1$ isn't added by the basis clause, since that only gives 0.
> For the inductive clause to add it, we'd need $-1\in\mathbb{N}$ first, which would need $-3$, and so on forever.
> That chain never reaches 0. Every element the clauses build starts at 0 and only ever goes up, so it's $\geq0$*. By the extremal clause, nothing else is in $\mathbb{N}$, so $-1\notin\mathbb{N}$. ✅

**Exercise**
Write a three-clause definition of the even natural numbers $\{0,2,4,\dots\}$
Then write one for the odd numbers:

*answer*
1. $0\in\mathbb{E}$
2. if $n\in\mathbb{E},\text{then }n+2\in\mathbb{E}$
3. Nothing else is in $\mathbb{E}$

----

##### Section 8.1–8.2: Basic Understanding
**Part A: "Smallest set" and membership**
The extremal clause means the same as "the set is the smallest set that satisfies the basis and the inductive clauses."

For example, $\mathbb{Z}$ (all integers) also satisfies clauses 1 and 2.
It contains 0, and adding 1 keeps you in $\mathbb{Z}$.
But it isn't the *smallest* such set. $\mathbb{N}$ is.

That gives you two techniques:

| To show...          | Do this                                                                                                                                                  |
| ------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| x is in the set     | Show the build sequence: basis, then the inductive<br>clause applied again and again.                                                                    |
| x is not in the set | Show that no build sequence can ever produce it. Usually<br>you find a property every built element has (e.g. "$\leq0$", "even")<br>that x doesn't have. |
**Part B: Values vs Syntax (Section 8.2)**
So far, our sets contained values (numbers). Computer science also needs
sets on **syntax**: symbols written on a page.
- An **alphabet** $\Sigma$ is a finite set of symbols, e.g. $\Sigma=\{a,b\}$
- A **string** (or word) over $\Sigma$ is a finite sequence of symbols, e.g. "abba".
- The **empty string** $\varepsilon$ is the string with no symbols at all.
- The **length** of a string is the number of symbols it has: $|abba|=4$ and $|\varepsilon|=0$.
- $\Sigma^*$ is the set of *all* strings over $\Sigma$.
	 *Note: the string "12" is two symbols. It isn't the number 12.*

$\Sigma^*$ has its own inductive definitions:
1. $\varepsilon\in\Sigma^*$
2. if $w\in\Sigma^*$ and $x\in\Sigma$, then $wx\in\Sigma^*$ (stick one symbol on the end)
3. Nothing else is in $\Sigma^*$

**Exercise (Part B check)**
Take $\Sigma=\{a,b\}$

>**NOTE** 💡
>You're able to choose x freely, that's the key idea here.
>The definition isn't a recipe for one particular string. It's a set of rules that is allowed to build every string over {a, b}. $\text{"aab"}$ and $\text{"bab"}$ are both in $\Sigma^*$. 
>They're just two different questions about two different strings.

**(a)** List every string in $\Sigma^*$ of length 0, 1 and 2.

**Step 0:** Plan it
Clause 2 only ever adds one symbol to the end.
So to build $\text{"aab"}$, we add its symbols in order, left to right:
$\varepsilon\to a\to aa\to aab$
That's three uses of clause 2, one per symbol, after one use of clause 1 to get started.

**Step 1:** Start with the basis
$\varepsilon\in\Sigma^*$, by clause 1.
Every build sequence starts here, because $\varepsilon$ is the only thing we get for free.

**Step 2:** Add the first symbol
- $w=\varepsilon$ (in $\Sigma^*$ from step 1)
- x = a ($a\in\Sigma$)

So,
$wx = \varepsilon a=\text{"a"}\in\Sigma^*$, by clause 2
($\varepsilon$ followed by a is just $\text{"a"}$ since $\varepsilon$ has no symbols.)

**Step 3:** Add the second symbol
- $w=$ a (in $\Sigma^*$ from step 2)
- x = a (a $\in\Sigma$)

So,
$wx = \text{"aa"}\in\Sigma^*$, by clause 2

**Step 4:** Add the last symbol
- $w=$ aa (in $\Sigma^*$ from step 3)
- x = b (b $\in\Sigma$)

So,
$wx=\text{"aab"}\in\Sigma^*$, by clause 2

**The finished answer, as you'd write it**

| Step | String                   | Reason                             |
| ---- | ------------------------ | ---------------------------------- |
| 1    | $\varepsilon\in\Sigma^*$ | Clause 1                           |
| 2    | a $\in\Sigma^*$          | Clause 2, w = $\varepsilon$, x = a |
| 3    | aa $\in\Sigma^*$         | Clause 2, w = a, x = a             |
| 4    | aab $\in\Sigma^*$        | Clause 2, w = aa, x = b            |
Therefore, $\text{"aab"}\in\Sigma^*$.
>💡 A string of length $n$ needs exactly 1 use of clause 1 and $n$ uses
>of clause 2. $\text{"aab"}$ has length 3, and we used clause 2 three times.

**(b)** Show the build sequence that proves $\text{"bab"}\in\Sigma^*$, quoting which clause you use at each step.

**Step 1:** Start with the basis.
$\varepsilon\in\Sigma^*$, by clause 1.

**Step 2:** Add the first symbol.
$w=\varepsilon$ (in $\Sigma^*$ from step 1)
x = b (b $\in\Sigma$)

So,
$wx = \varepsilon b = \text{"b"}\in\Sigma^*$ by clause 2

**Step 3:** Add the second symbol.
w = b (in $\Sigma^*$ from step 2)
x = a (a $\in\Sigma$)

So,
$wx=\text{"ba"}\in\Sigma^*$ by clause 2

**Step 4:** Add the last symbol.
w = $\text{"ba"}$ (in $\Sigma^*$ from step 3)
x = b (b $\in\Sigma$)

So,
$wx = \text{"bab"}\in\Sigma^*$ by clause 2

**The finished answer, as you'd write it**

| Step | String                   | Reason                             |
| ---- | ------------------------ | ---------------------------------- |
| 1    | $\varepsilon\in\Sigma^*$ | Clause 1                           |
| 2    | b $\in\Sigma^*$          | Clause 2, w = $\varepsilon$, x = b |
| 3    | $\text{ba}\in\Sigma^*$   | Clause 2, w = b, x = a             |
| 4    | $\text{bab}\in\Sigma^*$  | Clause 2, w = $\text{ba}$, x = b   |
Therefore, $\text{"bab"}\in\Sigma^*$.

**(c)** Is $\text{"abc"}\in\Sigma^*$? Give your reason using the definition.
