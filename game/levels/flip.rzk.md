---
id: flip
title: Swapping arguments
statement: 'B → A → C'
hints:
- text: 'Introduce both arguments: tap the introduction move twice, or type `\ b a → ?`. That gives `b : B` and `a : A`.'
- text: 'After introducing `b` then `a`, apply `f` in its own order: the `A`, then the `B`.'
---

A two-argument function can take its arguments in either order. Given `f` that wants an `A` and then a `B`, build the version that wants a `B` and then an `A`.

Build it.

```rzk prelude
#lang rzk-1
```

```rzk template
#def flip (A B C : U) (f : A → B → C)
  : B → A → C
  := ?
```

```rzk solution
#def flip (A B C : U) (f : A → B → C)
  : B → A → C
  := \ b a → f a b
```

## Conclusion

Only the binding order changed. Underneath, `f` is still applied to an `A` and then a `B`.
