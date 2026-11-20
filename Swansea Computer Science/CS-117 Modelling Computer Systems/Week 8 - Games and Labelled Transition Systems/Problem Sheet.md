#CS117 

Every game on this sheet has these features:
- two players take turns
- both players can see everything
- there's no luck
- the game always ends, and whoever makes the last move wins.

In games like this, every position is one of two types, judged from the point of view the player whose turn it is:
- **Losing position (L):** every move you can make leaves your opponent in a winning position (A position with no moves left is also L, because your opponent just made the last move.)
- **Winning position (W):** at least one move leaves your opponent in a losing position. That move is the "winning move".

If you're in a W position, you always move to an L position. Your opponent then has to hand you back a W position, because L means every move from there gives you a W. That repeats until they're stuck with nothing left. 

"The first player has a winning strategy" just means the starting position is W. 

**How to find them**
start from the end (0 coins, which is L) and work upwards one position at a time. This is called **backward induction**. Each position depends only on the positions you can reach from it, and those are smaller, so you'll already have worked them out.

**Question 1:**
There is a single pile of coins, and two players alternately remove either 1, 2, or 3 coins from the pile. The player who takes the last coin wins.

(a): For each number n from 1 to 12, explain who has the winning strategy starting from a pile of n coins. In the case in which the first player has the winning strategy, state how many coins (1, 2, or 3) the first player should take.

| n         | Where can I move?                     | Type | Winning move     |
| --------- | ------------------------------------- | ---- | ---------------- |
| 0         | nowhere (opponent took the last coin) | L    | n/a              |
| 1, 2, 3   | to 0 by taking everything             | W    | take all of them |
| 4         | 3, 2, 1, which are all W              | L    | none             |
| 5         | to 4 (L)                              | W    | take 1           |
| 6         | to 4 (L)                              | W    | take 2           |
| 7         | to 4 (L)                              | W    | take 3           |
| 8         | 7, 6, 5, which are all W              | L    | none             |
| 9, 10, 11 | to 8 (L)                              | W    | take 1, 2, 3     |
| 12        | 11, 10, 9 which are all W             | L    | none             |

(b): Generalise the above by explaining who has the winning strategy in TAKE-3 starting from a pile of n coins for an arbitrary n.

>**Note**
>"Arbitrary n" means any number of coins
>"Generalise the above" means turn your table from 1(a) into a rule that works for every n.

The second player has the winning strategy if n is a multiple of 4.
Otherwise, the first player has the winning strategy.

If n is a multiple of 4, then whenever the first player takes x coins (x = 1, 2, or 3), the second player takes 4 – x coins (also 1, 2, or 3, so it's always allowed). Each round removes exactly 4 coins, so the pile stays on a multiple of 4 after each of the second player's moves. Eventually it reaches 0 straight after the second player's move, so the second player takes the last coin.

for example, say:
$n = 18$ – for the first player to win, they need to take 2 as their first move to have the winning strategy (make sure to leave the second player a multiple of 4)

or

$n=32$ – the second player wins. Whatever the first player takes leaves a number that isn't a multiple of 4, and the second player then takes enough to get back to one: 28..., then 24... and so on down to 0.

(c): Generalise the above further by explaining who has the winning strategy in TAKE-k starting from a pile of n coins for an arbitrary n, but where players may alternately remove between 1 and $k$ coins (above, we had $k=3$)

In TAKE-$k$, the second player has the winning strategy if $n$ is a multiple of $k + 1$. Otherwise, the first player has the winning strategy.

If n is a multiple of k + 1, then whenever the first player takes x coins ($1\leq x\leq k$), the second player takes (k + 1) - x coins. This is also between 1 and k, so it's always a legal move. Each round removes exactly k + 1 coins, so the pile is still a multiple of k + 1 after every one of the second player's moves. It eventually reaches 0 straight after the second player's move, so the second player takes the last coin. 

If n is not a multiple of k + 1, the first player takes n mod (k + 1) coins (the remainder when n is divided by k + 1). That leaves a multiple of k + 1, and the first player then uses the same strategy to win.

**Question 2:**
Starting with a single pile of coins, two players alternately remove either 1 or 3 or 8 coins. The player who takes the last coin wins.

(a): For each number n from 1 to 12, explain who has the winning strategy in TAKE-1-3-8 starting from a pile of n coins. In this case in which the first player has the winning strategy, state how many coins the first player should take.

| n   | Where can I move?                         | Type | Winning move     |
| --- | ----------------------------------------- | ---- | ---------------- |
| 0   | nowhere (opponent took the last coin)     | L    | none             |
| 1   | 0 (L)                                     | W    | take 1           |
| 2   | 1 (W) Can't take 3 or 8, not enough coins | L    | none             |
| 3   | 2 (L), 0 (L)                              | W    | take 1, or 3     |
| 4   | 3 (W), 1 (W)                              | L    | none             |
| 5   | 4 (L), 2 (L)                              | W    | take 1, or 3     |
| 6   | 5 (W), 3 (W)                              | L    | none             |
| 7   | 6 (L), 4 (L)                              | W    | take 1, or 3     |
| 8   | 0 (L), 5 (W), 7 (W)                       | W    | take 8           |
| 9   | 8 (W), 6 (L), 1 (W)                       | W    | take 3           |
| 10  | 9 (W), 7 (W), 2 (L)                       | W    | take 8           |
| 11  | 10 (W), 8 (W), 3 (W)                      | L    | none             |
| 12  | 11 (L), 9 (W), 4 (L)                      | W    | take 1 or take 8 |
The second player has the winning strategy when n = 2, 4, 6, or 11. For every other n from to 1 to 12, the first player has the winning strategy, using the winning move shown in the table.

(b): Argue that the second player has a winning strategy if, and only if, $n$ is of the form 11k or 11k+2 or 11k+4 11k+6 for some $k\in \mathbb{N}$

TODO: Will come back to this question 2b

----

**Question 3:**
Starting with a single pile of coins, two players alternate taking either 1 coin or half of the remaining coins, including the leftover coin if there is an odd number of coins remaining. Thus, for example, if there are 25 coins in the pile then a move consists of taking either 1 coin or 13 coins; if 13 coins are taken leaving 12 in the pile, then the next move will consist of taking either 1 coin or 6 coins. The player who takes the last coin wins.

(a): For each number $n$ from 1 to 12, explain who has the winning strategy in this game starting from a pile of $n$ coins. In the case in which the first player has the winning strategy, state how many coins the first player should take.


| n   | Where can I move?                 | Type | Winning Move  |
| --- | --------------------------------- | ---- | ------------- |
| 0   | nowhere (opponent took last coin) | L    | none          |
| 1   | 0 (L)                             | W    | take 1        |
| 2   | 1 (W)                             | L    | none          |
| 3   | 2 (L), 1 (W)                      | W    | take 1        |
| 4   | 3 (W), 2 (L)                      | W    | take half (2) |
| 5   | 4 (W), 2 (L)                      | W    | take half (3) |
| 6   | 5 (W), 3 (W)                      | L    | none          |
| 7   | 6 (L), 3 (W)                      | W    | take 1        |
| 8   | 7 (W), 4 (W)                      | L    | none          |
| 9   | 8 (L), 4 (W)                      | W    | take 1        |
| 10  | 9 (W), 5 (W)                      | L    | none          |
| 11  | 10 (L), 5 (W)                     | W    | take 1        |
| 12  | 11 (W), 6 (L)                     | W    | take half (6) |
Using the winning move shown in the table, the first player has the winning strategy when $n = 12, 11, 9, 7, 5, 4, 3, 1$, and the second player has the winning strategy when $n=10,8,6,2$. 

(b): Argue that the first player has a winning strategy in the game starting with $n$ coins if, and only if, the binary representation of $n$ is an even number of 0's.
Specifically,
- if the binary representation of $n$ ends in an even number of 0's, then either n=1 and you can win by taking the single coin, or there is a move which leaves a number of coins whose binary representation ends in an odd number of 0's, and,
- if the binary representation of $n$ ends in an odd number of 0's, then every move leaves a number of coins whose binary representation ends in an even number of 0's.

On every turn, whoever is moving wants to leave their opponent with an odd number of 0's on the end, because that's an L position for the opponent.

- $n$ has an odd number of 0's. The first player moves first, and an even count always has a move that leaves an odd count. So the first player leaves an odd count, the second player is forced to hand back an even count, and the first player leaves odd again, and so on. **The first player wins.**
- $n$ has an odd number of 0's. The first player moves first, but from an odd count every move leaves an even count. So the first player is forced to hand the second player an even count, and now the second player is the one leaving odd counts. **The second player wins.**

- Having an even number removes one 0 from the end of its binary form
	- (e.g. 12 = 1100 $\to$ 6 = 110)
- An even number minus 1 is odd, so it ends in 1 (in binary), which means zero 0's on the end.
- If $n$ is odd, taking half rounded up leaves ($n-1$)/2 which is $n-1$ with one 0 removed from its end.

| Case                                                                 | Reasoning                                                                                                                                                                                                                                                                                                                                             |
| -------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Case 1<br><br>$n$ ends in an odd number of 0's.<br>then $n$ is even. | taking 1 leaves $n-1$, which is odd, so it has zero 0's on the end (even). <br><br>taking half leaves $n/2$, which has one fewer 0 <br>(odd-1=even)                                                                                                                                                                                                   |
| Case 2<br><br>$n$ ends in an even number of 0's.                     | If $n=1$, take the coin and win.<br>If $n$ is even (2, 4, ... 0's on the end), take half. This leaves $n/2$ with one fewer , which is an odd number of 0's.<br>If $n$ is odd and n>1, suppose $n-1$ ends in t zeros. Taking 1 leaves n$-1$ (t zeros), and taking half leaves ($n-1$)/2 ($t-1$ zeros). One of t and $t-1$ is odd, so choose that move. |
If $n$ ends in an even number of 0's, the first player always moves to a position with an odd number of 0's. From there the second player can only return a position with an even number of 0's. The pile gets smaller every turn, so eventually the first player faces $n=1$ and takes the last coin. If $n$ ends in an odd number of 0's, the roles are swapped and the second player wins.

**Question 4**
**The setup.** There are two piles ($n, k$), with the bigger pile $n$ first, and the smaller pile $k$ second. On your turn you take $1xk, 2x, 3xk, ...$ coins from the **bigger** pile. If you empty a pile, you win.


| n   | Where can I move? | Type | Winning Move |
| --- | ----------------- | ---- | ------------ |
| 1   | (1, 1)            | W    | take one     |


