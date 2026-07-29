---
id: plus
title: Addition
statement: ℕ
checks:
- prop: plus (succ zero) (succ zero) = succ (succ zero)
  label: 1 + 1 = 2
- prop: plus zero (succ zero) = succ zero
  label: 0 + 1 = 1
- prop: plus (succ zero) zero = succ zero
  label: 1 + 0 = 1
hints:
- text: 'Recurse on `m` with `match`. The `zero` branch returns `n`; the `succ` branch binds the predecessor `k` and the induction hypothesis `ih` (the result of the recursion on `k`).'
- text: 'The `zero` branch returns `n`; the `succ k ih` branch returns `succ` of the hypothesis `ih`. Fill these into `match m (…)`.'
---

Addition by recursion on the first argument: `plus zero n` is `n`, and `plus (succ m) n` is one more than `plus m n`. Build it with `match`.

Build it.

```rzk prelude
#lang rzk-1
#data ℕ := zero | succ (n : ℕ)
```

```rzk template
#def plus (m n : ℕ)
  : ℕ
  := ?
```

```rzk solution
#def plus (m n : ℕ)
  : ℕ
  := match m
       ( zero ⇒ n
       | succ k ih ⇒ succ ih)
```

## Conclusion

Recursion on `m`: the `zero` branch returns `n`, and each `succ` adds one to the running total `ih`, the result of the recursion on the predecessor `k`. That `ih` binder is the **induction hypothesis** — recursion happens only through it, so every `match` terminates. That is addition, and it computes definitionally.
