---
id: coproducts-summary
title: What you built
role: summary
---

You met your first inductive types, declared with `#data`: the empty type `Void` and the coproduct `coprod A B`, falsity and disjunction read as types. Declaring a type generates its induction and recursion principles, so eliminating one is just calling `rec-…` with a handler per constructor.
