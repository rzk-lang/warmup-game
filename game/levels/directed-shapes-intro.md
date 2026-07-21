---
id: directed-shapes-intro
title: Morphisms and triangles
role: bridge-in
---

This is what Rzk was built for. On top of the type theory you have learned, Rzk adds a **cube** and **tope** layer for *directed* type theory, following Riehl and Shulman.

The basic cube is the **directed interval** `2`, with two endpoints `0₂` and `1₂`. A **shape** carves a region out of a cube using topes (logical constraints on points): the whole interval is the shape `Δ¹ := \ t → TOP`, and one dimension up is the 2-simplex `Δ²`. An **extension type** `A [ t ≡ 0₂ ↦ x , t ≡ 1₂ ↦ y ]` is the type of maps out of a shape that take prescribed values on part of its boundary.

Here you build the two simplest directed shapes: the identity morphism, and then a triangle.

*By the end of this section you will be able to:* build the identity morphism at a point and fill the constant triangle.

*Further reading:* Riehl and Shulman, [*A type theory for synthetic ∞-categories*](https://arxiv.org/abs/1705.07442), and the [sHoTT library](https://rzk-lang.github.io/sHoTT/).
