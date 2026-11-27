---
tags:
  - CS117
  - coursework
released: 2026-11-13
due: 2026-11-27
group-work: true
---
>[!info] Task
>Fix a set $\mathbb{V}$ of propositional variables. Recall that propositional formulas can be defined inductively as follows:
>
>$p,q ::= \text{true} \mid \text{false} \mid P, (P \in \mathcal{V}) \mid p \lor q \mid p \land q \mid p \Rightarrow q \mid \neg p$
>
>Let us denote by Form the set of formulas thus defined. Observe that in the lectures we also introduced the connective $\leftrightarrow$, which we will not include for the purpose of this assignment. Consider the subset $Form_0 \subseteq Form$ which is inductively defined as follows:
>
>$p,q ::= \text{false} \mid P, (P \in \mathcal{V}) \mid p \Rightarrow q$


>[!important] Task 1
>Inductively define a function $f : Form \to Form_0$ that takes as input a formula $p$ and outputs an equivalent formula $f(p)$.
>
>**Hint.** First think about how you can define the other propositional connectives in terms of the connective $\Rightarrow$ and the constant "false".

1. Check if they're base or inductive & small formula count.

| Option          | Base or inductive? | Small formula count? |
| --------------- | ------------------ | -------------------- |
| true            | base               | 0                    |
| false           | base               | 0                    |
| P               | base               | 0                    |
| p $\lor$ q      | inductive          | 2 (p, q)             |
| p $\land$ q     | inductive          | 2 (p, q)             |
| p $\Rightarrow$ | inductive          | 2 (p, q)             |
| $\neg$p         | inductive          | 1 (p)                |

2. Check whether it is allowed in the target set.

| Form option       | in Form0?          |     |
| ----------------- | ------------------ | --- |
| true              | ==🔴no== ==🟢yes== |     |
| false             | ==🟢yes==          |     |
| P                 | ==🟢yes==          |     |
| p $\lor$ q        | ==🔴no==           |     |
| p $\land$ q       | ==🔴no==           |     |
| p $\Rightarrow$ q | ==🟢yes==          |     |
| $\neg$p           | ==🔴no== ==🟢yes== |     |
$\text{A function }f : \text{Form} \to \text{Form}_0 \text{ defined inductively is as follows:}$

- `f(false) = false`
- `f(P) = P`
- `f(p`$\Rightarrow$`q) = f(p)`$\Rightarrow$`f(q)
- `f(true) = false`$\Rightarrow$`false`
- `f(`$\neg$`p) = f(p)`$\Rightarrow$`false`
- `f(p`$\lor$`q) =` `f(p`$\lor$`q) =` `(f(p)`$\Rightarrow$`false)`$\Rightarrow$ `f(q)`
- `f(p`$\land$`q)  = (f(p)`$\Rightarrow$`(f(q)`$\Rightarrow$`false))` $\Rightarrow$ `false`

>[!important] Task 2
>**Prove by induction** that your function $f$ indeed maps every formula $p$ to an equivalent formula $f(p)$. **Use truth tables to justify that two given formulas are equivalent.**
>

>In other words, prove that your function:
>(function is Form, not $Form_0$)
>
>(the seven equations written in Q1)
>maps to every formula p to an equivalent formula f(p)
>
>Whatever formula you feed into f, what comes out should mean the same thing. It should have the same T/F in every row of a truth table. f changes how the formula looks
>(only false and $\Rightarrow$ allowed!), never what it *means*.

Case **false**:
`f(false)` = `false` – *by definition of f* 

| false | f(false) = false |
| ----- | ---------------- |
| F     | F                |
The last two columns match,
therefore `f(false)` $\equiv$ `false`

Case **P** (for each P $\in \mathbb{V}$):
`f(P) = P`  – *by definition of f*

| P   | f(P) = P |
| --- | -------- |
| T   | T        |
| F   | F        |
Both columns match,
therefore `f(P) `$\equiv$ `P


Case **true**:
`f(true) = false`$\Rightarrow$`false` – *by definition of f*

| false | false | false $\Rightarrow$ false | true |
| ----- | ----- | ------------------------- | ---- |
| F     | F     | T                         | T    |
The last two columns match,
therefore `f(true)` $\equiv$ `true`












-----
##### Practice Question

>[!info] Practice Task
>Fix a set $\mathbb{V}$ of propositional variables. Recall that propositional formulas can be defined inductively as follows:
>
>$p,q ::= \text{true} \mid \text{false} \mid P, (P \in \mathcal{V}) \mid p \lor q \mid p \land q \mid p \Rightarrow q \mid \neg p$
>
>Let us denote by Form the set of formulas thus defined. Observe that in the lectures we also introduced the connective $\leftrightarrow$, which we will not include for the purpose of this task. Consider the subset $Form_N \subseteq Form$ which is inductively defined as follows:
>
>$p,q ::= \text{false} \mid P, (P \in \mathcal{V}) \mid \neg p \mid p \land q$
>

>[!important] Question 1
>**1.** Inductively define a function $f_N : Form \to Form_N$ that takes as input a formula $p$ and outputs an equivalent formula $f_N(p)$.
>
>**Hint.** First think about how you can define the other propositional connectives in terms of the connectives $\neg$, $\land$ and the constant "false".


**Step 1. Check if they're base or inductive & how many small formulas they have.**

| Option | Base or inductive? | How many smaller formulas? |
| ------ | ------------------ | -------------------------- |
| true   | base               | 0                          |
| false  | base               | 0                          |
| P      | base               | 0                          |
| p ∨ q  | inductive          | 2 (p, q)                   |
| p ∧ q  | inductive          | 2 (p, q)                   |
| p ⇒ q  | inductive          | 2 (p, q)                   |
| ¬p     | inductive          | 1 (p)                      |
|        |                    |                            |

**Step 2. The base cases**
For each option, check whether it is allowed in the target set.
1. Yes: copy it across unchanged.
2. No: find an equivalent formula built only from allowed parts, and check it with a truth table.


| Form option       | In Form0? | What to do                                                                   |     |
| ----------------- | --------- | ---------------------------------------------------------------------------- | --- |
| true              | ❌ no ✅    | rebuild using false and $\Rightarrow$                                        |     |
| false             | ✅ yes     | copy it: f(false) = false                                                    |     |
| P                 | ✅ yes     | copy it: f(P) = P                                                            |     |
| p $\lor$ q        | ❌ no      | rebuild using false and $\Rightarrow$                                        |     |
| p $\land$ q       | ❌ no      | rebuild using false and $\Rightarrow$                                        |     |
| p $\Rightarrow$ q | ✅ yes     | keep the $\Rightarrow$, but apply f to both sides<br>f(p) $\Rightarrow$ f(q) |     |
| $\neg$p           | ❌ no      | rebuild using false and $\Rightarrow$                                        |     |

to build **true:**
`f(true) = false`$\Rightarrow$`false`

to build $\neg$ p:
`f(`$\neg$`p) = p`$\Rightarrow$`false`

| p   | q   | p $\Rightarrow$ q | p $\Rightarrow$ false | $\neg$ p |
| --- | --- | ----------------- | --------------------- | -------- |
| T   | T   | T                 | F                     | F        |
| F   | T   | T                 | T                     | T        |
| T   | F   | F                 | F                     | F        |
| F   | F   | T                 | T                     | T        |
|     |     |                   |                       |          |

to build $\lor$:
`f(p`$\lor$`q) =` `(f(p)`$\Rightarrow$`false)`$\Rightarrow$ `f(q)`

| p   | q   | $\neg$ p | $\neg$ q | p $\Rightarrow$ q | p $\Rightarrow$ $\neg$ q | $\neg$ p $\Rightarrow$ q | p $\lor$ q |
| --- | --- | -------- | -------- | ----------------- | ------------------------ | ------------------------ | ---------- |
| T   | T   | F        | F        | T                 | F                        | T                        | T          |
| F   | T   | T        | F        | T                 | T                        | T                        | T          |
| T   | F   | F        | T        | F                 | T                        | T                        | T          |
| F   | F   | T        | T        | T                 | T                        | F                        | F          |


to build $\land$:
f(p $\Rightarrow$ (q$\Rightarrow$false)) $\Rightarrow$ false

| p   | q   | $\neg$ p | $\neg$ q | p $\Rightarrow$ q | $\neg$ (p $\Rightarrow$ $\neg$ q) | p $\land$ q |
| --- | --- | -------- | -------- | ----------------- | --------------------------------- | ----------- |
| T   | T   | F        | F        | T                 | T                                 | T           |
| F   | T   | T        | F        | T                 | F                                 | F           |
| T   | F   | F        | T        | F                 | F                                 | F           |
| F   | F   | T        | T        | T                 | F                                 | F           |


>[!important] Question 2
>**2.** Prove by induction that your function $f$ indeed maps every formula $p$ to an
equivalent formula $f (p)$. Use truth tables to justify that two given formulas
are equivalent.

**For false**. f(p) = false – *by definition of f*
Since false $\equiv$ false, we have f(false) $\equiv$ false

**For P** (for each P $\in \mathcal{V}$). f(P) = P – *by definition of f*
Since P $\equiv$ P, we have f(P) $\equiv$ P

**For true.** f(true) = false $\Rightarrow$ false – *by definition of f*

| false | false | false $\Rightarrow$ false | true |
| ----- | ----- | ------------------------- | ---- |
| F     | F     | T                         | T    |
The last two columns match, 
therefore f(true) $\equiv$ true

**For $\neg$ p**. f($\neg$p) = p $\Rightarrow$ false $\equiv$ $\neg$p – *by inductive hypothesis, we can prove it through:*

| p   | q   | p $\Rightarrow$ q | p $\Rightarrow$ false | $\neg$ p |
| --- | --- | ----------------- | --------------------- | -------- |
| T   | T   | T                 | F                     | F        |
| F   | T   | T                 | T                     | T        |
| T   | F   | F                 | F                     | F        |
| F   | F   | T                 | T                     | T        |
Since 


**For p $\lor$ q**. Assume f(p) $\equiv$ p and f(q) $\equiv$ q 
$\equiv$ $\neg$($\neg$p $\lor$ $\neg$q) = $\neg$($\neg$f(p)$\lor \neg$f(q)) – *by definition of f*
$\equiv$ p $\lor$ q (by the truth table below)

| p   | q   | $\neg$ ($\neg$ p $\land$ $\neg$ q) | p $\lor$ q |
| --- | --- | ---------------------------------- | ---------- |
| T   | T   | T                                  | T          |
| T   | F   | T                                  | T          |
| F   | T   | T                                  | T          |
| F   | F   | F                                  | F          |
