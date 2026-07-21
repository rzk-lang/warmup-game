---
id: const-triangle
title: The constant triangle
statement: hom2 A x x x (id-hom A x) (id-hom A x) (id-hom A x)
hints:
- text: 'The goal is a map out of `Δ²`. Introduce the two coordinates, then return a point of `A`.'
- text: 'Introduce the two coordinates, ignore them, and return `x`.'
---

The simplest triangle is the constant one at `x`, whose three edges are all the identity morphism. Fill it with the constant map: two coordinates now, but the value never moves.

Build it.

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
#def const-triangle (A : U) (x : A)
  : hom2 A x x x (id-hom A x) (id-hom A x) (id-hom A x)
  := ?
```

```rzk solution
#def const-triangle (A : U) (x : A)
  : hom2 A x x x (id-hom A x) (id-hom A x) (id-hom A x)
  := \ (t , s) → x
```

## Conclusion

The constant triangle ignores both coordinates. With the identity on every edge, `x` fills the whole simplex.
