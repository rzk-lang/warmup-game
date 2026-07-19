---
id: is-set-unit
title: The unit type is a set (★)
statement: is-set Unit
hints:
- text: 'Bind the two elements and the two paths `p`, `q`, then induct on `p`, and inside that, induct on `q`, reaching `refl = refl`. This is a genuine double path induction.'
- text: 'Write `\ unit unit (p : unit = unit) (q : unit = unit) → ind-path Unit unit (\ unit s → s = q) (ind-path Unit unit (\ unit t → refl_{unit} = t) refl unit q) unit p`.'
---

`Unit` is a set: any two proofs of an equality in `Unit` are equal. Unlike `Void`, this is not automatic; it takes a double path induction. A hard one, so lean on the hints.

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
  := \ unit unit (p : unit = unit) (q : unit = unit) →
    ind-path Unit unit (\ unit s → s = q)
      ( ind-path Unit unit (\ unit t → refl_{unit} = t) refl unit q) unit p
```

## Conclusion

Two nested path inductions collapse both `p` and `q` to `refl`, where the goal is `refl = refl`. So all equalities in `Unit` are equal: `Unit` is a set.
