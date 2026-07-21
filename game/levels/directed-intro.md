---
id: directed-intro
title: Morphisms
role: bridge-in
---

A **morphism** `x → y` in a type `A` is a path along the directed interval with fixed endpoints:

```
hom A x y := (t : Δ¹) → A [ t ≡ 0₂ ↦ x , t ≡ 1₂ ↦ y ]
```

Unlike an identity `x = y`, a morphism has a *direction*, from `x` to `y`.
