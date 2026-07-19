---
id: aoc-intro
title: The axiom of choice
role: bridge-in
---

A striking payoff of Σ-types. Suppose that for each `x : A` you are given a value of `Σ (y : B) , R x y`: a witness `y`, together with data `R x y`. The **type-theoretic axiom of choice** collects all of these into one function `A → B` that picks a witness for each `x`, paired with the data for each.

It holds because a value of a Σ-type already carries its witness in the first component: projecting gives the choice function directly, with nothing to invent. (Under the reading of the next chapter, this is the *axiom of choice* of logic, provable here where in set theory it is an axiom.)

*By the end of this section you will be able to:* prove the type-theoretic axiom of choice.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.6.
