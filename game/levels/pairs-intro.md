---
id: pairs-intro
title: Pairs and Σ-types
role: bridge-in
---

A function carries one argument at a time. To hold two values at once you need a **pair**. Here the type of pairs of an `A` and a `B` is written `prod A B`, and a pair is written `(a , b)`. Rzk gives you two projections to take a pair apart, `first` and `second`.

The **Σ-type** (sigma) generalizes this. In `Σ (x : A) , B x` the type of the second component may depend on the value of the first. An ordinary product `prod A B` is the special case `Σ (a : A) , B`, where the second type ignores the first.

*By the end of this chapter you will be able to:* build a pair and project out its parts, swap a pair, move between a two-argument function and a function on pairs (currying), and build and take apart a dependent pair.
