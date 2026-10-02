#CS117 

### Data Representation
Data representation is the process of presenting information in a meaningful way, allowing for easy understanding

#### Why care about data representation?
**4th June, 1996:** Ariana 5 explodes 37 seconds after launch, destroying $370M of rocket and satellites.

#### Types of data representation
1. Textual: Representing data using words, sentences, paragraphs
2. Numerical: Representing data through numbers or mathematical values
3. Visual: Representing data using graphs, charts, maps, diagrams
4. Mutimedia

#### Numbers
- Natural numbers: The counting numbers achieved by adding 1 (1, 2, 3...)
- Whole numbers: The natural numbers AND zero (also called non-negative integers)
- Integers: The whole numbers and negative Natural Numbers (-4, -3, -2, -1, 0, 1, 2, 3)
- Rational numbers: Integer, or a quotient of an integer and a non-zero integer
- Real numbers: All "non-imaginary" numbers

when writing numbers, we use digits (0, 1, 2, 3, ... 9) and the number of digits available to us define the **base** of the number we are representing

- Base 2: {0, 1} binary
- Base 3: {0, 1, 2}
- ...
- Base 10 {0, 1, 2 ... 9} (decimal)
- ...
- Base 16 {0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F} (hexadecimal)

#### Writing numbers
To avoid ambiguity, we can state the base a number is in.
"is 357" in base 8? 10? 16?

We write number in brackets (sometimes) and include the base in the subscript.

**Bigger numbers?**
If we only have 10 digits, how do we write larger decimal numbers?

In decimal, for any number greater than 9, we need to use multiple digits...

#### Why is it important to convert number bases?
- Human readability
- Programming and Input/Output

**Convert (2A5) 16** to decimal

Bases:
- 2 – Binary: 0, 1
- 10 – Decimal: 0-9
- 16 – Hexadecimal: 0-9 + A-F (10-15)

2 x 16 ^ 2 = 512
10 x 16 ^ 1 = 160
5 x 16 ^ 0 = 5

512 + 160 + 5 = 677 (10)

#### Convert from base *b* to decimal

Convert (239)10 to base 8:
(239)10 / 8 = 29.875

Quotient = 29
Remainder = 0.875 x 8 (base) = 7

Convert (239)10 to base 16 (hex):

(239)10 / 16 = 14 remainder 15 (F)
14 / 16 = 0, remainder 14 (E)

= (EF)16
