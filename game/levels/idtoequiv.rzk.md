---
id: idtoequiv
title: Equal types are equivalent
statement: Equiv A B
inventory:
- name: ind-path
  synopsis: 'path induction: reduces a goal about a path to the refl case'
- name: Equiv
  synopsis: the type of equivalences between two types
- name: Equiv-identity
  synopsis: every type is equivalent to itself
hints:
- text: 'Induct on `p` with `ind-path` at the universe `U`. The base case asks for `Equiv A A`.'
- text: 'The motive is `\ e _ → Equiv A e` and the base case is `Equiv-identity A`. Assemble these with `ind-path` at the universe `U`, inducting on `p`.'
---

From a path between types, build an equivalence between them. Induct on the path: when it is `refl`, the equivalence is the identity.

One caveat before you start. Here `p : A = B` is an equality between *types*, not between elements of a fixed type — an identity one universe up from the paths you have been proving so far. Inducting on it means path induction over the universe `U` itself, which relies on Rzk treating `U` as its own type. That is convenient here, but it is not yet on firm footing (a proper account needs universe levels, which Rzk does not track for now). So read this level as a preview of the shape univalent reasoning takes, rather than a proof to rely on.

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
#def Equiv (A B : U)
  : U
  := Σ (f : A → B) , is-equiv A B f
#def is-equiv-identity (A : U)
  : is-equiv A A (identity A)
  := ((identity A , \ _ → refl) , (identity A , \ _ → refl))
#def Equiv-identity (A : U)
  : Equiv A A
  := (identity A , is-equiv-identity A)
#def ind-path
  ( A : U) (a : A)
  ( C : (x : A) → (a = x) → U)
  ( d : C a refl)
  ( x : A) (p : a = x)
  : C x p
  := idJ (A , a , C , d , x , p)
```

```rzk template
#def idtoequiv (A B : U) (p : A = B)
  : Equiv A B
  := ?
```

```rzk solution
#def idtoequiv (A B : U) (p : A = B)
  : Equiv A B
  := ind-path U A (\ e _ → Equiv A e) (Equiv-identity A) B p
```

## Conclusion

Path induction reduces to the case where `p` is `refl` and `B` is `A`, and there the equivalence is `Equiv-identity A`. Every equality of types gives an equivalence.
