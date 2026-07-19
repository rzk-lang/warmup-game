---
id: naturals-intro
title: Natural numbers
role: bridge-in
---

The **natural numbers** `ℕ` are a *recursive* inductive type: `zero` is a number, and `succ` takes a number to its successor.

```
#data ℕ := zero | succ (n : ℕ)
```

Because `succ` stores a `ℕ`, the generated `ind-ℕ` is genuine mathematical induction: it hands the step an *induction hypothesis* for the predecessor. Its non-dependent form `rec-ℕ` builds a function from a base value and a step.

*By the end of this section you will be able to:* double a number and add two numbers, both by recursion.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.9.
