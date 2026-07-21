---
id: ind-sigma
title: The induction principle for Σ-types
statement: '(z : total-type A B) → C z'
hints:
- text: 'Pattern-match `z` as `(a , b)`. The goal becomes `C (a , b)`.'
- text: 'After pattern-matching `z` as `(a , b)`, apply `f` to `a` and `b`.'
---

The induction principle for Σ-types: define a dependent function out of the Σ-type, with `C z` depending on the pair. This is the most general way to use a Σ-value.

Build it.

```rzk prelude
#lang rzk-1
#def total-type (A : U) (B : A → U)
  : U
  := Σ (a : A) , B a
```

```rzk template
#def ind-Sigma (A : U) (B : A → U) (C : total-type A B → U) (f : (a : A) → (b : B a) → C (a , b))
  : (z : total-type A B) → C z
  := ?
```

```rzk solution
#def ind-Sigma (A : U) (B : A → U) (C : total-type A B → U) (f : (a : A) → (b : B a) → C (a , b))
  : (z : total-type A B) → C z
  := \ (a , b) → f a b
```

## Conclusion

Every use of a Σ-value factors through matching it as `(a , b)`. Induction for Σ is the general form; the projections `first`/`second` and the product principles are special cases.
