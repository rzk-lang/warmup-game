---
id: naturals-summary
title: What you built
role: summary
---

Three inductive types, all declared with `#data` and taken apart with `match`, one branch per constructor: the empty type and coproducts (falsity and disjunction), the booleans, and the natural numbers. A `match` on a recursive type like `ℕ` binds an induction hypothesis and is genuine mathematical induction, elaborating to the generated `ind-ℕ`. Because `#data`'s computation rules are definitional, all of these compute on their own.

That completes the dependent-types toolkit. Next: logic, read as types.
