---
id: rec-nat
title: The recursion principle for numbers
statement: ℕ → C
inventory:
- name: ind-ℕ
  synopsis: induction on a natural number (base case and step)
hints:
- text: 'Use `ind-ℕ` with a constant motive `\ _ → C`, then the base and the step.'
- text: 'Write `ind-ℕ (\ _ → C) base step`.'
---

Define a function out of `ℕ` by a base value and a step that extends the result from `n` to `succ n`. Derive recursion from `ind-ℕ`.

Build it.

```rzk prelude
#lang rzk-1
#postulate ℕ : U
#postulate zero : ℕ
#postulate succ (n : ℕ) : ℕ
#postulate ind-ℕ
  ( C : ℕ → U)
  ( base : C zero)
  ( step : (n : ℕ) → C n → C (succ n))
  : (n : ℕ) → C n
```

```rzk template
#def rec-ℕ (C : U) (base : C) (step : (n : ℕ) → C → C)
  : ℕ → C
  := ?
```

```rzk solution
#def rec-ℕ (C : U) (base : C) (step : (n : ℕ) → C → C)
  : ℕ → C
  := ind-ℕ (\ _ → C) base step
```

## Conclusion

With a constant motive, induction becomes recursion: a base value and a step build a function on every number.
