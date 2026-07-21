---
id: ind-prod
title: The induction principle for products
statement: '(z : prod A B) → C z'
hints:
- text: 'Pattern-match the pair: `\ (a , b) → ?`. The goal becomes `C (a , b)`.'
- text: 'After pattern-matching the pair, apply `f` to the two components `a` and `b`.'
---

The **induction principle** is the dependent version of recursion: the result type `C z` may depend on the pair `z`. Given `f` that handles a literal pair `(a , b)`, define the dependent function.

Build it.

```rzk prelude
#lang rzk-1
#def prod (A B : U)
  : U
  := Σ (a : A) , B
```

```rzk template
#def ind-prod (A B : U) (C : prod A B → U) (f : (a : A) → (b : B) → C (a , b))
  : (z : prod A B) → C z
  := ?
```

```rzk solution
#def ind-prod (A B : U) (C : prod A B → U) (f : (a : A) → (b : B) → C (a , b))
  : (z : prod A B) → C z
  := \ (a , b) → f a b
```

## Conclusion

Same move, dependent codomain: matching `z` as `(a , b)` makes the goal `C (a , b)`, which `f a b` fills. Recursion is the special case where `C` ignores its argument.
