---
id: negation-intro
title: Negation and disjunction
role: bridge-in
---

The table in the previous section already lists **negation** and **disjunction**, and you have the types for both from the Dependent types chapter.

Negation `¬ A` means "`A` leads to a contradiction". It is the function type `A → Void`, into the empty type: a proof of `¬ A` turns any proof of `A` into an element of a type that has none. Disjunction `A ∨ B` is the coproduct `coprod A B`: a proof is a proof of one side or the other, tagged with `inl` or `inr`.

*By the end of this section you will be able to:* prove double-negation introduction, and two of the De Morgan laws relating negation, conjunction, and disjunction.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.11.
