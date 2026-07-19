---
id: equivalences-intro
title: Homotopy and equivalence
role: bridge-in
---

When are two functions "the same"? A **homotopy** `homotopy A B f g` is a pointwise equality: a proof that `f x = g x` for every `x`.

```
homotopy A B f g := (x : A) → f x = g x
```

A function `f : A → B` is an **equivalence** when it has a two-sided inverse: a *retraction* (a left inverse `r`, with `r (f a)` homotopic to `a`) and a *section* (a right inverse `s`, with `f (s b)` homotopic to `b`).

```
is-equiv A B f := prod
    (Σ (r : B → A) , homotopy A A (\ a → r (f a)) (identity A))
    (Σ (s : B → A) , homotopy B B (\ b → f (s b)) (identity B))
```

Two types are **equivalent**, `Equiv A B`, when some `f : A → B` is an equivalence.

*By the end of this section you will be able to:* build the reflexive homotopy, show the identity function is an equivalence, and conclude every type is equivalent to itself.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §2.4 and §4.
