---
id: id-morphism
title: The identity morphism
statement: hom A x x
hints:
- text: 'The goal is a map out of `Δ¹`. Introduce the interval coordinate `t`, then return a point of `A`.'
- text: 'Stay at `x` for the whole interval: write `\ t → x`.'
---

The simplest morphism is the identity at a point: the one that stays at `x` all the way along the interval. Both endpoints are `x`, so a constant path will do.

Build it.

```rzk prelude
#lang rzk-1
#def Δ¹
  : 2 → TOPE
  := \ t → TOP
#def hom (A : U) (x y : A)
  : U
  := (t : Δ¹) → A [ t ≡ 0₂ ↦ x , t ≡ 1₂ ↦ y ]
```

```rzk template
#def id-hom (A : U) (x : A)
  : hom A x x
  := ?
```

```rzk solution
#def id-hom (A : U) (x : A)
  : hom A x x
  := \ t → x
```

## Conclusion

The constant path is the identity morphism: both endpoints ask for `x`, so `x` itself fills the whole interval, with no need to move.
