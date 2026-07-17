---
id: paths-intro
title: Identity types and paths
role: bridge-in
---

The last new type is the **identity type**. For `x y : A`, the type `x = y` is the type of proofs that `x` and `y` are equal. It has one constructor, `refl`, the proof that anything equals itself: `refl : x = x`.

Rzk also has fuller forms that spell out what `=` and `refl` leave implicit. The type can name the ambient type, `x =_{A} y`, and the constructor can name its point, `refl_{x}`, or the point together with its type, `refl_{x : A}`. The short `=` and `refl` are just these with the annotations inferred, and they are all you need in this chapter.

Everything else about equality comes from a single principle, **path induction**. To prove something about an arbitrary proof `p : x = y`, it is enough to prove it in the case where `p` is `refl` (and `y` is `x`). The prelude packages this as `ind-path`; using it reduces a goal about `p` to the `refl` case.

In homotopy type theory a proof of `x = y` is pictured as a **path** from `x` to `y`. That picture is where the directed intervals of the final chapter begin.

*By the end of this chapter you will be able to:* reverse and concatenate paths, apply a function to a path, and transport a value along a path, each by path induction.
