#CS117 

#### One-To-One Functions
A one-to-one function (also called **injective**) is a function that ==never gives the same output to two different inputs==. Every output value is “used” by at most one input.

A function f: A → B sends each element of A to one element of B.
Normally, two different inputs are allowed to land on the same output.
A one-to-one function forbids that: no two inputs share an output.

[![One to One Function - GeeksforGeeks|380](https://media.geeksforgeeks.org/wp-content/uploads/20231003072114/One-to-one-function-1.png)](https://www.google.com/url?sa=t&source=web&rct=j&url=https%3A%2F%2Fwww.geeksforgeeks.org%2Fmaths%2Fone-to-one-functions%2F&ved=0CBcQjRxqFwoTCIiC2M7xypcDFQAAAAAdAAAAABA4&opi=89978449)


#### Onto Functions
An onto function (also called **surjective**) is a function that hits every element of the codomain. Nothing on the right-hand side is left out.

The **codomain** is the set B in f: A → B.

For f: A → B, the set B is the codomain. A function is onto if every b ∈ B receives at least one arrow. No element of B is “unused.”

**The formal definition**
For all b ∈ B, there exists a ∈ A such that f(a) = b.

In other words, whatever target value you pick in B, you can find some input in A that maps to it.

**How it differs from one-to-one**

- **One-to-one:** no output is hit by _more than one_ arrow (no sharing).
- **Onto:** no output is hit by _zero_ arrows (nothing missed).

These are independent properties. A function can have one, both, or neither.

#### Bijective Functions
A **bijective** function is one that is both one-to-one (injective) and onto (surjective). It pairs up the elements of A and B perfectly: every element of B is hit by **exactly one** element of A.

*Remember:*
- One-to-one means no output is shared.
- Onto means no output is missed.
- Bijective means both: each element of B gets exactly one arrow.

f: A → B is bijective if:

1. For all a, a′ ∈ A, if a ≠ a′ then f(a) ≠ f(a′) (injective)
2. For all b ∈ B, there exists a ∈ A with f(a) = b (surjective)

Equivalently: for every b ∈ B, there is **exactly one** a ∈ A with f(a) = b.

#### Properties of Composed Functions: Chaining two functions
**Composition**: chaining two functions so the output of the first becomes the input of the second. It then says that one-to-one, onto and bijective all “survive” composition.

**What composition means**
Given f: A → B and g: B → C, the composed function g ∘ f: A → C is defined by

(g ∘ f)(a) = g(f(a))

You apply f first, then g. In the diagram, a goes to b = f(a), and then b goes to c = g(b) = g(f(a)). The long arrow on top is the shortcut from a straight to c.

Note the order: g ∘ f means “f first, then g”, which reads right to left.

![[Screenshot 2026-10-21 at 11.29.43.png|448]]

**The three rules**

1. If f and g are both one-to-one, then g ∘ f is one-to-one.
2. If f and g are both onto, then g ∘ f is onto.
3. If f and g are both bijective, then g ∘ f is bijective.

Rule 3 follows directly from rules 1 and 2, since bijective means one-to-one and onto.