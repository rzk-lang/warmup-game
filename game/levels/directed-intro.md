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

The square brackets make this an **extension type**. An element of
`(t : Δ¹) → A [ t ≡ 0₂ ↦ x , t ≡ 1₂ ↦ y ]` is a function `f : Δ¹ → A` from the shape `Δ¹` to the type `A` that strictly satisfies the constraints listed inside the brackets: here, that `f 0₂` is `x` and `f 1₂` is `y`.

These equations are judgmental, not identity types. Rzk checks them for you rather than asking you to prove them. So to build a term of an extension type you write a function that satisfies the constraints, and that is all: there is no side goal to discharge.
