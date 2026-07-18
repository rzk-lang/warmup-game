---
id: booleans-intro
title: Booleans
role: bridge-in
---

The type of **booleans** `Bool` has exactly two values, `false` and `true`. Its induction principle `ind-Bool` handles the two cases: to define something for every boolean, give its value on `false` and on `true`.

Like the coproduct, `Bool` is **postulated** here, since Rzk does not yet have user-defined inductive types. It is planned as a real inductive type in the upcoming **Rzk v0.11**.

*By the end of this section you will be able to:* derive recursion for booleans and define negation.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.8.
