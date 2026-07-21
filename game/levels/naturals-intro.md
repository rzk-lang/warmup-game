---
id: naturals-intro
title: Natural numbers
role: bridge-in
---

The **natural numbers** `ℕ` are a *recursive* inductive type: `zero` is a number, and `succ` takes a number to its successor.

```
#data ℕ := zero | succ (n : ℕ)
```

You take a number apart with `match`, as before — but now one constructor is *recursive*. Because `succ` stores a `ℕ`, its branch binds not only the predecessor `k` but an **induction hypothesis** `ih`: the result of the recursion on `k`.

```
match n
  ( zero ⇒ …
  | succ k ih ⇒ …)
```

That hypothesis is what makes a `match` on `ℕ` genuine mathematical induction. Under the hood, `#data ℕ` generates the induction principle `ind-ℕ` (and its non-dependent form `rec-ℕ`), and every `match` elaborates to it. Recursion happens only through the hypothesis, so it always terminates.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.9.
