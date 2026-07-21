---
id: double-nat
title: Doubling
statement: ℕ → ℕ
hints:
- text: 'Use `match`: the `zero` branch is `zero`, and the `succ` branch turns the induction hypothesis `ih` into two more.'
- text: 'The `zero` branch is `zero`; the `succ k ih` branch adds two to the hypothesis `ih`. Fill these into `match n (…)` under a `\ n →`.'
---

Double a number: send `zero` to `zero`, and add two at each successor step. Build it with `match`.

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
  := \ n → match n
       ( zero ⇒ zero
       | succ k ih ⇒ succ (succ ih))
```

## Conclusion

Recursion turns a base branch and a step branch into a function on `ℕ`. Because computation is definitional, `double-ℕ` applied to a numeral computes to its double on the nose.
