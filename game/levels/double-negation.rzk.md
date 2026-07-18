---
id: double-negation
title: Double-negation introduction
statement: '(a : A) → neg (neg A)'
hints:
- text: 'Introduce `a`, then a proof `f` of `neg A`. The goal is `Void`.'
- text: 'A proof of `neg A` is a function `A → Void`. Apply it to `a`: write `\ a f → f a`.'
---

**Double-negation introduction**: if `A` holds, then `A` cannot be refuted. With `neg A` defined as `A → Void`, prove `A → neg (neg A)`.

The converse, `neg (neg A) → A`, is *not* provable here. That is double-negation *elimination*, which intuitionistic logic does without.

Build it.

```rzk prelude
#lang rzk-1
#postulate Void : U
#def neg (A : U)
  : U
  := A → Void
```

```rzk template
#def double-negation (A : U)
  : (a : A) → neg (neg A)
  := ?
```

```rzk solution
#def double-negation (A : U)
  : (a : A) → neg (neg A)
  := \ a f → f a
```

## Conclusion

`\ a f → f a` reads: given `a` and a refutation `f` of `A`, derive a contradiction by applying `f` to `a`. Double-negation elimination stays out of reach without an extra axiom.
