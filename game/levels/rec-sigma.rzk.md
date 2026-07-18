---
id: rec-sigma
title: The recursion principle for Σ-types
statement: total-type A B → C
hints:
- text: 'Pattern-match the pair: `\ (a , b) → ?`, with `a : A` and `b : B a`.'
- text: 'Combine them with `f`: write `\ (a , b) → f a b`.'
---

The recursion principle for Σ-types, the dependent generalization of the one for products. Given `f` that takes a first component `a` and a second `b : B a`, define a function out of the Σ-type into any type `C`.

Build it.

```rzk prelude
#lang rzk-1
#def total-type (A : U) (B : A → U)
  : U
  := Σ (a : A) , B a
```

```rzk template
#def rec-Sigma (A : U) (B : A → U) (C : U) (f : (a : A) → B a → C)
  : total-type A B → C
  := ?
```

```rzk solution
#def rec-Sigma (A : U) (B : A → U) (C : U) (f : (a : A) → B a → C)
  : total-type A B → C
  := \ (a , b) → f a b
```

## Conclusion

The same pattern-matching move as for products, now with a second component whose type `B a` depends on the first.
