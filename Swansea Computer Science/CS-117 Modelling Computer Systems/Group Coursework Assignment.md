#CS117 

Fix a set $\mathbb{V}$ of propositional variables. Recall that propositional formulas can be defined inductively as follows:

$p,q::=true\:|\:false\:|\:P,\:(P\in\mathbb{V})\:|\:p\lor q\:|\:p\land q\:|\:p\to q\:|\:\lnot p$

Let us denote by Form the set of formulas thus defined.
Observe that in the lectures we also introduced the connective $\Leftrightarrow$, which we will not include for the purpose of this assignment. Consider the subset $Form_0$ $\subseteq$ $Form$ which is inductively defined as follows:

$p,q::=false\:P,(P\in\mathbb{V})\:|\:p\to q$

Connectives:
- true
- false – *this connective is present in the small set*
- $\land$ 
- $\lor$ 
- $\implies$ – *this connective is present in the small set*

Connective formulas:
- f(true) = false $\implies$ false
- f(false) = false
- f(P) = P(for each P $\in\mathbb{V}$)
- f(p $\lor$ q) = (f(p)$\implies$false)$\implies$f(q)
- f(p $\land$ q) = (f(p) -> ((f(q)->false)) -> false
- f(p$\implies$q) = f(p)$\implies$f(q)
- f($\lnot$ p) = f(q) $\implies$false

## 2
Prove by induction that your function $f$ indeed maps every formula $p$ to an equivalent formula $f(p)$. Use truth tables to justify that two given formulas are equivalent.


### Practice Question

![[Screenshot 2026-11-22 at 22.26.20.png|281]]

### Base Clause
Left = just 2
Right side = $n(n+1)$ = 2 (1*(1+1)=2)
**Base case (n = 1):** the left side is 2 and the right side is 1 x (1 + 1) = 2. 
They're equal, thus the statement holds for $n=1$

### Inductive Clause
assume 2 + 4 + 6 ... + 2n = n(n + 1)
2+4+6...+2n = 



| n   | Last term (2n) | Left Side | Total |
| --- | -------------- | --------- | ----- |
| 1   | 2              | 2         | 2     |
| 2   | 4              | 2+4       | 6     |
| 3   | 6              | 2+4+6     | 12    |

