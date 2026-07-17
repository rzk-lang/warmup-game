---
hints:
- text: 'Induct on the path `p` with `ind-path`. As the endpoint varies, you want a path back to `x`.'
- text: 'The motive sends an endpoint `y''` and a path `x = y''` to `y'' = x`; at `refl` that is `x = x`, so the base case is `refl`. Build it with `ind-path A x (\ y'' p'' → y'' = x) refl y p`.'
  when-goal: '= x'
id: no-idj
gated: true
inventory:
# An entry is usually just a name and a synopsis; the type is read from the
# prelude. Here we also give an explicit `type`, to show how to override it.
- name: ind-path
  synopsis: path induction — the principle to use here
  type: '(A : U) (a : A) (C : (x : A) → (a = x) → U) (d : C a refl) (x : A) (p : a = x) → C x p'
forbidden:
- idJ
statement: y = x
title: Build it yourself
---

Reverse a path: from `p : x = y`, build a path `y = x`. This level is **gated** — its success is withheld unless you build the reversal the intended way, with path induction.

Two things stand in your way, and they show the two halves of a gate. First, the prelude already defines the finished `rev`, but it is **not** in your inventory, so calling `rev A x y p` type-checks yet trips the gate: the inventory grants only `ind-path`. Second, the built-in eliminator behind path induction is `idJ`, which the inventory cannot reach because it is not a prelude definition — so it is named in the `forbidden` list. A forbidden move is dropped from the Moves panel, and writing one fails the check.

So build it yourself with the granted `ind-path`. To see each guard, try `rev A x y p` (ungranted) or `idJ (A , x , …)` (forbidden) and watch the gate refuse them. Without `gated: true` both would be soft amber notices rather than hard failures.

The prelude is split across two blocks, to show that `prelude` fences are concatenated in order. Run `make format-game` from a checkout to tidy them in place.

```rzk prelude
#lang rzk-1
#def ind-path
  ( A : U)
  ( a : A)
  ( C : (x : A) → (a = x) → U)
  ( d : C a refl)
  ( x : A)
  ( p : a = x)
  : C x p
  := idJ (A , a , C , d , x , p)
```

```rzk prelude
#def rev (A : U) (x y : A) (p : x = y)
  : y = x
  := ind-path A x (\ y' p' → y' = x) refl y p
```

```rzk template
#def no-idj (A : U) (x y : A) (p : x = y)
  : y = x
  := ?
```

```rzk solution
#def no-idj (A : U) (x y : A) (p : x = y)
  : y = x
  := ind-path A x (\ y' p' → y' = x) refl y p
```

## Conclusion

The gate keeps a puzzle honest. The inventory rules out the pre-made `rev`, and `forbidden` rules out the raw `idJ` — a built-in the inventory cannot touch — so the only way through is to build the reversal yourself with `ind-path`. The scan looks only at proof bodies, never the prelude or the type signatures.
