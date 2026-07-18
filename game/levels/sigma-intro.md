---
id: sigma-intro
title: Σ-types
role: bridge-in
---

The **Σ-type** (sigma) generalizes the product. In `Σ (a : A) , B a` the type of the second component may depend on the value of the first, where `B : A → U` is a **type family**. A value is still a pair `(a , b)`, now with `a : A` and `b : B a`. When `B` ignores its argument, `Σ (a : A) , B` is exactly `prod A B`.

The projections are `first` and `second` as before, but `second` is subtler: its type mentions the first component. Rzk lets you abbreviate the type as `total-type A B := Σ (a : A) , B a`.

*By the end of this section you will be able to:* build and take apart a dependent pair, and state the recursion and induction principles for Σ-types.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.6.
