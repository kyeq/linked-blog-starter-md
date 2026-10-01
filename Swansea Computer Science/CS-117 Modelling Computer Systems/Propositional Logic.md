#### Logical argument
Consider the following argument:

1. Either this man is dead, or my watch has stopped.
2. My watch is still ticking.
3. Therefore, this man is dead.

If you believe the first two statements, then, you must believe the third statement.

The first two statements are often called the premises, and the third statement is often called the conclusion.

This type of argument is called a **deduction** – this is when you make an argument that states "this is true, this is true, so therefore, this is true"

#### Propositions, or statements
are declarations which are either true or false.

The following are propositions:
- ==2+3 = 5== – *This is a statement because we can assign a declaration of truth value. (True)*
- ==2+3 = 6== – *This is a statement because we can assign a declaration of truth value. (False)*
- Joel didn't do his homework. – *The statement is true or false.*
- What Felix says is false. – *This is a statement as well.*

The following are **not** propositions:
- ==2 + x = 6== – *2+x=6 not a proposition because it has a variable that isn't definitive. Predicated on x. Without knowing what x is, you cannot assign it a truth value.*

- Do your homework, Joel! – *You can't assign a truth value to this, it's a command, and its not in the scope of propositional logic.*
- Is there life on Mars? – *Not a statement, because the question itself doesn't have a truth value.*
- What this sentence says is false. – *Paradoxical - you can't assign a truth value.*

---
#### Deductions / Inferences
A deduction, or inference, is when you deduce, or infer, one statement (a conclusion) from one or more other statements (premises)

| Valid deductions                                                                        | Invalid deductions                                                                       |
| --------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| All men have green blood.<br>Socrates is a man.<br>Therefore, Socrates has green blood. | All men have green blood.<br>Socrates has green blood.<br>Therefore, Socrates is a man.  |
| Some animals are mammals.<br>All mammals lay eggs.<br>Therefore, some animals lay eggs. | Some animals are mammals.<br>Some mammals lay eggs.<br>Therefore, some animals lay eggs. |

> [!NOTE] Explanation
> All men have green blood... Socrates is a man... Therefore, Socrates has green blood.
> *This is a valid deduction because it states that all men have green blood, and that socrates is a man.*
> 
> Some animals are mammals... Some mammals lay eggs... Therefore, some animals lay eggs.
> *This is an invalid deduction because it never states that some animals lay eggs, only that some mammals lay eggs.*

### The Language of Propositional Logic
For propositional variables, we will always use upper-case letters or (more commonly) meaningful words starting with an upper-case letters.

**Example**: Let *Dead* represent the statement: *This man is dead*

Algebraic formulas are build up using four basic operations:
1. Addition (+)
2. Subtraction (-)
3. Multiplication (x)
4. Division (÷)

Propositional formulas use five basic propositional connective (operations):
1. not ( ¬ )
2. and ( ∧ )
3. or ( ∨ )
4. implies ( → )
5. is equivalent to ( ↔ )
---
#### Negation
*Connective:* Negation
*Symbol:* ¬ p
*Pronounced:* "not p"

*in English:*
- *not* p *(or, rather, statement p with "not" after verb)*
- p *does not hold / is not true / is false*
- *it is not the case that* p

**Example:** if Dead stands for "This man is dead", then ¬ Dead says:
- The man is not dead.
- It is not the case that this man is dead.

	Exercise
	*Rewrite the following statements without negations at the start.*
	1. ¬ "The Earth revolves around the sun"
	2. ¬ "All of my children are boys"
	3. ¬ (2 + 2 ≤ 4)

	4. The Earth does not revolve around the sun. ✅
	5. Not all of my children are boys. ✅
	6. (2 + 2 > 4) ✅ or (2+2 ≰ 4) – *Typically, if one integer is not less than or equal to another integer, then it must be strictly greater than the other integer.* 

```
¬ ¬ p is equivalent to p
```

***This is known as the Law of Double Negation***

---
#### Conjuction
*Connective:* Conjunction
*Symbol:* p ∧ q (p and q are called conjuncts)
*Pronounced:* "p and q"

*in English:*
- p and q
- p but q
- not only p but also q

**Example:** if Dead stands for "this man is dead," and Stopped stands for "My watch has stopped", then Dead ∧ Stopped says
- *This man is dead and my watch has stopped*
- Not only is this man dead, but so is my watch

---
#### Disjunction
*Connective:* Disjunction
*Symbol:* p ∨ q (p and q are called disjuncts)
*Pronounced:* "p or q"

*in English:*
- p or q
- p or q or both
- p and/or q
- p unless q

**Example:** if Dead stands for "This man is dead" and Stopped stands for "My watch has stopped", then Dead ∨ Stopped says
- Either this man is dead or my watch has stopped
- If this man is alive, then my watch must have stopped

*(Possibly the man is dead and the watch has stopped)*

---
#### Conjunction and Disjunction
Exercise
Are the following disjunctions true or false?

1. C1 – (3 < 2) ∧ (3 < 5) – ❌
2. C2 – (5 < 4) ∧ (7 < 5) – ❌
3. C3 – (5 < 6) ∧ (6 < 8) – ✅

4. D1 – (3 < 2) ∨ (3 < 5) – ✅
5. D2 – (5 < 4) ∨ (7 < 5) – ❌
6. D3 – (5 < 6) ∨ (6 < 8) – ✅

🎉 **ALL CORRECT! 6/6**

**Observation:** As ¬ p is true whenever p is *not* true,
p ∧ ¬p will always be false, and
p ∨ ¬p will always be true.

(The latter is known as the Law of Excluded Middle)

#### Inclusive vs Exclusive Or
The disjunction operation ∨ is always used in an *inclusive* sense, in that it is true if **one or both** disjuncts are true. For example:

- *Joel came in last place in the round-robin competition; thus,
  either Felix beat him or Oskar beat him.*
	(It may be the case that both Felix and Oskar beat Joel)

Sometimes an **exclusive** interpretation is intended when we use the word "or", whereby we allow *only one* of the disjuncts to be true. For example:

- *The light is either on or off.*
- *You can either have coffee or tea with your meal.*

This kind of disjunction, written ⊕, is called **exclusive or***

---
#### Implication
*Connective:* Implication
*Symbol:* p → q
*Pronounced:* "p implies q"

*in English:*
- p implies q
- if p then q
- q if p
- p only if q
- q whenever p
- p is a sufficient condition for q
- q is a necessary condition for p

**Example:** If SignalRed stands for "The signal shows red" and TrainStop stands for "The train stops", then SignalRed → TrainStop says "If the signal shows red then the train stops."

The only scenario in which this statement is false is if the signal shows red but the train does not stop. Hence the statement does not contradict the situation in which the signal does not show red and yet the train nevertheless stops.

Exercise
Let JoelHappy stand for "Joel is happy"
and let AmandaHappy stand for "Amanda is happy"

Each of these three statements below translates as either:

JoelHappy → AmandaHappy or as AmandaHappy → JoelHappy

1. Joel is happy whenever Amanda is happy – AmandaHappy → JoelHappy
2. Joel is happy only if Amanda is happy – JoelHappy → AmandaHappy – *Joel can ONLY be happy, if AmandaHappy*
3. Joel is happy unless Amanda is not happy – AmandaHappy → JoelHappy

---
#### Equivalence
*Connective:* equivalence
*Symbol:* p ⇔ q
*Pronounced:* "p if, and only if, q"

in English:
- p if, and only if, q
- p is equivalent to q
- p is a necessary and sufficient for q

**Example:** Let TrainEnter stand for "The train enters the tunnel" and TunnelClear stand for "The tunnel is clear"

Then TrainEnter ⇔ TunnelClear says
"The train enters the tunnel if, and only if, the tunnel is clear"

This statement is false if one of these two scenarios holds:
- The train enters the tunnel while the tunnel is not clear;
- The tunnel is clear but the train does not enter

p ⇔ q is equivalent to (p ⇔ q) ∧ (q → p) 
*Saying*:
- p is true, and only if, q is true
*Is the same as saying:*
- if p is true then q is true and if q is true then p is true

p → q is equivalent to ¬ p ∨ q
*Saying:*
if p is. true then q is true
*Is the same as saying:*
either p is false or q is true

---
> **Refresher** ♻️

**Definition**
A propositional formula is either
- An atomic formula, typically an uppercase variable P, Q, R etc.; or
- A compound formula build up using connectives

Two special atomic formulas:
- **true** (the proposition which is always true)
- **false** (the proposition which is always false)

P ∨ Q → R could be read in two very different ways:
- (P ∨ Q) → R
- or
- P ∨ (Q → R)

We define a precedence for connectives to reduce the need for parentheses
(and increased readability)

![[Screenshot 2026-10-01 at 12.37.27 PM.png]]


P, Q statements

> **P → Q**
   if P then Q
   Q if P
   P only if Q

1. "Joel is happy only if Amanda is happy"
2. "Joel is ==only happy== if Amanda is happy"
	 ^ *These are equivalent*

3. I will only trust you if you did not lie to me about the cake.
4. I will trust you only if you did not lie to me about the cake.
	 ^ *These are equivalent*

5. You will only pass the exam if you understand propositional logic.
6. You will pass the exam only if you understand propositional logic.
	 ^ *These are equivalent*

> It does NOT say: if you understand propositional logic, then you will pass.
> it DOES say: if you don't understand propositional logic, then you won't pass the exam.

¬Q → ¬P

**Syntax trees**
 ![[Screenshot 2026-10-01 at 12.39.04 PM.png]]

**Well-formed Formulas (wff)**
A syntactically-correct formula is called a **well-formed formula (wff)**

For example, the string of symbols ¬(P ∨ ( ∧ (Q, R) → P)))
fails to be a well-formed formula.

This could be simplified 

**Exercise**
> Defining Further Propositional Operators

The *exclusive or* operation p 