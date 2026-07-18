---
id: double-nat
title: Doubling
statement: ℕ → ℕ
inventory:
- name: rec-ℕ
  synopsis: recursion on a natural number (base value and step)
- name: zero
  synopsis: the number zero
- name: succ
  synopsis: the successor function
- name: ℕ
  synopsis: the type of natural numbers
hints:
- text: 'Use `rec-ℕ`: the base is `zero`, and the step turns the running result into two more.'
- text: 'Add two at each step: write `rec-ℕ ℕ zero (\ _ m → succ (succ m))`.'
---

Double a number: send `zero` to `zero`, and add two at each successor step. Build it with `rec-ℕ`.

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
#def rec-ℕ (C : U) (base : C) (step : (n : ℕ) → C → C)
  : ℕ → C
  := ind-ℕ (\ _ → C) base step
```

```rzk template
#def double-ℕ
  : ℕ → ℕ
  := ?
```

```rzk solution
#def double-ℕ
  : ℕ → ℕ
  := rec-ℕ ℕ zero (\ _ m → succ (succ m))
```

## Conclusion

Recursion turns a base and a step into a function on `ℕ`. Doubling sends `n` to `2n` by adding two per successor.
