---
id: fiber-point
title: A point of a fiber
statement: preimage A B f (f a)
hints:
- text: 'A point of the fiber is a pair: an input, and a proof that `f` sends it where you want.'
- text: 'Pair the input `a` with the proof `refl` that `f a` equals `f a`.'
---

Every input lands in the fiber over its own image. Given `a : A`, exhibit a point of the fiber of `f` over `f a`.

Build it.

```rzk prelude
#lang rzk-1
#def preimage (A B : U) (f : A → B) (y : B)
  : U
  := Σ (x : A) , (f x = y)
```

```rzk template
#def fiber-point (A B : U) (f : A → B) (a : A)
  : preimage A B f (f a)
  := ?
```

```rzk solution
#def fiber-point (A B : U) (f : A → B) (a : A)
  : preimage A B f (f a)
  := (a , refl)
```

## Conclusion

The fiber over `f a` always contains `(a , refl)`: `a` itself, paired with the trivial proof that `f a = f a`.
