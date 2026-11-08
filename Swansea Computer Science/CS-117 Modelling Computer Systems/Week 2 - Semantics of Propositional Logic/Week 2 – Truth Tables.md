#### What is a truth table?
A truth table lists every possible combination of true/false values for your inputs,  and shows what the expression gives for each one.
**T/F and 1/0 mean the same thing.**

**The core operators**
$\begin{array}{cc|cccccc} P & Q & \neg P & P \land Q & P \lor Q & P \oplus Q & P \rightarrow Q & P \leftrightarrow Q \\ \hline T & T & F & T & T & F & T & T \\ T & F & F & F & T & T & F & F \\ F & T & T & F & T & T & T & F \\ F & F & T & F & F & F & T & T \\ \end{array}$


> [!NOTE] Easy ways to remember
> - **NOT** ($\neg$): flips the value.
> - **AND** ($\land$): true only when both inputs are true.
> - **OR** ($\lor$): true when at least one is true.
> - **XOR** ($\oplus$): true when they're different.
> - **IFF** ($\leftrightarrow$): true when they're the same.
> - **IMPLIES** ($\rightarrow$): false only when $T \rightarrow F$ (PROMISE)


with *n* variables, you need $2^n$ rows:
- 2 variables give 4 rows
- 3 variables give 8 rows


