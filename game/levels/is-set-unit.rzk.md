---
id: is-set-unit
title: The unit type is a set
statement: is-set Unit
hints:
- text: 'Introduce the two elements `x y : Unit` and the two paths `p q : x = y`; you must prove `p = q`. Both `idJ` moves are offered — you will induct on `p`, then on `q`.'
- text: 'A double path induction. Induct on `p` first: its base case turns the goal into `refl = q`. Then induct on `q`: its base case is `refl = refl`, closed by `refl`.'
- text: 'The outer motive is `\ w s → s = q` — it mentions the path `s`, unlike the earlier levels — and the inner motive is `\ w t → refl_{x} = t`, with both base cases `refl`. Assemble the two `ind-path` calls, the inner one supplying the outer base case.'
---

`Unit` is a set: any two proofs of an equality in `Unit` are equal. Unlike `Void`, this is not automatic; it takes a double path induction. A hard one, so lean on the hints.

What makes this level unusual is the motive. It is the first proof whose motive uses the *path* it inducts on, not only the endpoint — so the outer motive binds two variables, `\ w s → …`, and actually mentions the second, `s`. You induct twice: first on `p`, which turns the goal into `refl = q`, then on `q`, which reaches `refl = refl`. Along the way the motive type-checks only because `Unit`'s elements are all definitionally `unit` — the same fact behind `is-prop-Unit`; the conclusion says why.

Build it.

```rzk prelude
#lang rzk-1
#def ind-path
  ( A : U) (a : A)
  ( C : (x : A) → (a = x) → U)
  ( d : C a refl)
  ( x : A) (p : a = x)
  : C x p
  := idJ (A , a , C , d , x , p)
#def is-prop (A : U)
  : U
  := (x y : A) → x = y
#def is-set (A : U)
  : U
  := (x y : A) → is-prop (x = y)
```

```rzk template
#def is-set-Unit
  : is-set Unit
  := ?
```

```rzk solution
#def is-set-Unit
  : is-set Unit
  := \ x y p q →
    ind-path Unit x (\ w s → s = q)
      ( ind-path Unit x (\ w t → refl_{x} = t) refl x q) y p
```

## Conclusion

Two nested path inductions collapse both `p` and `q` to `refl`, where the goal is `refl = refl`. So all equalities in `Unit` are equal: `Unit` is a set.

This proof leans on something special to the built-in `Unit`: its **definitional** uniqueness. Every element of `Unit` is *judgmentally* `unit`, so the endpoints `x`, `y`, and the induction's varying point `w` are all the same term up to computation — the same fact that let `is-prop-Unit` prove `x = y` by `refl`. That is why the inner motive `\ w t → refl_{x} = t` type-checks even though `t : x = w`: the type `x = w` is definitionally `x = x`, so `refl_{x}` and `t` live in the same identity type. A unit type you declare yourself, `#data my-Unit := my-unit`, has only *weak* (propositional) uniqueness — its elements are equal up to a path, not on the nose — so this exact proof would not type-check for it, and you would have to transport along that path by hand.
