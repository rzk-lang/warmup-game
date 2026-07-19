---
id: double-nat
title: Doubling
statement: ℕ → ℕ
hints:
- text: 'Use `rec-ℕ`: the base is `zero`, and the step turns the running result into two more.'
- text: 'Add two at each step: write `rec-ℕ ℕ zero (\ _ m → succ (succ m))`.'
---

Double a number: send `zero` to `zero`, and add two at each successor step. Build it with the generated `rec-ℕ`.

Build it.

```rzk prelude
#lang rzk-1
#data ℕ := zero | succ (n : ℕ)
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

Recursion turns a base and a step into a function on `ℕ`. Because computation is definitional, `double-ℕ` applied to a numeral computes to its double on the nose.
