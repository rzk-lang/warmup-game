---
id: flip
title: Swapping arguments
statement: '(b : B) → (a : A) → C'
hints:
- text: 'Introduce both arguments: tap the introduction move twice, or type `\ b a → ?`. That gives `b : B` and `a : A`.'
- text: 'Apply `f` in its own order, an `A` then a `B`: `f a b`.'
---

A two-argument function can take its arguments in either order. Given `f` that wants an `A` and then a `B`, build the version that wants a `B` and then an `A`.

Build it.

```rzk prelude
#lang rzk-1
```

```rzk template
#def flip (A B C : U) (f : A → B → C)
  : (b : B) → (a : A) → C
  := ?
```

```rzk solution
#def flip (A B C : U) (f : A → B → C)
  : (b : B) → (a : A) → C
  := \ b a → f a b
```

## Conclusion

Only the binding order changed. Underneath, `f` is still applied to an `A` and then a `B`.
