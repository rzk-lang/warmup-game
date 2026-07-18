---
id: coproducts-intro
title: Coproducts
role: bridge-in
---

A **coproduct** `coprod A B` is a disjoint union: a value is either an `A` or a `B`, tagged by which side it came from. Its nullary companion is the **empty type** `Void`, with no values at all. Read as logic, a coproduct is *disjunction* ("or") and `Void` is *falsity*.

These types are **postulated** here. Rzk does not yet have user-defined inductive types, so `Void` and `coprod`, with their constructors `inl`/`inr` and their induction principle, are assumed in the prelude rather than defined. This is a genuine preview: inductive types are planned for the upcoming **Rzk v0.11**, after which they become ordinary definitions.

A coproduct is built with `inl` (left) or `inr` (right), and used with `ind-coprod`, which handles the two cases separately.

*By the end of this section you will be able to:* derive recursion from induction for the empty type and for coproducts, and swap the two sides of a coproduct.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.7.
