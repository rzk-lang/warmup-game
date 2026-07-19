---
id: negation-aside
title: Negation and disjunction
role: note
---

The table above already lists **negation** and **disjunction**, and you have the types for both from the Dependent types chapter.

Negation `¬ A` means "`A` leads to a contradiction". It is the function type `A → Void`, into the empty type: a proof of `¬ A` turns any proof of `A` into an element of a type that has none. Disjunction `A ∨ B` is the coproduct `coprod A B`: a proof is a proof of one side or the other, tagged with `inl` or `inr`.

The next level proves a first fact about negation. The De Morgan laws relating negation, conjunction, and disjunction are provable too, by case analysis on the coproduct.
