---
id: bonus
statement: hom2 A x x x (id-hom A x) (id-hom A x) (id-hom A x)
title: A constant triangle (bonus)
---

An optional ★ level. Marked `extra` in `game.yaml`, it does not gate completion of the section — it is enrichment for anyone who wants it.

A triangle (`hom2`) is a map out of the $2$-simplex $\Delta^2$. The constant triangle at $x$, whose three edges are all the identity, is filled by the constant map. Two coordinates this time, but the value never moves.

```rzk prelude
#lang rzk-1
#def Δ¹
  : 2 → TOPE
  := \ t → TOP
#def Δ²
  : ( 2 × 2) → TOPE
  := \ (t , s) → s ≤ t
#def hom (A : U) (x y : A)
  : U
  := (t : Δ¹) → A [ t ≡ 0₂ ↦ x , t ≡ 1₂ ↦ y ]
#def id-hom (A : U) (x : A)
  : hom A x x
  := \ t → x
#def hom2 (A : U) (x y z : A)
  ( f : hom A x y) (g : hom A y z) (h : hom A x z)
  : U
  := ((t , s) : Δ²) → A [ s ≡ 0₂ ↦ f t , t ≡ 1₂ ↦ g s , s ≡ t ↦ h s ]
```

```rzk template
#def bonus (A : U) (x : A)
  : hom2 A x x x (id-hom A x) (id-hom A x) (id-hom A x)
  := ?
```

```rzk solution
#def bonus (A : U) (x : A)
  : hom2 A x x x (id-hom A x) (id-hom A x) (id-hom A x)
  := \ (t , s) → x
```

## Conclusion

The constant triangle ignores both coordinates. With the identity on every edge, $x$ itself fills the whole simplex.
