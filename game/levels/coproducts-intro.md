---
id: coproducts-intro
title: Coproducts
role: bridge-in
---

A **coproduct** `coprod A B` is a disjoint union: a value is either an `A` or a `B`, tagged by which side it came from. Its nullary companion is the **empty type** `Void`, with no values at all. Read as logic, a coproduct is *disjunction* ("or") and `Void` is *falsity*.

In the Type formers section you wrote the eliminators for products by hand. For a new type, the **`#data` command** declares it and generates its eliminators for you. The empty type has no constructors, and the coproduct has two:

```
#data Void

#data coprod (A B : U)
  := inl (a : A)
  |  inr (b : B)
```

Each declaration generates the induction principle `ind-…` and its non-dependent version `rec-…`. A coproduct is built with `inl` (left) or `inr` (right), and taken apart by `rec-coprod`, which handles the two cases separately.

*By the end of this section you will be able to:* eliminate the empty type, and swap the two sides of a coproduct.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.7.
