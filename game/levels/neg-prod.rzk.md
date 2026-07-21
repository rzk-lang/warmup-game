---
id: neg-prod
title: De Morgan, other direction
statement: prod (neg A) (neg B) → neg (coprod A B)
hints:
- text: 'You hold refutations of `A` and of `B`, and are handed a proof of `coprod A B`. Case-analyse it with `match`.'
- text: 'For a left `a`, apply `first p`; for a right `b`, apply `second p`. Fill these into `match z (…)`.'
---

If `A` is false and `B` is false, then `A ∨ B` is false. Given refutations of both, refute the coproduct by case analysis.

Build it.

```rzk prelude
#lang rzk-1
#data Void
#data coprod (A B : U)
  := inl (a : A)
  |  inr (b : B)
#def neg (A : U)
  : U
  := A → Void
#def prod (A B : U)
  : U
  := Σ (a : A) , B
```

```rzk template
#def neg-prod (A B : U)
  : prod (neg A) (neg B) → neg (coprod A B)
  := ?
```

```rzk solution
#def neg-prod (A B : U)
  : prod (neg A) (neg B) → neg (coprod A B)
  := \ p z → match z
       ( inl a ⇒ first p a
       | inr b ⇒ second p b)
```

## Conclusion

Matching on the coproduct sends a left `a` to the refutation `first p` and a right `b` to `second p`, both landing in `Void`. Refuting both sides refutes their disjunction.
