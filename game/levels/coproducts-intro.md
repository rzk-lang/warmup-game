---
id: coproducts-intro
title: Coproducts
role: bridge-in
---

A **coproduct** `coprod A B` is a disjoint union: a value is either an `A` or a `B`, tagged by which side it came from. Its nullary companion is the **empty type** `Void`, with no values at all. Read as logic, a coproduct is *disjunction* ("or") and `Void` is *falsity*; the Propositions as types chapter develops that reading.

The empty type has no constructors, and the coproduct has two:

```
#data Void

#data coprod (A B : U)
  := inl (a : A)
  |  inr (b : B)
```

A coproduct is built with `inl` (left) or `inr` (right), and taken apart by `match`, with a branch for each side: `match z (inl a ⇒ … | inr b ⇒ …)`. `Void` has no constructors, so there is nothing to match on — you eliminate it with the generated `rec-Void` (or its dependent form `ind-Void`) instead, vacuously.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.7.
