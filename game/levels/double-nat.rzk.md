---
id: double-nat
title: Doubling
statement: ℕ → ℕ
checks:
- prop: double-ℕ zero = zero
  label: double 0 = 0
- prop: double-ℕ (succ zero) = succ (succ zero)
  label: double 1 = 2
- prop: double-ℕ (succ (succ zero)) = succ (succ (succ (succ zero)))
  label: double 2 = 4
hints:
- text: 'Use `match`: the `zero` branch is `zero`, and the `succ` branch turns the induction hypothesis `ih` into two more.'
- text: 'The `zero` branch is `zero`; the `succ k ih` branch adds two to the hypothesis `ih`. Fill these into `match n (…)` under a `\ n →`.'
---

Double a number: send `zero` to `zero`, and add two at each successor step. Build it with `match`.

If you have written recursive definitions in another proof assistant, the shape here is worth a second look. There is no recursive call: `double-ℕ` is not in scope inside its own body, so `double-ℕ k` is not something you can write. Instead the `succ` branch binds **two** variables, `succ k ih`: the predecessor `k`, and `ih`, the result of the function on that predecessor. Everything a recursive call would have given you is already handed to you as `ih`, which is why the recursion always terminates and always computes.

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

The induction hypothesis `ih` is the recursive call, already made. Naming it rather than writing it is what makes `match` a total, computing eliminator instead of a general recursion you would have to justify.
