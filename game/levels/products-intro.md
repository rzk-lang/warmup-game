---
id: products-intro
title: Products
role: bridge-in
---

A function carries one argument at a time. To hold two values at once you need a **pair**. The type of pairs of an `A` and a `B` is written `prod A B`, a pair is written `(a , b)`, and the two projections that take a pair apart are `first` and `second`.

`prod` is not a Rzk primitive. It is defined in the prelude as `prod A B := Σ (a : A) , B`, the non-dependent case of the **Σ-type** developed in the next section. So a pair and its projections are really Σ operations.

*By the end of this section you will be able to:* build a pair, project out its parts, swap a pair, and move between a two-argument function and a function on pairs (currying).

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.5.
