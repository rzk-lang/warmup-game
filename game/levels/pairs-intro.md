---
id: pairs-intro
title: Pairs and Σ-types
role: bridge-in
---

A function carries one argument at a time. To hold two values at once you need a **pair**. In these puzzles the type of pairs of an `A` and a `B` is written `prod A B`, a pair is written `(a , b)`, and the two projections that take a pair apart are `first` and `second`.

One thing to know up front: `prod` is not a Rzk primitive. The primitive is the **Σ-type** (sigma). In `Σ (x : A) , B x` the type of the second component may depend on the value of the first. The `prod` used here is just a convenient definition supplied in each puzzle's prelude, `prod A B := Σ (a : A) , B`, the special case where the second type ignores the first. So a pair and its projections are really Σ operations.

*By the end of this chapter you will be able to:* build a pair and project out its parts, swap a pair, move between a two-argument function and a function on pairs (currying), and build and take apart a dependent pair.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §§1.5 and 1.6.
