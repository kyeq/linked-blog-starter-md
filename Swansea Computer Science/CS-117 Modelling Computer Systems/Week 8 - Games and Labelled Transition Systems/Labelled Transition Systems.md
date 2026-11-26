#CS117 

### What is a Computation?
Consider the following algorithm for computing the greatest common divisor of two numbers $x$ and $y$. 
```
forever do:
	x := x mod y;
	if x=0 then return y;
	if y:= mod x;
	if y=0 then return x
```

> Note:
> 	:= means assignment (setting a variable)
> 	x:= x mod y means **work out** x mod y
> 	mod is the remainder after division (e.g. 17 mod 5 = 2)

for example, to understand this program, you can hand-turn it, keeping track of the state variables:

![[Pasted image 20261118163342.png]]

The steps are as follows:

| Step  | Arrow Label         | Working                            | New State    |
| ----- | ------------------- | ---------------------------------- | ------------ |
| start |                     |                                    | x=246, y=174 |
| 1     | $x:=x\text{ mod }y$ | 246 mod 174 $\to$ 246 = 1x174 + 72 | x=72, y=174  |
| 2     | $y:=y\text{ mod }x$ | 174 mod 72 $\to$ 174 = 2x72 + 30   | x=72, y=30   |
| 3     | $x:=x\text{ mod }y$ | 72 mod 30 $\to$ 72 = 2x30 + 12     | x=12, y=30   |
| 4     | $y:=y\text{ mod }x$ | 30 mod 12 $\to$ 30 = 2x12 + 6      | x=12, y=6    |
| 5     | $x:=x\text{ mod }y$ | 12 mod 6 $\to$ 12 = 2x6 + 0        | x=0, y=6     |
Therefore, the greatest common divisor of the two numbers $x$ and $y$, is 6.

### Modelling Processes
A computation, or more generally a process, is represented by a Labelled Transition System (LTS), which consists of a set of states, wit transitions from one state to another state labelled by events.

**Example:** A lamp process

![[Pasted image 20261118171823.png|546]]

The execution of this process can be traced by placing a token on a state, and moving it from state to state along arrows representing events.

In this model of the process of this lamp, pulling the lamp turns it on, and then pulling it again turns it off (ON & OFF states). If for example the circuit breaker is broken, pulling results in the lamp going into the BROKEN state. If you try pull whilst it's in the broken state & it is still broken, the state doesn't change – it loops back around to the BROKEN state. If you reset it, then the lamp goes to the OFF state.

### LTS - The Formal Definition
A labelled transition system (LTS) is a triple
$T = (\text{States, Actions,}\to)$
consisting of:
- a set of States of states;
- a set of Actions of actions or events; and
- a set $\to\subseteq\text{States x Actions x States}$ of transitions between states, which are labelled by actions (a transition relation)

We generally write $\text{s}\to^a\text{t}$, or the more pictorial version:
![[Pasted image 20261118172512.png|269]]

instead of (s, a, t) $\in\to$, meaning that in state $s$, we may do the action $a$ and thereby evolve into the state $t$.

#### A Simple Vending Machine Example

![[Pasted image 20261118201955.png|434]]

#### Car Safety System Example

![[Pasted image 20261118202100.png]]

### The LTS of a Game
We can use labelled transition systems to analyse games.

**Example:**
*Starting with a pile of 10 coins, two players take turns removing 2 or 3 coins from the pile. Whoever takes the last coin wins; if one coin remains, then the game is a draw.*

![[Pasted image 20261118202212.png]]

Here, the states are the positions, and the transitions are the moves. The winning positions (states) are circled in blue, and the losing positions (states) are squared in red. The optimal moves (transitions) are depicted by blue arrows.

### The Man-Wolf-Goat-Cabbage Riddle
A man is to cross a river with a wolf, a goat and a cabbage, but his boat can only carry himself and one of his three possessions, so he must transport these items one at a time.

However, if he leaves the wolf and the goat together unattended, then the wolf will eat the goat; similarly, if he leaves the goat and the cabbage together unattended, then the goat will eat the cabbage.

How can the man get across safely with his three items?

This puzzle can be solved by modelling it with a labelled transition system (LTS), in which a state represents the current position (left or right bank) of the four entities (man, wolf, goat, cabbage), and there are four events representing the four possible actions that the man can take:
- $m$ = the man crosses the river on his own;
- $w$ = the man crosses the river with the wolf;
- $g$ = the man crosses the river with the goat;
- $c$ = the man crosses the river with the cabbage.

![[Pasted image 20261118203017.png]]
### Cops and Robbers
Three cops are transporting three robbers to jail on foot through a jungle when they come upon a river. They have a boat, but it can only hold two people. The problem is: the robbers can never be allowed to outnumber the cops on either side of the river. Each cop and each robber can row the boat.

So, **how can all six get across the river?**

This puzzle can be solved by modelling it with an LTS (Labelled Transition System), in which a state represents the current positions of the six people and the boat (left or right bank), and there are five events representing the five possible actions that can happen:

- $c$ = one cop crosses the river on their own;
- $cc$ = two cops cross the river;
- $r$ = one robber crosses the river on their own;
- $rr$ = two robbers cross the river;
- $cr$ = one cop and one robber cross the river

**Solution**
![[Pasted image 20261126090356.png]]
A (shortest) solution: $cr,c,rr,r,cc,cr,cc,r,rr,r,rr.$

### Water Jugs
In the 1995 film Die Hard: With a Vengence, New York Detective john McClane (played by Bruce Willis) and Harlem dry cleaner Zeus Carver (played by Samuel L. Jackson) had to solve the following problem in order to prevent a bomb from exploding at a public fountain.

Given only a five-gallon jug and a three-gallon jug, neither with any markings on them, they had to fill the larger jug with exactly four gallons of water from the fountain, and place it onto a scale in order to stop the bomb's timer and prevent disaster.

**How did they manage this feat?**
A state of the system underlying this riddle consists of a pair of integers (i, j) with 0 $\leq$ i $\leq$ 5 and 0 $\leq$ j $\leq$ 3, representing the volume of water in the 5-gallon and 3-gallon jugs $A$ and $B$, respectively. The initial state is ($0, 0$) and the final state you wish to reach is ($4, 0$).

There are six possible moves from a given state (i, j):
![[Pasted image 20261126091415.png]]
### Modelling an Elevator
Here is a very simplistic model of an elevator servicing three floors which reflects only its movement:
![[Labelled Transition Systems 2026-11-26 09.16.15.excalidraw]]