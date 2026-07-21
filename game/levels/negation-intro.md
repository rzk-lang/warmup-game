---
id: negation-intro
title: Negation and disjunction
role: bridge-in
---

The Rosetta table at the start of this section already lists **negation** and **disjunction**, and you built the types for both — `Void` and `coprod` — earlier in this chapter.

Negation `¬ A` means "`A` leads to a contradiction". It is the function type `A → Void`, into the empty type: a proof of `¬ A` turns any proof of `A` into an element of a type that has none. Disjunction `A ∨ B` is the coproduct `coprod A B`: a proof is a proof of one side or the other, tagged with `inl` or `inr`.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.11.
