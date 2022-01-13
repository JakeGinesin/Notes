[hackmd](https://hackmd.io/vHSSzIcnTKGHXkRC7Mza_A)

###### tags: `CS1800 - Discrete Structures`

# Discrete Structures Textbook Notes - Computers and Computing: Numbers, Circuits, and Logic

> This is part 1/6 of notes from [this](https://ccs.neu.edu/home/ntuck/courses/2015/05/cs1800/cs1800_text.pdf) textbook

## Number Representations

- We use a base ten system, therefore we represent numbers with: (0, 1, 2, 3, 4, 5, 6, 7, 8, 9)
- If we don't allow leading zeros, every non-negatie integer has a unique represntation as a finite sequence of numbers
- It's natural to us because we have 10 fingers and we grew up with it :O

$$
\sum^n_{k=0}d_k \cdot 10^k
$$

### Theory 1:

Let *b* be an integer greater than 1. If *n* is a positive integer, *n* can be expressed uniquely in the form:

$$
n = a_k \cdot b^k + a_{k-1} \cdot b^{k-1} + . . . + a_1 \cdot b^1 + a_0 \cdot b^0
$$

where k is a nonnegative integer, a_0, a_1, ..., a_k are non negatie integers less than b and a_k /= 0

### Examples for Theory 1:

> Example 1

$$
201_3 = 2 \cdot 3^2 + 0 \cdot 3^1 + 1 \cdot 3^0
\\
= 2 \cdot 9 + 0 \cdot 3 + 1 \cdot 1
\\
= 19_{10}
$$

> Example 2

$$
201_5 = 2 \cdot 5^2 + 0 \cdot 5^1 + 1 \cdot 5^0
\\
= 2 \cdot 25 + 0 \cdot 5 + 1 \cdot 1
\\
= 51_{10}
$$

> Example 3

$$
201_7 = 2 \cdot 7^2 + 0 \cdot 7^1 + 1 \cdot 7^0
\\
= 2 \cdot 49 + 0 \cdot 7 + 1 \cdot 1
\\
= 100_{10}
$$

*Conclusion:* we use base 10 in our every day lives, but we must also understand that computers use binary (base 2) and hexidecimal (base 16) representations

~~octal (base 8) is rarely used, huge L~~

### Binary Representation

In binary representation (base 2), the integers (a_k, a_{k-1},...,a_1,a_0) must be non-negative and less than 2. This leaves us with only two choices: 0, and 1. We are still able to express any positive integer with base 10 with this tho.

### Binary Representation Examples:

> Example 1

$$
(10010)_2 = 1 \cdot 2^4 + 0 \cdot 2^3 + 0 \cdot 2^2 + 1 \cdot 2^1 + 0 \cdot 2^0
\\
= 1 \cdot 16 + 0 \cdot 8 + 0 \cdot 4 + 1 \cdot 2 = 0 \cdot 1
\\
= 18_{10}
$$

> Example 2

$$
(1010011)_2 = 1 \cdot 2^6 + 0 \cdot 2^5 + 1 \cdot 2^4 + 0 \cdot 2^3 + 0 \cdot 2^2 + 1 \cdot 2^1 + 1 \cdot 2^0
\\
= 1 \cdot 64 + 0 \cdot 32 + 1 \cdot 16 + 0 \cdot 8 + 0 \cdot 4 + 1 \cdot 2 + 1 \cdot 1
\\
= 83_{10}
$$

### Simple Binary Arithmetic
When we were in like first grade we added stuff up through this process:

$$
\begin{array}{crrrr}&_1 & & _1\\& 3 & 5 & 3 & 7 \\ + & 1 & 9 & 3 & 6\\  \hline & 5 & 4 & 7 & 3 \end{array}
$$

You add the numbers from right to left, then carry the one if you need to. 

This same algorithm actually applies to binary :o

### Binary Addition Example:

$$
\begin{array}{crrrrrr}_1 & _1 & & _1 & _1 & _1\\& 1 & 1 & 0 & 1 & 0 & 1 \\+& & 1 & 0 & 1 & 1 & 1\\
\hline 1 & 0 & 0 & 1 & 1 & 0 & 0
\end{array} 
\iff
\begin{array}{crrr}\\& 5 & 3 \\+ & 2 & 3 \\ \hline & 7 & 6
\end{array}
$$

### Binary Subtraction Arithmatic

The subtraction algorithm from elementary can also be applied to binary numbers :o we go from right to left subtracting nums. If we can't, we "borrow" from the didget on the left

$$
\begin{array}{crrrrrr}& & _7 & _9 & & _4\\& 3 & 8 & ^10 & ^12 & 5 & ^13 \\-& & 5 & 4 & 3 & 2 & 9 \\ \hline & 3 & 2 & 5 & 9 & 2 & 4\end{array}
$$

### Binary Subtraction Example

$$
\begin{array}{crrrrrr}& & ^10 & 1 & ^10\\& 1 & 1 & ^10 & 1 & ^10 & 1
\\ - & & 1 & 0 & 1 & 1 & 1
\\ \hline & & 1 & 1 & 1 & 1 & 0
\end{array}
\iff
\begin{array}{crrr}\\& 5 & 3 \\ - & 2 & 3 \\ \hline & 3 & 0
\end{array}
$$

### Binary Multiplication
For the multiplication algorithm in standard decimal, take the example `312 x 2013`. For this example, we'd multiply 312 by each of the digits of 2013. Each successive product is placed one space to the left of the prvious product (to account for the extra power of 10). 

Binary Multiplication is much easier since we're only working with 0 and 1. 

### Binary Multiplication Examples

> Regular multiplication

$$
\begin{array}{crrrrrrr}
&&&&& 3 & 1 & 2 \\
\times & & &&  2 & 0 & 1 & 3 \\
\hline & & & & & 9 & 3 & 6 \\
& & & & 3 & 1 & 2 \\
& & 6 & 2 & 4 & 0 \\
\hline
& & 6 & 2 & 8 & 0 & 5 & 6
\end{array}
$$

> Binary Multiplication

$$
\begin{array}{crrrrrr}
& & & & & 1 & 1 & 1 \\
\times & & & & 1 & 0 & 1 & 1 \\
\hline  & & & & & 1 & 1 & 0 \\
& & & & 1 & 1 & 0 \\
& & 1 & 1 & 0 & 0 \\
\hline & 1 & 0 & 0 & 0 & 0 & 1 & 0
\end{array}
$$

### Multiplication and Division by 2
When we multiply an integer in base 10 by 10, all we have to do is add a zero to the right side of the integer's decimal representation

$$
10 \times 3436 = 34360
$$

This follows from the meaning of the decimal representation:

$$
10 \times 3257 = 3 \cdot 10^4 + 2 \cdot 10^3 + 5 \cdot 10^2 + 7 \cdot 10^1 = 32570
$$

Inversely, if a decimal integer ends in zero, we can easily divide the integer by simply removing the 0.

**Binary Doe..**

In binary, we can multiply or devide a number by two by adding or removing a zero from the left

### Bytes

P much all digital data is stored in binary. A *byte* is an 8-bit binary number with leading zeros allowed. 

There are 256 different "bytes" and they represent the integers form 0 (00000000) to 255 (11111111).

Bytes are commonly used to represent characters. *ASCII* uses the 7-bits of a byte, 0 to 127, to represent letters and shit. 

Extending on that, Unicode is an international standard intended to encode all characters in all languages as well as mathematical and special characters. 

~~UTF-32, also called UCS-4, uses 4 bytes to encode Unicode characters, but no one cares lol~~

### Hexadecimal Representation

"Hexadecimal" is a combo of the greek *hexa* (meaning six) and the english word *decimal*

Since ppl don't give enough of a crap to say the full "hexadecimal," people usually just shorten it to *hex*

In order to represent hexidecimal, we use 0-9 and A-F to represent 0-15 respectively. 

A byte can be represented by two hex-digits instead of 8 bits 

### Hexadecimal Representation Example: 

$$
A2_{16} = 10 \cdot 16^1 + 2 \cdot 16^0
\\
= 162_{10}
\\
$$

### Converting Between Decimal and Binary

How do we convert a decimal integer to its binary equivilent? 

We use the following algorithm:

$$
39 = 19 \cdot 2 + 1
\\
19 = 9 \cdot 2 + 1
\\
9 = 4 \cdot 2 + 1
\\
4 = 2 \cdot 2 + 0
\\
2 = 1 \cdot 2 + 0
\\
1 = 0 \cdot 2 + 1
$$

So, we see thatb 39_{10} = (100111)_2

Though we can use this method to convert from base 10 to any base (in this case 8!)

$$$
143_{10} = 18 \cdot 8 + 7 \\
17 = 2 \cdot 8 + 1 \\
2 = 0 \cdot 8 + 2 
$$

So, 143_{10} = 217_{8}

### Representing Negative Numbers: Two's Complement

How do we turn negative numbers into binary? :O 

There's actually a standard for converting, and it's called two's complement. Literally all you do is flip all of the bits and add one

$$
15 \Rightarrow 00001111
\\
-15 \Rightarrow 00001111 \Rightarrow 11110000 \Rightarrow 11110001
\\
\\
28 \Rightarrow 00011100
\\
-28 \Rightarrow 00011100 \Rightarrow 11100011 
\Rightarrow 11100100
$$

some more information: http://en.wikipedia.org/wiki/Two's_complement

## Circuits

Woah wow we're onto circuits! As some background, the modern day CPUs are constructed from digital circuits, which are in turn constructed by logic gates, which are *in turn* constructed from transistors. In this chapter, we examine how digital circuits are constructed from logic gates. 

In the next chapter, we'll understand the mathematical underpins of these circuits, *boolean algebra*

### Transistors and Switches
Transistors are in effect, digital switches. They're either used to break or establish an electrical connection, much in the same way light switches are kinda on and off. 

Below, the left switch is "normally open," thereby allowing the electricity to flow freely.

The right, conversely, is "normally closed." This breaks the electrical conneciton

![](https://i.imgur.com/EcWLqV1.png)

### Basic Logic Gates: AND, OR, NOT

Switches can be wired together to form basic *logic gates* which are used to construct circuits which can manipulate nubers

#### And Gate:

Both switches are not "pushed" in for the electricity to flow!. 

![](https://i.imgur.com/BUlx78o.png) 

You need both to be not pushed in for the electricity to flow :D wow so innovative

being pushed in or not can be represented by a 1 or a 0, so in effect you can create a "truth table" that demonstrates their relationship:

$$
\begin{array}{rr|r}
A & B & A \space and \space B
\\ \hline 0 & 0 & 0
\\ 0 & 1 & 0
\\ 1 & 0 & 0
\\ 1 & 1 & 1
\end{array}
$$

#### OR gate:

an OR gate takes two inputs and is "on" so long as at least one of the inputs is "on"

![](https://i.imgur.com/pReKtVa.png)


Truth Table:
$$
\begin{array}{rr|r}
A & B & A \space and \space B
\\ \hline 0 & 0 & 0
\\ 0 & 1 & 1
\\ 1 & 0 & 1
\\ 1 & 1 & 1
\end{array}
$$

#### NOT gate

The NOT gate, unlike the other gates above, has only one input. Its output is simply the opposite of its input :O

![](https://i.imgur.com/hAP89BF.png)

Truth Table:
$$
\begin{array}{r|r}
A & A \space and \space B
\\ \hline 0 & 1
\\ 1 & 0 
\end{array}
$$

### Other Logic Gates: NAND, NOR, XOR, XNOR

In the next chapter, we'll learn that every conceivable truth table and its corresponding logic gate can be built from AND, OR, and NOT gates.

However, these gates are so common that they have their own annotation. They're certainly worth mentioning.

#### NAND Gate

The NAND gate is simply the opposite of an AND gate. It's only turned on if it's *not* the case both the inputs are true

![](https://i.imgur.com/drl5E7c.png)

Truth Table:
$$
\begin{array}{rr|r}
A & B & A \space and \space B
\\ \hline 0 & 0 & 1
\\ 0 & 1 & 1
\\ 1 & 0 & 1
\\ 1 & 1 & 0
\end{array}
$$

#### NOR Gate

The NOR gate is the opposite of the OR gate :O how crazy! It only turns on if both outputs are both off 

![](https://i.imgur.com/PvawC0p.png)

Truth Table:
$$
\begin{array}{rr|r}
A & B & A \space and \space B
\\ \hline 0 & 0 & 1
\\ 0 & 1 & 0
\\ 1 & 0 & 0
\\ 1 & 1 & 0
\end{array}
$$

#### XOR gate
This mf only turns on if and only if one input is 1, but not both. 

![](https://i.imgur.com/h4yi8bg.png)

Truth Table:
$$
\begin{array}{rr|r}
A & B & A \space and \space B
\\ \hline 0 & 0 & 0
\\ 0 & 1 & 1
\\ 1 & 0 & 1
\\ 1 & 1 & 0
\end{array}
$$

This gate in particular is very important. you can use it to build adders and shit. I really don't know too much about adders, but I'll certianly learn eventually.

#### XNOR Gate
The XNOR gate is the "exclusive NOR" gate. It's the opposite of the XOR gate. It's constructed by a XNOR gate followed by a NOT gate.

### Binary Arithmetic: Ripple Carry Adders

In order to perform the addition of two binary numbers, one must in each column sum the corresponding bits from each input number together, producing an input bit and possibly a carry bit. 

Truth Table:
![](https://i.imgur.com/ilaSkhN.png)

Full Adder Circuit:

![](https://i.imgur.com/gYL6R8G.png)

## Logic

We saw digital switches can be used to construct logic gates and that these logic gates can be used 

### Basic Operators

(0 is false, 1 is true)

``AND (conjunction)`` = `x ∧ y` = `x AND y` 

`OR (disjunction` = `x v y` = `x OR y`

`NOT (negation)` =`¬x` = `NOT x`

But how do we use this shit!

So, we use the basic operators and combine em and shit to form fomulae! For example:

`(A ∨ B ∧ (C ∨ B)) ∧ ¬((C ∧ B) ∨ (A ∨ C))`

There's a certain order of importance for these symbols doe: ¬, then ∧, then ∨. This means that `¬A ∧ B ∨ C ∧ ¬A` is functionally the same as s ``((¬A) ∧ B) ∨ (C ∧ (¬A))``

### Truth Tables

Truth Tables for the basic logical operators:

$$
\begin{array}{rr|r}
p & q & p ∧ q
\\ \hline F & F & F
\\ F & T & F
\\ T & F & F
\\ T & T & T
\end{array}
\space \space \space \space \space \space \space \begin{array}{rr|r}
p & q & p ∧ q
\\ \hline F & F & F
\\ F & T & F
\\ T & F & F
\\ T & T & T
\end{array}
\space \space \space \space \space \space \space \begin{array}{r|r}
p & ¬p
\\ \hline F & T
\\ T & F
\end{array}
$$

While logic is defined with respect to the basic operators, ∧, ∨, and ¬, there are other operators that exist. (Specificaly equivilance, represented by "≡" is useful asf)

### Logical Equivalence

Two boolean formulae are said to be *logically equivalent* if they have the same truth table.

For example, ``¬(¬p)`` is logically equivalent to `p`. This is typically written as `¬(¬p) ≡ p`

the corresponding truth tables is this:

$$
\begin{array}{r|r|r}
p & ¬p & ¬¬p
\\ \hline 0 & 1 & 0
\\ 1 & 0 & 1
\end{array}
$$


We can further understand that there are several propertires of these symbols that can be identified through relationshipal "equivilance" statements. This is the idea behind "communitative, associative, and dsitributive laws"

> Keep in mind, all of these are technically equivilant to "true"

$$
\begin{array}{|r|r|}\hline 
Communatative \space laws &{p ∧ q ≡ q ∧ p \\ p ∨ q ≡ q ∨ p}
\\
\hline Associative \space Laws & {(p ∧ q) ∧ r ≡ p ∧ (q ∧ r) \\ (p ∨ q) ∨ r ≡ p ∨ (q ∨ r)}
\\
\hline Distributive \space Laws & {p ∧ (q ∨ r) ≡ (p ∧ q) ∨ (p ∧ r) \\ p ∨ (q ∧ r) ≡ (p ∨ q) ∧ (p ∨ r)}
\\
\hline Identity \space Laws & {p ∧ True ≡ p \\ p ∨ False ≡ p}\\
\hline Complement \space Laws & {p ∧ ¬p ≡ False \\ p ∨ ¬p ≡ True}\\
\hline Annihilator \space Laws & {p ∧ False ≡ False \\ p ∨ True ≡ True}\\
\hline Idempotence \space Laws & {p ∧ p ≡ p \\ p ∨ p ≡ p}\\
\hline Absorption \space Laws & {p ∧ (p ∨ q) ≡ p \\ p ∨ (p ∧ q) ≡ p}\\
\hline Double \space Negation \space Law & ¬(¬p) ≡ p \\
\hline De \space Morgan's \space laws & {¬(p ∧ q) ≡ ¬p ∨ ¬q \\ ¬(p ∨ q) ≡ ¬p ∧ ¬q
}\\
\hline
\end{array}
$$

*So, lets use these laws to prove something, shall we?*

**Prove:** 
$$
(¬a ∧ ¬b) ∨ (¬a ∧ b) ∨ (a ∧ b) ≡ ¬a ∨ b
\\
(¬a ∧ ¬b) ∨ (¬a ∧ b) ∨ (a ∧ b)
\\
≡ (¬a ∧ ¬b) ∨ [(¬a ∧ b) ∨ (a ∧ b)] \space (associative) \\
≡ (¬a ∧ ¬b) ∨ [(¬a ∨ a) ∧ b \space (Distributive) \\
≡ (¬a ∧ ¬b) ∨ [True ∧ b] \space (complement) \\
≡ (¬a ∧ ¬b) ∨ b \space (AND \space identity) \\
≡ (¬a ∨ b) ∧ (¬b ∨ b) \space (distributive) \\
≡ (¬a ∨ b) ∧ True \space (complement) \\
≡ ¬a ∨ b \space (AND \space identity)
$$

### Normal Forms

When we try to analyze boolean formulae, it generally helps to writ ethe formulae in standard or *normal form.* Now, dear reader, you must be asking what the fuck normal form even is. Well, the below sections will explain that :D

### Conjunctive Normal Form

A Boolean formula is in **conjunctive normal form (CNF)** if it is a conjunction (∧) of clauses, where each clause is a disjunction (V) of variables 

> These formulae are in CNF

$$
\begin{array}{|r|r|}
\hline Formula & Clauses \\
\hline A ∧ ¬B ∧ (B ∨ C) & A, ¬C, B ∨ C \\
\hline A ∧ B & A, B \\
\hline A ∨ B & A ∨ B \\
\hline
\end{array}
$$

> These formulae are not in CNF

$$
\begin{array}{|r|r|}
\hline Formula & Reasons \\
\hline A ∧ ¬B ∧ ¬(B ∨ C) & ¬ outside (B ∨ C) \\
\hline (A ∧ B) ∨ ¬C & This \space is \space a \space disjunction \space and \space one \space clause, \space A ∧ B \space is \space a \space conjunction \\
\hline
\end{array}
$$

### Disjunctive Normal Form

It's pretty much the same thing as conjunctive normal form, just inverse. Clauses are separated by OR instead of AND

$$
\begin{array}{|r|r|}
\hline Formula & Clauses \\
\hline ¬B ∨ (A ∧ C) & ¬B, A ∧ C \\
\hline A ∧ B & A ∧ B  \\
\hline A ∨ B & A,B \\
\hline
\end{array}
$$

### Truth Tables, Formulae, and Circuits

So, how do we find the simpest circuit which is logically equivilent to a given Boolean formula? 

One way we saw this was to use the boolean formulas we've seen before to simplify an expression, but this can be difficult. 

We can also compute the truth tables for both boolean formulae then see if they're equivilant, but that can be hard too. If there are *N* variables in a formula, the truth tabs will have 2^N rows so the conversion will take exponential time in the num of variables. This is a *serious* problem.

How the fk do we do it then?

Here's an example truth table:

$$
\begin{array}{rr|r}
A & B & out \\
\hline 0 & 0 & 1 \\
 0 & 1 & 0 \\
 1 & 0 & 1 \\
 1 & 1 & 0
\end{array}
$$

The output *out* is 1 on the first and third lines, i.e. when A and B are both 0 or when A is 1 and B is 0. Therefore, we can determine that *out* is equivilant to:

$$
(¬A∧¬B)∨(A∧¬B)
$$

We simply determine the rules straight from the output of the truth table! This is called *DBF construction by 1s* and is quite intuitive imo!

As a note, this can only be done with truth tables where the output is 1


The steps are the following:
- For each row where the output is 1, write a conjunction clause (AND) of all the variables with ¬ (NOT) preceding each variable with a 0
- Take the disjunction (OR or V) of all those clauses

Going from a boolean formula to a circuit is pretty straight forward - just use AND, OR, and NOT gates :D the problem is this will make pretty messy circuits that will likely need to be simplified ._.

## Design of a Simple Processor

> This is largely a summerative example in order to bring together the last couple chapters. If you really want, you can skip lol. Although, I highly recommend following along
### Architecture

The processor will have the following components
- 8 32-bit registers R_0, R_1, ... R_7 for holding data
- 256 16-bit registers P_0, P_1, ..., P_255 for holding a program
- a 32-bit adder
- an 8-bit register *PC* that will serve as a program counter

Btw, a register is like the RAM for a CPU. 

First off, It's very useful to have the constant values 0 and 1 available for use. So, we set registers R_0 and R_1 to hold the values 0 and 1, respectively, and permanently. 

The processor will have four types of instructions: *add, negate, load,* and *jump if zero*. A program will consists of a sequence of instructions stored in the 256 program registers. Each of these registers holds 16 bits. The 16 bits of an instruction specify the type of instruction and its operands. We need two bits to specify the instruction; the two high bits (positions 14-15) will specify the instruction type. The formats of the 4 instructions areas follows:

### Addition

The add instructions simply adds the contents of two registers, R_a and R_b, then stores the value i R_c. 

### Negation

The negate instruction will replace R_a with -R_a using two's complement represetnation

### Loading

The load instruction loads an 8-bit number *d* into the 8 low-order bit positions of register R_a.

### Jump if Zero

The jump if zero instruction changes the program counter register to the value specified by an 8 bit number d, if register R_a is 0; otherwise the program counter *PC* is incrememented by 1, as usual. The jump if zero instruction is:
$$
jiz \space R_A \rightarrow d
$$
(jiz is "jump if zero" you dirty minded f___)

### Programming the CPU

The four instructions, *add, negate, load, *and* jump if zero* are enough to do complex computation. Here is a small program that computes the sum of the integers between 0 and 10:
