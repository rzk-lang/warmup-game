---
hints:
- text: 'Both endpoints of the path are the same point $x$, so you never have to move along the interval.'
- text: 'The goal is still the whole path type `(t : 2 | Δ¹ t) → …`. Your first move is to introduce the interval coordinate: tap `λ-intro` or type `\ t → ?`. Then return $x$.'
  when-goal: 'Δ¹ t'
id: identity
statement: hom A x x
title: The identity morphism
---

A morphism $x \to y$ is a path along the directed interval $\Delta^1$. The simplest one is the identity: the morphism from $x$ to itself that just stays put. Both endpoints are $x$, so a constant path will do. Build it.

This level carries two hints. Ask for one with the hint button: the first is plain. The second is contextual — it appears on its own while the goal is still the path type, and disappears once you introduce the coordinate.

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
#def identity (A : U) (x : A)
  : hom A x x
  := ?
```

```rzk solution
#def identity (A : U) (x : A)
  : hom A x x
  := \ t → x
```

## Conclusion

The constant path is the identity morphism. Both endpoints ask for $x$, so $x$ itself fills the hole — no need to move along the interval at all.
