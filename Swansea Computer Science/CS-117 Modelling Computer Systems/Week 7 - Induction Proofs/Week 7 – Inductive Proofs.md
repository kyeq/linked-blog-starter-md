#CS117 

# Week 7 – Inductive Proofs (Lecture 12)
*Follow-along note for `12 - Inductive Proofs.pdf` (16 slides). Each heading = one slide, in order.*

> [!summary] The big idea in one line
> Prove it for the **start**, prove "**if it works for k, it works for k+1**" → it works for **everything**. Like dominoes: knock the first one over, and make sure each one knocks the next.

---

## Slide 1 – Induction Proofs (the principle)
To prove $\forall n \in \mathbb{N} : P(n)$ (i.e. $P(n)$ is true for every $n \geq 0$), it's enough to prove two things:

| Part | What you prove | Name |
|---|---|---|
| (a) | $P(0)$ | **Base case** |
| (b) | $\forall k \in \mathbb{N}\,\big(P(k) \to P(k+1)\big)$ | **Induction step** |

Why it works — it's a chain reaction:
- By (a), $P(0)$ is true.
- $P(0)$ true + (b) ⇒ $P(1)$ true.
- $P(1)$ true + (b) ⇒ $P(2)$ true.
- ... and so on forever.

**Vocab:** in step (b), the assumption $P(k)$ is called the **inductive hypothesis (IH)**. You *assume* it, then *use* it to show $P(k+1)$.

> [!tip] Template you can reuse for every proof
> 1. **"Proof: By induction on n."**
> 2. **Base case:** plug in the smallest value (usually $n=0$, sometimes $n=1$ or $n=8$...). Show both sides are equal / the claim holds.
> 3. **Induction step:** "Assume $P(k)$ for some $k$ (IH). We show $P(k+1)$."
> 4. Write out $P(k+1)$, **find the $P(k)$ bit hiding inside it**, replace it using the IH, then tidy the algebra.
> 5. End with ∎.

---

## Slide 2 – A First Proof by Induction
**Theorem:** $1 + 2 + \dots + n = \dfrac{n(n+1)}{2}$ for all $n \geq 0$.

**Base case ($n=0$):** the sum of nothing is $0$, and $\frac{0(0+1)}{2} = 0$. ✔

**Induction step:** assume (IH) $1 + 2 + \dots + k = \frac{k(k+1)}{2}$. Want: $1 + \dots + k + (k+1) = \frac{(k+1)(k+2)}{2}$.

$$
\underbrace{1 + 2 + \dots + k}_{\text{this is the IH bit}} + (k+1) = \frac{k(k+1)}{2} + (k+1)
$$

The algebra the slide skips:
$$
\frac{k(k+1)}{2} + \frac{2(k+1)}{2} = \frac{(k+1)(k+2)}{2} \quad \checkmark
$$
(factor out $(k+1)$: $\;(k+1)\cdot\frac{k+2}{2}$)  ∎

> [!note] The key move
> The braces under $1 + 2 + \dots + k$ on the slide are pointing out "this chunk is exactly what the IH talks about". **Always split off the last term** and you'll find the IH.

---

## Slide 3 – Induction via Contradiction
Same theorem, proved a different way — this is *why* induction is valid.

**Idea:** suppose the theorem is false somewhere. Then there's a **smallest** $n$ where it fails ("least counterexample"). So it's true for everything below $n$.

Argue by cases on the **structure** of $n$ (every natural number is either $0$ or $k+1$ for some $k$):
- **$n = 0$:** sum $= 0 = \frac{0(0+1)}{2}$ — so it *doesn't* fail at 0. **Contradiction!**
- **$n = k+1$:** $k < n$, so it holds for $k$ (because $n$ was the smallest failure). Then exactly the same algebra as slide 2 gives $\frac{(k+1)(k+2)}{2} = \frac{n(n+1)}{2}$ — so it *doesn't* fail at $n$. **Contradiction!**

So there is no smallest failure ⇒ no failure at all. ∎

> [!info] Takeaway
> "Induction" = "there can't be a first counterexample". Same proof, just phrased backwards. Notice the two cases ($0$ / $k+1$) are just the **base clause** and **inductive clause** of how $\mathbb{N}$ was defined last week (Week 6).

---

## Slide 4 – Another Proof by Induction (sum of squares)
**Theorem:** $1^2 + 2^2 + \dots + n^2 = \dfrac{n(n+1)(2n+1)}{6}$ for all $n \geq 0$.

**Base case ($n=0$):** $0 = \frac{0 \cdot 1 \cdot 1}{6}$ ✔

**Induction step:** IH: $1^2 + \dots + k^2 = \frac{k(k+1)(2k+1)}{6}$. Want: $\frac{(k+1)(k+2)(2k+3)}{6}$.

$$
\underbrace{1^2 + \dots + k^2}_{\text{IH}} + (k+1)^2 = \frac{k(k+1)(2k+1)}{6} + (k+1)^2
$$

The algebra the slide skips (factor out $(k+1)$):
$$
= \frac{(k+1)\big[k(2k+1) + 6(k+1)\big]}{6} = \frac{(k+1)(2k^2 + 7k + 6)}{6} = \frac{(k+1)(k+2)(2k+3)}{6} \quad \checkmark
$$
(check: $(k+2)(2k+3) = 2k^2 + 3k + 4k + 6 = 2k^2 + 7k + 6$)  ∎

> [!tip] Algebra trick
> When stuck, **factor out the common bracket** (here $(k+1)$) first, then expand only what's left. You already know what the target looks like, so work towards it.

---

## Slide 5 – $6^n + 4$ is divisible by 10
**Theorem:** $6^n + 4$ is divisible by 10 for every integer $n > 0$.

⚠️ Note the base case is **$n = 1$** here (the claim starts at $n>0$; at $n=0$ you'd get $5$, not divisible by 10).

**Base case ($n=1$):** $6^1 + 4 = 10$ ✔

**Induction step:** IH: $6^k + 4 = 10m$ for some integer $m$. Want: $6^{k+1} + 4$ divisible by 10.

$$
\begin{aligned}
6^{k+1} + 4 &= 6 \cdot 6^k + 4 \\
&= 6(6^k + 4) - 20 \quad \text{(add 24, take 24, i.e. } 6\cdot4 = 24,\; 24 - 20 = 4\text{)} \\
&= 6(10m) - 20 \quad \text{(IH)} \\
&= 10(6m - 2)
\end{aligned}
$$
That's 10 × an integer ⇒ divisible by 10. ∎

> [!tip] Divisibility trick
> "Divisible by 10" means "$= 10 \times$ some integer". Write the IH as an **equation with a new variable** ($10m$), then **force the IH expression to appear** by adding/subtracting what you need.

---

## Slide 6 – A Fact About Fibonacci Numbers
Recall: $f_0 = 0,\ f_1 = 1,\ f_n = f_{n-1} + f_{n-2}$. (So $0, 1, 1, 2, 3, 5, 8, 13, \dots$)

**Theorem:** $f_1 + f_2 + \dots + f_n = f_{n+2} - 1$ for all $n \geq 0$.

Sanity check $n=4$: $1+1+2+3 = 7$ and $f_6 - 1 = 8 - 1 = 7$ ✔

**Base case ($n=0$):** empty sum $= 0 = 1 - 1 = f_2 - 1$ ✔

**Induction step:** IH: true for $n = k$.
$$
\begin{aligned}
f_1 + \dots + f_{k+1} &= (f_1 + \dots + f_k) + f_{k+1} \\
&= (f_{k+2} - 1) + f_{k+1} \quad \text{(IH)} \\
&= (f_{k+2} + f_{k+1}) - 1 = f_{k+3} - 1 \quad \text{(Fibonacci definition)}
\end{aligned}
$$
∎

> [!note] Pattern
> Split off last term → IH → **use the recursive definition** to tidy up. This is very common: the definition of the sequence is your algebra tool.

---

## Slide 7 – A Fact About Harmonic Numbers
Recall: $H_0 = 0,\ H_n = H_{n-1} + \frac{1}{n}$. (So $H_n = 1 + \frac12 + \frac13 + \dots + \frac1n$.)

**Theorem:** $H_1 + H_2 + \dots + H_n = (n+1)H_n - n$ for all $n \geq 0$.

**Base case ($n=0$):** $0 = (0+1)H_0 - 0 = 0$ ✔

**Induction step:**
$$
\begin{aligned}
H_1 + \dots + H_k + H_{k+1} &= \big((k+1)H_k - k\big) + H_{k+1} \quad \text{(IH)}
\end{aligned}
$$
Now replace $H_k$ using the definition backwards: $H_k = H_{k+1} - \frac{1}{k+1}$:
$$
\begin{aligned}
&= (k+1)\Big(H_{k+1} - \tfrac{1}{k+1}\Big) - k + H_{k+1} \\
&= (k+1)H_{k+1} - 1 - k + H_{k+1} \\
&= (k+2)H_{k+1} - (k+1) \quad \checkmark
\end{aligned}
$$
which is exactly the formula with $n = k+1$. ∎

> [!tip] The trick here
> Everything has to end up in terms of $H_{k+1}$, so **rewrite $H_k$ in terms of $H_{k+1}$**. The $(k+1)\cdot\frac{1}{k+1}$ cancels nicely to $1$.

---

## Slide 8 – Sizes of Power Sets
**Theorem:** if $A$ is a finite set with $n$ elements, then $|\mathcal{P}(A)| = 2^n$.

This is induction where $P(n)$ is about **sets**, not a formula.

**Base case ($n=0$):** $A = \emptyset$, $\mathcal{P}(\emptyset) = \{\emptyset\}$ which has $1 = 2^0$ element ✔

**Induction step:** IH: any set with $k$ elements has $2^k$ subsets.
- Take any $A$ with $k+1$ elements. Pick one element $x \in A$.
- $B = A \setminus \{x\}$ has $k$ elements ⇒ by IH, $B$ has $2^k$ subsets.
- Every subset of $A$ either:
  - **doesn't contain $x$** → it's a subset of $B$: $2^k$ of these
  - **does contain $x$** → it's (a subset of $B$) $\cup \{x\}$: another $2^k$
- Total: $2^k + 2^k = 2^{k+1}$ ✔ ∎

Example: $A = \{1,2\}$, $x = 2$, $B = \{1\}$. Without 2: $\emptyset, \{1\}$. With 2: $\{2\}, \{1,2\}$. Total $4 = 2^2$. (Links to the Finite Powersets slide from Week 6.)

---

## Slide 9 – Strong Induction
**Normal induction:** assume $P(k)$, prove $P(k+1)$ — you only get the **one** step before.
**Strong induction:** to prove $P(n)$, you may assume $P(k)$ for **every** $k < n$ — you get **all** previous steps.

Use it when the step needs to jump back further than 1 (e.g. to $n/2$).

**Example:**
$$
f(n) = \begin{cases} 0 & \text{if } n = 0 \\ 2 \cdot f(n/2) & \text{if } n > 0 \text{ even} \\ f(n-1) + 1 & \text{if } n \text{ odd} \end{cases}
$$

**Theorem:** $f(n) = n$ for every $n \geq 0$.

**Proof:** strong induction on $n$, cases on the structure of $n$:
- $n = 0$: $f(0) = 0$ ✔
- $n > 0$ even: $f(n) = 2 \cdot f(n/2) = 2 \cdot \frac{n}{2} = n$ — uses IH on $n/2$, which is $< n$ but **not** $n-1$ → needs *strong* induction.
- $n$ odd: $f(n) = f(n-1) + 1 = (n-1) + 1 = n$ ✔ ∎

Quick check: $f(6) = 2f(3) = 2(f(2)+1) = 2(2f(1)+1) = 2(2(f(0)+1)+1) = 2(2\cdot1+1) = 6$ ✔

> [!note] Notice
> Strong induction has **no separate base case written out** — the $n=0$ case just happens to be one where you don't need the IH. You still have to handle it!

---

## Slide 10 – Fundamental Theorem of Arithmetic
**Theorem:** every integer $n > 1$ is either prime or a product of primes.

**Proof (strong induction):** assume every $k$ with $1 < k < n$ is prime or a product of primes.
- If $n$ is prime → done.
- If not, $n = ab$ with $1 < a < n$ and $1 < b < n$.
- By IH, $a$ and $b$ are each prime or products of primes.
- So $n = ab$ is a product of primes. ∎

Example: $60 = 6 \times 10$; $6 = 2\times3$, $10 = 2\times5$ ⇒ $60 = 2\cdot3\cdot2\cdot5$.

> [!info] Why strong?
> $a$ and $b$ could be anything below $n$ — e.g. $n = 60$ needs $6$ and $10$, not $59$. Normal induction (only $n-1$) is useless here.

---

## Slide 11 – Induction over Words
Back to Week 6's inductive definitions! Words over $\{a,b\}$:
$$w ::= \varepsilon \mid aw \mid bw$$
A word is the empty word $\varepsilon$, or $a$ followed by a smaller word, or $b$ followed by a smaller word.

Length: $\text{length}(\varepsilon) = 0$, $\text{length}(as) = 1 + \text{length}(s)$, $\text{length}(bs) = 1 + \text{length}(s)$.

**Theorem:** $aw \neq wb$ for all words $w$.
(In words: sticking $a$ on the front never gives the same thing as sticking $b$ on the end.)

**Proof: by induction on the structure of $w$** — one case per clause of the definition:
- **$w = \varepsilon$:** $aw = a$, $wb = b$, and $a \neq b$ ✔
- **$w = as$:** IH: $as \neq sb$. Then $a(as) \neq a(sb)$ (same first letter, rest differ). So $aw = aas \neq asb = wb$ ✔
- **$w = bs$:** $aw = abs$ starts with **a**, $wb = bsb$ starts with **b** ⇒ different. ✔ (didn't even need the IH!) ∎

> [!tip] Structural induction recipe
> **One case per constructor** in the definition ($\varepsilon$, $a\_$, $b\_$). Base constructors = base cases. Constructors with a smaller piece inside = you get the IH for that smaller piece.

---

## Slide 12 – Induction over Trees
Binary trees: $t ::= \text{leaf} \mid N(t_1, t_2)$
A tree is a leaf, or an internal node with two smaller subtrees.

**Theorem:** every tree has exactly **one more leaf than internal nodes**. (leaves = nodes + 1)

**Proof: by induction on the structure of $t$:**
- **$t = $ leaf:** 1 leaf, 0 nodes ✔ ($1 = 0 + 1$)
- **$t = N(t_1, t_2)$:** by IH, $t_1$ has $n_1$ nodes and $n_1 + 1$ leaves; $t_2$ has $n_2$ nodes and $n_2 + 1$ leaves.
  - Nodes of $t$: $n_1 + n_2 + 1$ (the $+1$ is the new root $N$)
  - Leaves of $t$: $(n_1+1) + (n_2+1) = (n_1 + n_2 + 1) + 1$ ✔ ∎

```
        N          ← 1 new node
       / \
     t1   t2       ← leaves just add up
```

---

## Slide 13 – A Proof About Postage Stamps
**Theorem:** any postage of **at least 8p** can be made from only 3p and 5p stamps.

**Base case ($n=8$):** $3 + 5 = 8$ ✔

**Induction step:** assume we have stamps making $n \geq 8$ pence. Make $n+1$:
- **If there's a 5p stamp:** swap it for two 3p ($-5 + 6 = +1$) ✔
- **If there's no 5p stamp:** it's all 3p's, and since $n \geq 8$ there must be **at least three** of them (two 3p's is only 6p). Swap three 3p for two 5p ($-9 + 10 = +1$) ✔

Either way we get $n+1$. ∎

Examples: $8 = 3+5$ → $9 = 3+3+3$ → $10 = 5+5$ → $11 = 5+3+3$ → $12 = 3+3+3+3$ ...

> [!note] Things to notice
> - Base case doesn't have to be 0 — here it's **8** (7p is impossible: try it).
> - The step is a **case split** — very common. Make sure your cases cover everything.

---

## Slide 14 – A Proof About Playing Boards (L-tromino tiling)
**Setup:** a $2^n \times 2^n$ board, one square is black (anywhere), the other $4^n - 1$ are white. Tiles are **L-shapes** (a $2\times2$ block with one corner missing = 3 squares).

**Theorem:** you can always tile all the white squares exactly, leaving the black one uncovered.

**Base case ($n=0$):** $1\times1$ board = just the black square → 0 tiles needed ✔

**Induction step:** board is $2^n \times 2^n$.
1. Split it into **four quadrants**, each $2^{n-1} \times 2^{n-1}$.
2. The black square is in exactly one quadrant.
3. Put one L-tile in the **centre**, with its **gap pointing into the black square's quadrant** — so it covers one centre-corner square of each of the **other three** quadrants.
4. Now **every** quadrant has exactly one square that's "taken" (the real black one, or one covered by the centre tile) — treat each as that quadrant's "black square".
5. By IH, each quadrant can be tiled. ∎

```
+-----+-----+
|  ■  |     |
|     |  X  |      X = squares covered by the centre L-tile
+-----+-----+      (gap is in the top-left quadrant, where ■ is)
|  X  |  X  |
|     |     |
+-----+-----+
```
(sanity: $4^n - 1$ is always divisible by 3, so the counting works out)

---

## Slide 15 – A Non-Proof About Sums ❓
**"Non-Theorem":** $1 + 2 + \dots + n = \dfrac{(n-1)(n+2)}{2}$

**"Non-Proof":** the induction step on the slide actually works:
$$
\frac{(k-1)(k+2)}{2} + (k+1) = \frac{k^2 + k - 2 + 2k + 2}{2} = \frac{k(k+3)}{2} = \frac{\big((k+1)-1\big)\big((k+1)+2\big)}{2} \checkmark
$$

**Question: what's wrong?**

> [!warning]- Answer (click to reveal)
> **There's no base case — and the base case is false!**
> $n = 0$: LHS $= 0$, RHS $= \frac{(-1)(2)}{2} = -1$. ✘
> $n = 1$: LHS $= 1$, RHS $= \frac{0 \cdot 3}{2} = 0$. ✘
> The step "if true for $k$ then true for $k+1$" is valid, but it never gets started — no first domino falls. (In fact this formula is the real one minus 1, so it's wrong for every $n$.)
> **Lesson: never skip the base case.**

---

## Slide 16 – A Non-Proof About People ❓
**"Non-Theorem":** all people are the same age.

**"Non-Proof":** (strong) induction on $n$ = size of a set $S$ of people.
- Base: $S = \emptyset$ — trivially true.
- Step: split $S$ into two **overlapping** smaller sets $S'$ and $S''$ ($S = S' \cup S''$, $S' \cap S'' \neq \emptyset$). By IH, everyone in $S'$ is the same age, everyone in $S''$ is the same age. They share someone ⇒ everyone in $S$ is the same age.

**Question: what's wrong?**

> [!warning]- Answer (click to reveal)
> **The induction step doesn't work for every $n$ — it breaks at $n = 2$.**
> To use the IH, $S'$ and $S''$ must both be **smaller** than $S$ *and* **overlap**.
> - $n = 1$: fine (one person is trivially the same age as themself).
> - $n = 2$, $S = \{\text{Alice}, \text{Bob}\}$: the only smaller sets that cover $S$ are $\{\text{Alice}\}$ and $\{\text{Bob}\}$ — they **don't overlap**. So you can't conclude anything. The chain of dominoes breaks between 1 and 2.
>
> **Lesson:** the induction step must hold for **every** $k$, including the small ones. Always test your step on the smallest cases.

---

## Summary / Exam Cheat Sheet

| Type | Assume | Prove | Use when |
|---|---|---|---|
| **Ordinary (weak) induction** | $P(k)$ | $P(k+1)$ | formula with $n$; step only needs the previous one |
| **Strong induction** | $P(j)$ for **all** $j < n$ | $P(n)$ | step jumps back further ($n/2$, factors $a,b$...) |
| **Structural induction** | property for the **smaller pieces** | property for the bigger thing | inductively defined data: words, trees, lists (Week 6) |

**Checklist for every proof:**
- [ ] Said what you're inducting on ("by induction on $n$" / "on the structure of $w$")
- [ ] Base case — right starting value (0? 1? 8?) and actually checked
- [ ] Clearly stated the IH
- [ ] Clearly stated what you're trying to show ($P(k+1)$)
- [ ] Pointed out *where* the IH is used ("by the inductive hypothesis")
- [ ] Step works for **all** $k$ (no gaps like the people example)
- [ ] ∎

**Common tricks:** split off the last term · factor out a common bracket · use the sequence's own definition (Fibonacci/harmonic) · add-and-subtract to make the IH appear (divisibility) · case split (stamps).

**Links:** [[Week 6]] (inductively defined sets — this week proves things about them) · [[Week 1 & 2 – Propositional Logic]] ($\to$, $\forall$)
