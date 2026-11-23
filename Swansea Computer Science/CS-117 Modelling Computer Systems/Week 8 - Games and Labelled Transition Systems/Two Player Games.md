#CS117 

#### Two Player Games of No Chance
- These are games of **pure strategy** – no luck involved.
	- *for example, no dice or cards *(e.g. chess)*

**Strategy:** A rule telling a player which move to make every time it's their turn.
**Winning strategy:** Guarantees a win whatever the opponent does.
**Drawing strategy:** If draws are possible, guarantees you won't lose (but not that you'll win!)
**Winning position:** A position where you have a winning strategy.
**Losing position:** A position where the other player has a winning strategy.
**In any game:** Either one player has a winning strategy, or both players have drawing strategies.

> You're always asking: from this position, can the player about to move force a win?

#### Why Games?
- A computer running a program is playing a game against the user who gives the input.
- The program = the **the computer's strategy**. The computer wins if it computes the correct result.
- The user is the **adversary,** trying to confound the computer.
- A correct program = a **winning strategy.**
- In software engineering, this game shows up as **software testing.**
- A **controller vs its environment** works the same way: the controller tries to maintain the system's properties and the environment tries to break them.

> This is why games turn up in a modelling module:
> 	correctness = having a winning strategy.

#### Take-3
- **Rules:** one pile of coins. Player takes turn removing 1, 2 or 3. Whoever takes the last coin wins.
- 1, 2, 3 coins: first player wins (takes them all).
- 4 coins: second player wins.
- 5, 6, 7 coins: first player wins (take 1, 2, 3 respectively, leaving 4).
- 8 coins: second player wins.
- **General rule:** the first player wins unless the pile is a multiple of 4.
- **Winning move:** leave your opponent a **multiple of 4** (take $n \text{ mod } 4$) 

![[Pasted image 20261118113446.png|522]]

> If your opponent takes k, you take 4 – k, so each round removes exactly 4.

#### Winning verses Losing Positions
- **Winning positions:**
	- there exists ($\exists$) a move I can make such that, for every ($\forall$) move you might make, there exists ($\exists$) a move I can make such that, for every ($\forall$) move you might make, ... ... ... I will win the game.
- **Losing positions:**
	- for every ($\forall$) move I might make, there exists ($\exists$) a move you can make such that, for every ($\forall$) move I might make ... ... ... you will win the game.

Each definition is the logical negation of the other ($\exists\leftrightarrow\forall$)
**Summary:**
- From a winning position, there exists a move leading to a losing position.
- From a losing position, every move leads to a winning position.

> To solve a game, work backwards from the end and label each position W or L using these two rules.


#### Raisins
- **Rules:** two non-empty piles. On your turn you eat one pile and split the other into smaller non-empty piles. If you can't move, you lose.
- The only stuck position is (1, 1), because a pile of 1 can't be split.
- **Fact:**
	- **Losing position:** both piles odd.
	- **Winning position:** at least one pile is even.

- **From a winning position:** eat the other pile and split the even pile into two odd piles. Your opponent is now in a losing position.
- **From a losing position:** you have to split an odd pile, which always gives one even pile. Your opponent is now in a winning position.

> Even = odd + odd, but odd = odd + even, which is why this works.

#### Nim
In actual fact, it is straightforward to determine who has the winning strategy in Nim using the following observation;
- Write out the numbers of coins in the piles in binary, one above the other, and add up the columns module 2 (ie 0 if the sum is even, 1 if the sum is odd); call the position ***balanced*** if all columns sums are even; otherwise call it ***unbalanced****.

**Every** move from a balanced position leaves an unbalanced one.
**Some** move from an unbalanced position leaves a balanced one.
The goal is to leave the piles in the balanced position consisting of no coins in any piles.


