[hackmd](https://hackmd.io/AYRouk4kTvuDZJ7hCQxdLQ)

###### tags: `CS1800 - Discrete Structures`

# Discrete Structures Textbook Notes - Computers and Computing: Cryptography and Modular Arithmetic

> This is part 2/6 of notes from [this](https://ccs.neu.edu/home/ntuck/courses/2015/05/cs1800/cs1800_text.pdf) textbook

Cryptography is hella important! It has been used by secret societies like the Freemasons. The germans used cyphers to hide their messages from the british.

Today, computers and the internet haev made cryptography a suuuuper important part of our lives. Passwords, purchases, atm transactions, file transfers, intellectual property, etc. 

This chapter will introduce simple methods of encrypting stuff through algebraic methods, in particular modular arithmetic. 

I'll refer to the original message as *plaintext* and the encrypted message as the *ciphertext*

## Simple Shift Ciphers

Julius Caesar was one of the *first* peple known to use cryptogrpahy to protect messages of military significance. So cool!

It's described by Suetonius in his work *Life of Julius Caesar* as: 

*There are also letters of his to Cicero, as well as to his intimates on private affairs,
and in the latter, if he had anything confidential to say, he wrote it in cipher, that
is, by so changing the order of the letters of the alphabet, that not a word could be
made out. If anyone wishes to decipher these, and get at their meaning, he must
substitute the fourth letter of the alphabet, namely D, for A, and so with the others.*

We call this the caesar cipher! Every letter is shifted over by three. 

If you're shifting after Z, it just wraps around

`DISCRETE MATH` becomes `GLVFUHWH PDWK`

We can shift all the letters in any sort of direction. Up 5, back 2, up 671. Whatever works for us!

## Encoding

Using numbers instead of letters gives us a nice advantage that we can put math and computers to work to encrypt and decrypt for us, so just keep in mind that for the future. 

*Encoding* plaintext typically means replacing the letters with numbers by an agreed upon, public method. Computers mostly use Ascii - and that's all well and good. 

But, for this example, we'll just use the numbers **00-25 to represent A-Z.**

If we encode `MATH IS COOL` with that structure, it becomes `12001907 0818 02141411` if we leave the spaces, and `12001907081802141411` if we don't. 

## The mod Function

The *mod* function has many applications in computer science - so, we shall study it in detail :O

It's used for both simple and complex cryptography, calendars nad clocks, random number generators, and hash tables for a start. 

Rn tho, we'll use the mod function to generate shift siphers and more general *linear* ciphers

### Definition

If *n* is an integer greater than 1, and *a* is any integer, then

*a* mod *n*

is the integer remainder when *a* is divided by *n*. In fact, *a* mod *n* is defined when *n* is negative, but we'll restrict our attention to n > 1. In this case, *a* mod *n* is always an integer between 0 and n-1. In scheme the mod function is given by (modulo a n)

#### Examples:

17 mod 5 = 2 --- 17 divded by 5 is 3; the remainder is 2

8 mod 5 = 3 --- 8 divided by 5 is 1; the remainder is 3

55 mod 5 = 0 --- 55 divided by 5 is 11; the remainder is 0

4 mod 5 = 4 --- 4 divided by 5 is 0; the remainder is 4

37 mod 17 = 3 --- 37 divided by 17 is 2; the remainder is 3

---
This is nice and all, but how do we evaluate *a* mod *n* when *a* is negative? Remember that as long as n > 1, the values of *a* mod *n* must be between 0 and n - 1. In general, *a* mod *n* is the unique integer beween 0 and n - 1 that satisfies a = q * n + *a* mod *n* for some integer *q*

-17 mod 5 = 3 --- -17 = -4 * 5 + 3 
-8 mod 5 = 2 --- -8 = -2 * 5 + 2
-55 mod 5 = 0 --- -55 = -11 * 5 + 0

## Properties of mod

Let *n* be an integer greater than 1, and let *a* and *b* be any integers, then

1. If *a* mod *n* = *b* mod *n* then there is an integer *k* such that a - b = k * n
2. (a+b) mod n = ((a mod n) + (b mod n)) mod n
3. (a * b) mod n = ((a mod n) * b mod n)) mod n
4. -a mod n = n - (a mod n)

## Simple Substitution Ciphers

A *simple substitution cipher* is a cryptographic sytem in which letters (or their codes), are arbitrarily tansposed or replaced with other letters (or their codes). The Caesar Cipher and the general Shift Cipher are both simple subtitution ciphers. Cryptograms that sometimes appear as newspaper puzzles are also simple substitution ciphers. Each letter is replaced by another letter. We will study some simple substitutionciphers that can be generated using the mod or modulo function

### Shift Cipher

Once we have encoded the letters A, ... , Z, a general shift cipher with the shift *k* can be described by:

$$
n \rightarrow (n + k) \space mod \space 26
$$
or by
$$
n \rightarrow (n + k) \space mod \space 29
$$

if we encode encipher space, "." and "," as well as the letters A ... Z. 

If we want our encrypted message to look like letters, possibly with punctuation, we decode the shifted codes to get our ciphertext. 

For example:
`MATH IS COOL` becomes `12001907 0818 02141411` if we just encode the letters. If we shift it by 15, we get `01150822 2307 17030300` which becomes `BPIW XH RDDA`

If we recieve the message `BPIW XH RDDA` and know that the shift key is 15, we just reverse the prodecure above to decrypt our message, ode the letters, shit by -15 (which is the same as +11 mod 26), the decode the result

### Linear Ciphers

We can create more complex substituion ciphers by using linear functions along with mod instead of just adding a constant then using mod. 

If we have a 26 letter alphabet, we can use the following equation assuing two constants, *m* and *k*

$$
a \rightarrow(m \cdot a + k) mod 26
$$

So we're shifting by a linear constant, and a flat constant.

This makes a pretty damn strong cipher! 

#### Diving Into Linear Ciphers

There are a few questions we should think about when we make a simple linear cipher:

1. What values of *m* and *k* mke good linear ciphers if the alphabet has 26 characters?
2. What if the alphabet has 29 characters, e.g. with space, "." and "," included?
3. What if the alphabet has 128 ASCII characters?
4. Can we say anything in general for an alphabet of n characters?
5. Can the person recieving our message decipher it without reconsutructing the table, i.e. with just knowing n, m, and k? (This is important if n is largr)

To answer these questions, we need to understand more about mod and the arithmetic if induces

### Modular Arithmetic

Once we fix an integer *n* greater than 1, the properties of mod, we mentioned above, allow us to talk about arithmetic mod *n* on the set Z_n of integers from 0 to n-1.

We can move to define:

$$
a + b = (a + b) \mod n
\\
a \times b = (a \times b) \mod n
$$

Consider these plus and times tables for arithmetic mod 3

![](https://i.imgur.com/N9q33DH.png)

As we can see, arithmetic mod 3 has some very nice properties. If a, b, and c are in Z_3, (the set {0, 1, 2}) then these properties are true:

$$
\begin{align}
& \mathbf{closure:} \space a + b \space \mathrm{and} \space a \times b \space \mathrm{are \space in} \space Z_3
\\ \\
& \mathbf{commutativity:} \space \mathrm{a + b = b + a \space and \space a \times b = b \times a} 
\\ \\
& \mathbf{associativity:} \space \mathrm{(a+b)+c = a+(b+c) \space and \space (a \times b) \times c = a \times (b \times c)} 
\\ \\
& \mathbf{identity + \colon} \space \mathrm{0 \space is \space an \space additive \space identity, \space meaning \space a + 0 = a for all a \in Z_3}
\\ \\ 
& \mathbf{identity \times \colon} \space \mathrm{1 \space is \space an \space additive \space identity \space a \times 0=a \space for \space all \space a \in Z_3}
\\ \\
& \mathbf{inverse + \colon} \mathrm{Every \space a \in Z_3 \space has \space an \space additive \space inverse \space b \in Z_3 \space such \space that a + b = 0}
\\ \\
& \mathbf{inverse \times \colon} \mathrm{Every \space non-zero \space a \in Z_3 \space has \space an \space multiplicative \space inverse \space b \in Z_3 \space such \space that \space a \times b = 1}
\\ \\
& \mathbf{distributive \space law \colon} \mathrm{c \times (a+b) = (c \times a) + (c \times b)} 
\end{align}
$$

Note that the symbol "∈" means "in" so a ∈ Z_3 means "a in Z_3"

~~calm down you dirty minded mfs~~

These properties mean the set Z_3 with + and x mod 3 is a mathemtical *field*. The real numbers, rational numbers, and complex numbers are also mathematical *fields* with their regular addition and multiplication

Now that we have the laws, lets consider these + and x tables for arithmetic mod 4 on the set $Z_4 = {0, 1, 2, 3}$

![](https://i.imgur.com/jRlp1pZ.png)

Addition mod 4 has p similar properties to addition mod 3. There is an additive identity, 0, and evert $a \in Z_4$ has an additive identity, $0+0 = 1+3=2+2=0$. However, $Z_4$ is not a field. I does have a multiplicative identity, $a \times 1 = a$ for all $a \in Z_4$, but 2 does not have a mulitiplicive inverse. There is *no answer* for $2 \times b = 1$ or $2 \times b = 3$ in $Z_4$ (because $2 \times 2 \mod 4 = 0$).

In general, we say $a \in Z_n$ is a *zero-divisor* mod *n* if there isa non-zero $b \in Z_n$ such that $a \times b \mod n = 0$ 

Now we can say what values of *m* will be bad for linear ciphers, $a \rightarrow (m \cdot a + b) \mod 26$

(anything equal to $26 - b \over a$!)

### Powers mod n

We often have to compute powers of numbers mod n. The RSA Encryption algorithm, which is widely used in electronic commerce protocols uses high powers of numbers mod n. 

Check out the basics of RSA encryption [here](http://fringe.davesource.com/Fringe/Crypt/RSA/Algorithm.html)

We can easily compute powers mod *n* when the exponent is itself a power of 2 by using the property: 

$$
(a \cdot b) \bmod n = ((a \bmod n) \cdot (b \bmod n)) \bmod n
$$

and the fact that:

$$
a^{(2^k)} = a^{(2\cdot2^{k-1})} = a^{(2^{k-1} + 2^{k-1})} = (a^{(2^{(k-1)})}) \cdot (a^{(2^{k-1})}) = (a^{(2^{k-1})})^2
$$

The idea is to alternate evaluating mod *n* and squaring. This is probably best understood by looking at some examples:

#### Powers mod n squaring

$$
\begin{align}
& 37^2 \bmod 3 = (37 \bmod 3)^2 = 1^2 = 1
\\
& 115^4 \bmod 7 = (115 \bmod 7)^4 = (3 \bmod 7)^4 = (3^2 \bmod 7)^2 = (9 \mod 7)^2 = (2 \bmod 7)^2 = (2^2 \bmod 7) = (4 \bmod 7) = 4
\end{align}
$$

To compute $a^m$ mod *n* when *m* is not a power of 2, we use the binary representation of *m* to express *m* as a sum of powers of 2 and the rule for the product of two powers with the same base. In general, *m* can be expressed as $n = b_k2^k + b_{k-1}2^{k-1} + ... + b_12+b_0$ where $b_i = 0$ or 1 for $0 \leq i \leq k$ 

Each factor in this product where $b_i = 0$ evaluates to 1. In the other factors, $b_i = 1$ and the factor is just *a* raised to a power that is a power of 2. To evaluate $a^m \bmod *n*$ we apply the repeated squaring and evaluating mod n described above to each of these factors and then multiply the results mod *n*

## Integers and Division

Through you probably learned about integers and division back in 2nd grade or som lmao, we need formal defintions and theorems to descrie the algorithms we use and to verify that they are correct, in general. 

### Divides

if *a* and *b* are integers and a /= 0, we can say that a *divides* b (or that a is a *factor* of b) if there is an integer c such that $b=ac$

a | b means a divides b.

a /- b means a does not divide b.

#### Theorum 2

*Let a, b and c be integers, then*
1. *if a | b and a | c then a | (b+c)*
2. *if a | b then a | bc for all integers, c*
3. *if a | b and b | c then a | c*

Proof for #1: 

Assume that a, b, and c be integers and that a | b and a | c. From the defintion of *divides*, there must be integers *m* and *n* such that:
$$
b = ma \\
c = na
$$

Adding the left - and the right-hand sides of the equations nets us:
b + c = ma + na

distributive law...
b + c = (m + n)a

by the closure of addition, m + n is an intefer, so by the defition of divides,
a|(b + c)

### Primes

If a positive integer $p>1$ is called *prime* if the only positive factors of *p* are 1 and *p*. Extremely large prime numbers are used in RSA and other algorithms for public key crypography. Primes are also used for hash tables and pseudorandom number generators. 

#### Finding Primes

Howe can we find prime numbers? In 200BC, the mathematician Eratosenthenes invented a prime number sieve, the "Sieve of Eratosthenes," which, in modified form, is still used in number theory research. Here's how it works:

1. Make a list-to-check of the numbers from 2 to *N*
2. Make a list-of-primes that starts out empty
3. Repeat the following until the first number in the list-to-check is $> \sqrt{N}$
    a. put the first number in the list-to-check in the list-of-primes
    b. remove all multiples of that number from the list-to-check
4. Put all the numbers still in list-to-check into list-of-primes

#### Example: 

That's kinda arbitrary, so lets look at an example!

To find all the primes up to N=25, we start with:

list-to-check = 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25

list-of-primes =

Then we put 2 in the list-of-primes and remove all multiples of 2 from the list-to check. we now have:

list-to-check = 3 5 7 9 11 13 15 17 19 21 23 25

list-of-primes = 2

Now put 3 in the list-of-primes and remove all multiples of 3 from the list-to-check. We now have:

list-to-check = 5 7 11 13 17 19 23 25

list-o-primes = 2 3

Now we do the same thing with 5...

list-to-check = 7 11 13 17 19 23

list-of-primes = 2 3 5

Since $\sqrt{25} = 5$, we put all the numbers remaining in the list-to-check into the list-of-primes. List-of-primes (less than or equal to 25) = 2 3 5 7 11 13 17 19 23

### Prime Number Decomposition

A positive integer $n > 1$ that is not prime is a call *composite*. Composite integers can always be expressed as products of primes.

#### Theorem 3 (Fundamental Theorem of Arithmetic)

*Every positive integer greater than 1 can be written uniquely as a prime or as the product of two or more primes where the prime factors are written in order of non-decreasing size. This is the prime number decomposition of the integer*

#### Example:

a. $364 = 2 \cdot 2 \cdot 7 \cdot 13 = 2^2 \cdot 7 \cdot 13$
b. $7581 = 7 \cdot 19 \cdot 57$
c. $32768 = 2^{15}$
d. $31752 = 2^3 \cdot 3^4 \cdot 7^2$

### More About Primes

Theorem 4: *There are infinitely many primes*

**Proof:** Here's a pretty neat proof thanks to Euclid! Suppose for the sake of contradiction, that there are only a finite number of primes; let $S = \{p_1, p_2, ... p_n\}$ be the set of all prime numbers. Now consider the number..

$$
P = {p_1 \cdot p_2 \cdot \cdot \cdot \space p_n + 1}
$$

Now *P* must be must be either prime or composite. 

> composite = a num that can made by multiplying other whole numbers

If *P* were composite, it must be divisible by a prime in *S*; however, the remainder after the division of *P* by any $p_i$ is 1, by construction. Therefore, *P* must be prime, contradticting the assumption that *S* is the set of all primes, since *P* is clearly larger than any element of *S*. Thus, our assumption that there are a finite number of primes must be false.

So cool!!

### Division

Back in elementary school, we learned about division in problems like this:

$$
\require{enclose}
\begin{array}{r}
                4  \\[-3pt]
7 \enclose{longdiv}{29} \\[-3pt]
\end{array} \space \space \space \space \space
r = 1
$$

In this equation, 29 is the divident, 7 is the divisor, 4 is the quotient, and 1 is the remainder. The following therum tells us that we can always find a quotient and remaineder in a division problem. 

#### Theorem:

*let a be an integer and b a positive integer. Then there are multiple integers q and r, with $0 \leq r \lt b$ such that $a = b \cdot q + r$*

### Greatest Common Divisor and Least Common Multiple

if *a* and *b* are integers, that are ont both 0, the *greatest common divisor* of *a* and *b*, gcd(a,b) is the largest integer *d* that *d* | *a* and *d* | *b*

Examples:
1. gcd(75, 21) = 3
2. gcd(52, 81) = 1
3. $\gcd(2^2 \cdot 7 \cdot 13, 2^3 \cdot 3^4 \cdot 7^2) = 2^2 \cdot 3^0 \cdot 7 \cdot 13^0 = 2^2 \cdot 7$ (what is this rule?^1)
4. gcd(49831, 825579) = ?
5. $lcm(75, 21) = 75 \cdot 7 = 25 \cdot 21 = 525$
6. $lcm(52, 81) = 52 \cdot 81 = 4212$

1 - gcd(a, b) divides both a and b so the exponent of each prime factor of gcd must be the minimum of that prime's exponent in a and b

*two integers are said to be relatively prime or coprime if gcd(m, n) = 1. The integers 52 and 81 are relatively prime*

### Applications of gcd and lcm

The most common applications of the gcd and lcm is in working with fractions. You put them to us ewhenever you reduce or add fractions. You would use tem the same way if you were implementing a class to represent factions:

reducing fractions with gcd:

$$
{84 \over 36} = {12 \cdot 7 \over {12 \cdot 3}} = {7 \over 3} \space \space \space \space \space \gcd(84, 36) = 12
$$

we can use lcm when we add fractions!

$$
{3 \over 5} + {2 \over 7} = {21 + 10 \over 35} = {31 \over 35} \space \space \space \space \space lcm(5, 7) = 35
$$

we can also use gcd in crypography. For exampe, to decrypt a linear cipher

$$
a \rightarrow (m \cdot a + b) \bmod n
$$

we need a multiplicative inverse for $m \bmod n$. In fact, a multiplicative inverse for $m \bmod n$ exists if any only if gcd(m, n) = 1. If we are working with a large number of letters or blocks *n*, we need an efficient way to calculate gcd(m, n) in order to check whether we are using a good multiplier, *m*

### Euclidean Algorithm

How do you find the gcd(49831, 825579) or gcd(8094702578291,7403070229547) or the gcd of two hundred-digit numbers? You could factor both numbers, but this is a costly operation and will not be feasible if the numbers are too large. The **Euclidean Algorithm** is a method to compute the gcd of two non-zero integers, *a* and *b*. The method is based on the Division Algo.

#### Therem 7 (Euclidean Algorithm)

*if r is the remainder when a is divided by b, i.e. $a=q\cdot b + r$, with $0 \leq r \lt b$, then gcd(a,b) = gcd(b,r)*

If $a=q\cdot b + r$, with $0 \leq 4 \lt b$ then, by definiton, $r=a \bmod b$. So another wya of stating the Uclidean algorithm is $\gcd(a,b) = \gcd(b, a \bmod b)$. This still sounds like a theory rather than an algorithm that lays out the steps to find gcd(a,b), tho. This is how we use it as an algorithm:

**The Algo Itself:**

*input:* two positive numbers, *a* and *b*
*output:* gcd(a, b)

- if a < b, swap a and b
- if b divides a, return b
- else return gcd(b, a mod b)

The correctness of the Euclidean Algorithm can be proven in many wyas. Here, we make the following lemma concerning *divides* and *gcd*

Lemma 1: if x | y and x | z, then x | gcd(y, z)

**Proof:** Since *x* is a common divisor of both y and z, it must be a factor of the greatest common divisor of y and z

we can now use this lemme to verify the correctness of the Euclidean Algorithm. 

> gotta complete this bit..

## Inverses mod n

We have already seen that we need to fin dmultiplicative inverses mod *n* to decipher cipher text that was created using linear ciphers. Mutliplicative inverses mod *n* are important in the decryption process in much more sophisitacted encryption systems we will see in the next section, the *RSA (Rivest-Shamir-Adelman) cryptosystem.* Recall that the *multiplicative inverse* of an integer *a* modulo *n* is an integer *x* such that x * a mod n = 1. An integer *a* has the multiplicative inverse mod *n* if and only gcd(a, n) = 1. This means we can apply the extended euclidian algorithm to silve $a \cdot a + y \cdot n = 1$. this implies $x \cdot a = 1 - y \cdot n$ which means $x \cdot a \bmod n = 1$ so *x* is the muliplicative inverse of *a* mod *n*

### The RSA (Rivest Shamir Adelman) cryptosystem

The RSA cyptosystem is a public-key cryptosystem, widely used for secure communication and e-commerce applications. It is often used to encrypt messages sent between two communicating pearties so that an eavesdropper who overhears the converastion cannot decode the messages easily. It also enables a party to append an unforgeable signature to the end of a message. This signiature cannot be "easily" forget and can be checked by anyone.

#### How do public-key cryptosystems work?

Consider our anime protagonists Alice and Bob. The want to communicate with each other securely. 

Suppose bob watns to send a message to Alice. In a typical public-key cryptosystem Alice has two keys, a secret (or private) key that only Alice knows and a public key that Alice advertises to the whole world. Each key yields a function that maps a message to another message: the public key yields a public *encryption function* - let us call it $P_A$ - and the secret key yields a secret *decryption function*, $S_A$. A typical message exchange proceeds as follows:

- Bob encrypts his message M using $P_A$ and sends the message $P_A(M)$ to Alice.
- If Alice recieves $P_A(M)$ she applies $S_A$ and obtains $S_A(P_A(M)) = M$, for all permissible messages $M$

Furthermore, our seletion of $S_A$ and $P_A$ should be such that any eavesdropper, who can read message $P_A(M)$ cannot "efficiently" extract M from this; or, ideally, cannot "effectively" etract any reasonable information from this

### How does RSA work?

The basic RSA cryptosystem is completely specified by the following sequence of steps.
1. Alie selects at random two large primes *p* and *q*
2. Alice computes $n = pq$
3. Alice selects a small odd integer *e* that is relatively prime to (p-1)(q-1)

> two nums are relatively if they share no common positive factors (divisors) except 1.

4. Alice sets *d* so that *de* mod (p-1)(q-1) equals 1
5. Alice publishes the pair (e, n) as the public key, with $P_A(M) = M^e \bmod n$
6. Alice stores the pair (d, n) as  the secret key, with $S_A(E) = E^d \bmod n$

In order to send a message $M$ in $\{0,1,...,n-1\}$, Bon sends $P_A(M) = M^e \bmod n$. On recieving the encrypted message Alice computes $S_A(P_A(M)) = M^{de} \bmod n$. Our choices of d, e, and n ensure that $M^{de} \bmod n equals M$

To see the last step, we need to undersetand the mathematical underpinnings of RSA, which we will do so in the next setion. But first, lets do a couple examples!

Take:
$$
p=5, q=3;n=5 \cdot 3 = 5;(p-1)(q-1)= 4 \cdot 2 = 8; e =3
$$

We need to find the multiplicative inverse of 3 mod 8. Well, 3 * 3 = 9 mod 8 = 1. So d = 3. Suppose we take

$$
p=7,q=11;n=7 \cdot 11 = 77;(p-1)(q-1)=6\cdot 10 = 60; e=13
$$

> I need to finish this bit..

### Is RSA secure and efficient?

What are the individual steps in RSA? Which of these can be executed efficiently? How secure is RSA? Here is a brief discussion on the efficiency and security of RSA:

- Generting two large primes: How do we perform this? Well, one way to do it is to generate a random number and test if it's prime. How do we test whether it's prime tho? Our naive scheme (that works in time proportional to the square root of the number) is too slow and inefficient. Fortunately, there are faster, efficient, ways to do it.
- We need to raise a number to a (potentially) large power in modular arithmetic. We have seen how to do this efficnetly using the repeated squaring method
- We also need to find a multiplicative inverse in modula arithmetic. this canbe done efficiently using the Extended Euclid Algorithm.
- We do not want the number *n* (used in the RSA private and public key) to be easily favtored into its prime factors *p* and *q*. A native algorithm takes time proprtional to the square root of *n*. Fortunately, there is *no* efficient way known for this problem :DDD
- As stated, RSA is a deterministic encryption system; i.e., a particular message is encrypted the same way each time. This is prone to easy attacks, referred to as plaintext attacks, where the attacker may be aware that the message is being sent is one of a small number of possibility, and can try the public encryption system with different possiblities. One way to avoid this attack is th randomize the system - for instance by adding a fixed size random pad to the plaintext message and encrypting the padded message. The random pad is chose independently at eery step, this making the above plaintext attack more difficult. 
