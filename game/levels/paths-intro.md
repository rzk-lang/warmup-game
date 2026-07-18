---
id: paths-intro
title: Identity types and paths
role: bridge-in
---

The last new type is the **identity type**. For a type `A` and elements `x y : A`, the type `x = y` is the type of equalities between `x` and `y`, also called *identities* or *paths*. It has one constructor, `refl`: the proof by reflexivity that everything equals itself, `refl : x = x`.

Rzk also has fuller forms that spell out what `=` and `refl` leave implicit. The type can name the ambient type, `x =_{A} y`, and the constructor can name its point, `refl_{x}`, or the point together with its type, `refl_{x : A}`. The short `=` and `refl` are just these with the annotations inferred, and they are all you need in this chapter.

Everything else about equality comes from a single principle, **path induction** (also called `J`). Fix a point `x : A`. To prove a statement `C` that may depend on *both* the other endpoint `y` and the path `p : x = y`, it is enough to prove the one base case where `y` is `x` and `p` is `refl`. Since `refl` is the only way to build a proof of equality, that single case covers every path.

The prelude packages this as `ind-path`:

```
ind-path (A : U) (x : A)
  (C : (y : A) → (x = y) → U)   -- the motive: what to prove, over the endpoint y and the path
  (d : C x refl)                -- the base case, at y = x and p = refl
  (y : A) (p : x = y)
  : C y p
```

You supply the motive `C` and a base-case proof `d`, and get `C y p` for any endpoint and path. On the base case it computes: `ind-path A x C d x refl` reduces to `d`.

For example, path induction can even talk about the path itself. With the motive `C w q := (q = q)`, the base case `C x refl` is `refl = refl`, true by `refl`, so induction gives `p = p` for every path `p`. The levels below use simpler motives that ignore the path argument, which is why their solutions read `\ w _ → …` and then prove their own base case.

In homotopy type theory a proof of `x = y` is pictured as a **path** from `x` to `y`.

*By the end of this chapter you will be able to:* reverse and concatenate paths, apply a function to a path, and transport a value along a path, each by path induction.
