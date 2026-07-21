---
id: paths-intro
title: Identity types and paths
role: bridge-in
---

The last new type is the **identity type**. For a type `A` and elements `x y : A`, the type `x = y` is the type of equalities between `x` and `y`, also called *identities* or *paths*. It has one constructor, `refl`: the proof by reflexivity that everything equals itself, `refl : x = x`.

Rzk also has fuller forms that spell out what `=` and `refl` leave implicit. The type can name the ambient type, `x =_{A} y`, and the constructor can name its point, `refl_{x}`, or the point together with its type, `refl_{x : A}`. The short `=` and `refl` are just these with the annotations inferred, and they are all you need in this section.

Everything else about equality comes from a single principle, **path induction** (also called the *J rule*). Fix a point `x : A`. To prove a statement `C` that may depend on *both* the other endpoint `y` and the path `p : x = y`, it is enough to prove the one base case where `y` is `x` and `p` is `refl`. Since `refl` is the only way to build a proof of equality, that single case covers every path.

Rzk's built-in eliminator for identity types is `idJ`. The prelude wraps it in the more readable `ind-path`, which you will use throughout this section:

```
ind-path (A : U) (x : A)
  (C : (y : A) → (x = y) → U)   -- the motive: what to prove, over the endpoint y and the path
  (d : C x refl)                -- the base case, at y = x and p = refl
  (y : A) (p : x = y)
  : C y p
```

You supply the motive `C` and a base-case proof `d`, and get `C y p` for any endpoint and path. On the base case it computes: `ind-path A x C d x refl` reduces to `d`.

This principle looks abstract, but the exercises that follow make it concrete. They recover the familiar laws of equality, each proved the same way, by reducing to the single `refl` case:

- **reflexivity** is given: `refl : x = x`.
- **symmetry** is `rev`: from `x = y` it builds `y = x`.
- **transitivity** is `concat`: from `x = y` and `y = z` it builds `x = z`.
- **congruence** is `ap`: a function sends equal inputs to equal outputs, `f x = f y`.
- **substitution** is `transport`: a property that holds at `x` is carried to `y`.

Working through them is how to see what path induction means. In each you supply a motive and prove its base case; the motives here do not use the path itself, so the solutions begin `\ w _ → …`.

In homotopy type theory a proof of `x = y` is pictured as a **path** from `x` to `y`.

*By the end of this section you will be able to:* reverse and concatenate paths, apply a function to a path, and transport a value along a path, each by path induction — and, pairing identity with Σ-types, exhibit a point of a fiber.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.12 and §2.1.
