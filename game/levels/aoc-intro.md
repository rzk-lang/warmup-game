---
id: aoc-intro
title: The axiom of choice
role: bridge-in
---

A striking payoff of Σ-types. Suppose that for each `x : A` you are given a value of `Σ (y : B) , R x y`: a witness `y`, together with data `R x y`. The **type-theoretic axiom of choice** collects all of these into one function `A → B` that picks a witness for each `x`, paired with the data for each.

It holds because a value of a Σ-type already carries its witness in the first component: projecting gives the choice function directly, with nothing left to choose. So the *type-theoretic* axiom of choice is a theorem. It is not the classical axiom of choice, which is stated with a weaker "there exists" that records only *that* a witness exists, not which one. That statement can be written precisely in homotopy type theory, and there it is a genuine, unprovable axiom.

*By the end of this section you will be able to:* prove the type-theoretic axiom of choice.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.6.
