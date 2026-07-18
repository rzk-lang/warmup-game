---
id: type-formers-intro
title: Type formers
role: bridge-in
---

Every type in Rzk comes with a fixed set of rules: how to **form** it, how to **build** its values (constructors), and how to **use** them (eliminators), plus **computation** rules saying how the two fit together. You have seen this for products: `prod A B` is formed from two types, built by `(a , b)`, and used by `first` and `second`.

Elimination can also be packaged as a single principle. The **recursion principle** says how to define a function *out of* a type into any other type; the **induction principle** is its dependent version, defining a dependent function. For a pair, both come down to one move: match the pair as `\ (a , b) → …`, naming its two components at once. This pattern-matching λ is the eliminator in action.

There is also a **uniqueness** principle, that every pair equals `(first z , second z)`. It needs identity types, so it waits for a later chapter; in Rzk it even holds on the nose.

*By the end of this section you will be able to:* state the recursion and induction principles for products by pattern-matching on a pair.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.5.
