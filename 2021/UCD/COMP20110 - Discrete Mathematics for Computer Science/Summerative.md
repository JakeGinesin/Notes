###### tags: `COMP20110 - Discrete Mathematics for Computer Science`

# COMP20110 - Discrete Mathematics for Computer Science

> This class is just proving a ton of proofs. Pretty cool stuff! :D 
> The prof would show a proof, then prove it with the previously explained proofs.
> There are various symbols with various proof functions demonstrated throughout the class, including equival, or, and, not, etc.


## Notation

 - According to my prof, the base of proofs is notation. Good notation should almost do the work for you.
 - The notation on its own doesn't have a solid definition. Rather, the meaning the notation has is defined by the relationships it has with smols n stuff.
     - For example {x ≡ not(x)} is false by definition.
 - Also, recognize the symbols "X" or "Y" or wtv are just placeholders for actual values. You can plug in whatever value for the variable and it'd work

### Notation example:

> Basic Stuff

- `≡` "equival"
- `∨` "or"
- `∧` "and"
- `¬` "not"
- `⇒` "implies"

> More advanced stuff

- `::` "all"
- `R` "range"
- `F` "term"
- `∀` "for all"
- `≔` "is defined as"

## Proofs

- As a note, I'm just listing these in the order that I learned em.

### Intro equival "≡" proofs

- **(1)** `[(X≡(Y≡Z)) ≡ ((X≡Y)≡Z)]` "≡ associative"
- **(2)** `[X≡Y≡Y≡X]` "≡ symmetric"
- **(3)** `[X≡true≡X]` "≡ reflexive "
- **(4)** `[X≡X]` "identity of ≡"
- **(5)** `True` 

> Just an interesting side note, but all of these proofs are equal to true. If we have true in a proof, we can replace it with any existing proof

### Intro or "∨" proofs

> ∨ "or" binds higher than ≡ "equival"

- **(6)** `[X∨Y ≡ Y∨X]` "∨ symmetric"
- **(7)** `[X∨(Y∨Z) ≡ (XvY)vZ]` "v associative"
- **(8)** `[XvX ≡ X]` "v independent"
- **(9**) `[Xv(Y≡Z) ≡ XvY ≡ XvZ]` "v distributed"
- **(10)** `[XvTrue ≡ True]` "v zero"

### Or "v" proof example:

We observe for any X, Y, Z, W...

``Xv(Y≡Z≡W) ≡ ?``
= {v distributed, X, Y, Z ≔ X, Y, Z = w}
``XvY ≡ Xv(Z≡W)``
= {v distributed, X, Y, Z ≔ X, Z, W}
`XvY ≡ XvZ ≡ ZvW`

### Proving #10

We observe for any X...

XvTrue ≡ True 
> Start with more complex side..

``(XvTrue)``
= {Identity of ≡}
``(Xv(X≡X))``
= {v distribution}
``(XvX ≡ XvX)``
= {Identity of ≡}
`True`

---

### And "∧" Proofs

- **(11)** `[X∧Y ≡ X ≡ Y ≡ XvY]` "Golden Rule!"
- **(12)** `[X∧Y ≡ Y∧X]` "∧ Symmetry"
- **(13)** `[X∧(Y∧Z) ≡ (X∧Y)∧Z]` "∧ Associative"
- **(14)** `[X∧X ≡ X]` "∧ Identity"

### Proving #12

We observe for any X, Y...

(X∧Y ≡ Y∧X)
``(X∧Y)``
= {Golden Rule}
`X ≡ Y ≡ XvY`
= {≡ Symm.}
`Y ≡ X ≡ XvY`
= {v Symm.}
`Y ≡ X ≡ YvX`
= {Golden Rule}
`Y∧X`

---

### "∧" and "v" proofs
- **(17)** `[Xv(X∧Y) ≡ X]`
- **(18)** `[(XvY)∧(XvZ) ≡ Xv(Y∧Z)]`
- **(20)** `[X∧(Y≡Z) ≡ X ≡ (X∧Z) ≡ (X∧Y)]`
- **(21)** `[X∧(Y≡Z≡W) ≡ X∧Y ≡ X∧Z ≡ X∧W]`
- **(22)** `[X∧(Y≡Y) ≡ X∧Y]`
- **(23)** `[(X≡Y) ∧ (W≡X) ≡ (X≡Y) ∧ (X≡Y)]`
 
### Proving #17

We observe for any X, Y...

``Xv(X∧Y)``
= {Golden Rule, X, Y ≔ X, (X∧Y)}
``X ≡ X∧Y ≡ X∧Y ≡ X∧(X∧Y)``
= {∧ Associative}
`X ≡ (X∧Y) ≡ (X∧X) ∧ Y`
= {∧ Identity}
`X ≡ X∧Y ≡ X∧Y`
= {Symmetry}
`X`

### Proving #18

We observe for any X, Y...
``(XvY) ∧ (XvZ)``
= {Golden Rule, X, Y ≔ XvY, XvZ}
``XvY ≡ XvZ ≡ XvYvXvZ``
= {V independent}
`XvY ≡ XvZ ≡ XvYvZ`
= {v distribution}
``Xv(Y≡Z≡YvZ)``
= {Golden Rule, X, Y ≔ Y, Z}
``Xv(Y∧Z)``

### Proving #20

We observe for any X, Y, Z...
``X∧(Y≡Z)``
= {Golden Rule, X, Y ≔ X, Y≡Z}
``X ≡ Y≡Z ≡ Xv(Y≡Z)``
= {v Distribution}
`X ≡ Y ≡ Z ≡ XvY ≡ XvZ`
= {Golden Rule, X, Y ≔ X, Z}
`X ≡ X∧Z ≡ X∧Y`

### Proving #21

- It's worth noting that this example is in contrary to 20. Keep 20 in mind as you read this one

We observe for any X, Y, Z, W...
`X∧(Y≡Z≡W)`
= {Theory 20 with X, Y, Z ≔ X, Y, Z≡W}
`X∧Y ≡ X∧(Z≡W) ≡ X`
= {Theory 20 Again}
`X∧Y ≡ X∧Z ≡ X∧W ≡ X ≡ X`
= {≡ Symmetry}
`X∧Y ≡ X∧Z ≡ X∧W`

- Woah! If the inside is odd, you'll get a perfect series with no extras. If it's even, you'll get stuck with an extra thing on the end >_<

### Proving #22

We observe for all X, Y...

`X∧(X≡Y)`
= {Theory 20, X, Y, Z ≔ X, X, Y}
`X∧X ≡ X∧Y ≡ X`
= {∧ Identity}
`X ≡ X∧Y ≡ X`
= {≡ Equivilance}
`X∧Y`

---

### Intro to implication "⇒" proofs

- **(24)** `[X⇒Y ≡ XvY≡Y]`
- **(25)** `[X⇒X]` "⇒ Reflexive"
- **(26)** `[X⇒True]` "⇒ Identity"

> It's worth keeping in mind that, with 26, the whole proof is technically equival to "True"

### Intro to not "¬" proofs
 
- **(34)** `[False ≡ ¬True]` "False Definition"
- **(35)** `[¬(X≡X) ≡ ¬X≡Y]` "¬ Over ≡"
- **(36)** `[¬X ≡ X ≡ False]` "¬ Identity"
- **(37)** `[¬X ≡ Y ≡ X ≡ ¬Y]` "¬ Flip"
- **(38)** `[¬¬X ≡ X]` "Double Negative ¬"
- **(39)** `[Xv¬X]` "Excluded Middle"
- **(40)** `[¬XvY ≡ XvY≡Y]`
- **(41)** `[XvFalse ≡ X]` "Identity of v"
- **(42)** `[X∧False ≡ False]` "Zero ∧"
- **(43)** `[¬Xv¬Y ≡ ¬(X∧Y)]` "De Morgan"

### Prooving #43

We observe for all X, Y...
`¬Xv¬Y`
= {40}
`¬Xv¬Y ≡ ¬Y`
= {v Symmetry}
``¬YvX ≡ ¬Y``
= {40}
`YvX ≡ X ≡ ¬Y`
= {≡ Symm, v Symm}
`¬Y ≡ X ≡ XvY`
= {¬ Over ≡}
``¬(Y ≡ X ≡ XvY)``
= {Golden Rule}
``¬(X∧Y)``

### Summerative Proofs pt 1
- **(46)** `[Xv(¬X∧Y) ≡ XvY]`
- **(47)** `[X∧(¬XvY) ≡ X∧Y]`
> ^ These are compliment laws
- **(48)** `[X≡Y≡(X∧Y) v (¬X ∧ ¬Y)]`
- **(49)** `[X∧¬X ≡ False]` "Contradiction"
- **(50)** `[X⇒Y ≡ ¬XvY]`
- **(51)** `[X⇒Y ≡ ¬Y⇒¬X]`
- **(52)** `[false⇒X]`
- **(53)** `[X⇒False⇒¬X]` "Reducio AD Absurdem"

### Prooving #46

We oberve for all X, Y... 
``Xv(¬X∧Y)``
= {v Distrib over ∧}
``Xv¬X ∧ XvY``
= {Known theory}
`True ∧ XvY`
= {Id v}
`XvY`

### Prooving #49

We observe for all X, Y
`X∧¬X`
= {Golden Rule}
`X ≡ ¬X ≡ Xv¬X`
= {Excluded Middle (Known Theory)}
`X ≡ ¬X ≡ True`
= {≡ Identity}
`X ≡ ¬X`
= {Neg Id}
`False`

### Prooving #50

We observe for all X, Y..
`¬XvY`
= {Theory 40}
`XvY ≡ Y`
= {Identity of ⇒}
`X ⇒ Y`

### Summerative Proofs pt 2
- **(54)** `¬False ≡ True`
- **(55)** `[X∧(X⇒Y)⇒Y ≡ Y∧X ⇒ Y]`

### Prooving #55

We observe for all X, Y...

``X∧(X⇒Y)⇒Y``
= {Theory #50}
`X∧(¬XvY)⇒Y`
= {∧ Distribution}
`X∧¬X v X∧Y ⇒ Y`
= {Contradiction}
`False v X∧Y ⇒ Y`
= {Identity of v}
`X∧Y ⇒ Y`
= {∧ Symmetry}
`Y∧X ⇒ Y`



