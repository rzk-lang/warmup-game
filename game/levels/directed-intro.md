---
id: directed-intro
title: The directed interval
role: bridge-in
---

This is what Rzk was built for. On top of the type theory you have learned, Rzk adds a **cube** and **tope** layer for *directed* type theory, following Riehl and Shulman.

The basic cube is the **directed interval** `2`, with two endpoints `0₂` and `1₂`. A **shape** carves a region out of a cube using topes (logical constraints on points); the whole interval is the shape `Δ¹ := \ t → TOP`. An **extension type** `A [ t ≡ 0₂ ↦ x , t ≡ 1₂ ↦ y ]` is the type of maps out of a shape that take prescribed values on part of its boundary.

Putting these together, a **morphism** `x → y` in a type `A` is a path along the directed interval with fixed endpoints:

```
hom A x y := (t : Δ¹) → A [ t ≡ 0₂ ↦ x , t ≡ 1₂ ↦ y ]
```

Unlike an identity `x = y`, a morphism has a *direction*, from `x` to `y`.

*By the end of this section you will be able to:* build the identity morphism at a point.

*Further reading:* Riehl and Shulman, [*A type theory for synthetic ∞-categories*](https://arxiv.org/abs/1705.07442), and the [sHoTT library](https://rzk-lang.github.io/sHoTT/).
