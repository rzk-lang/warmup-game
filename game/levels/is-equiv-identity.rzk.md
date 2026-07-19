---
id: is-equiv-identity
title: The identity is an equivalence
statement: is-equiv A A (identity A)
inventory:
- name: identity
  synopsis: the identity function on a type
hints:
- text: 'An `is-equiv` is a pair of a retraction and a section. Both are the identity here.'
- text: 'Each round-trip is homotopic to the identity by `refl`: write `((identity A , \ _ → refl) , (identity A , \ _ → refl))`.'
---

The identity function is an equivalence: it is its own retraction and its own section. Build the two witnesses.

Build it.

```rzk prelude
#lang rzk-1
#def identity (A : U)
  : A → A
  := \ x → x
#def prod (A B : U)
  : U
  := Σ (a : A) , B
#def homotopy (A B : U) (f g : A → B)
  : U
  := (x : A) → f x = g x
#def is-equiv (A B : U) (f : A → B)
  : U
  := prod
      ( Σ (r : B → A) , homotopy A A (\ a → r (f a)) (identity A))
      ( Σ (s : B → A) , homotopy B B (\ b → f (s b)) (identity B))
```

```rzk template
#def is-equiv-identity (A : U)
  : is-equiv A A (identity A)
  := ?
```

```rzk solution
#def is-equiv-identity (A : U)
  : is-equiv A A (identity A)
  := ((identity A , \ _ → refl) , (identity A , \ _ → refl))
```

## Conclusion

Both inverses of the identity are the identity, and both round-trips are literally the identity, homotopic to it by `refl`.
