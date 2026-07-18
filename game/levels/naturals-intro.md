---
id: naturals-intro
title: Natural numbers
role: bridge-in
---

The **natural numbers** `ℕ` are built from `zero` and the successor `succ`. Their induction principle `ind-ℕ` is genuine mathematical induction: to prove something for every `n`, prove it for `zero` and show it passes from `n` to `succ n`.

Like the previous two, `ℕ` is **postulated** here, since Rzk does not yet have user-defined inductive types. It is planned as a real inductive type in the upcoming **Rzk v0.11**.

*By the end of this section you will be able to:* derive recursion for `ℕ` and define doubling.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.9.
