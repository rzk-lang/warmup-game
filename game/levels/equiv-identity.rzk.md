---
id: equiv-identity
title: Every type is equivalent to itself
statement: Equiv A A
inventory:
- name: identity
  synopsis: the identity function on a type
- name: is-equiv-identity
  synopsis: the proof that the identity is an equivalence
hints:
- text: 'An `Equiv A A` is a pair: the function, and a proof it is an equivalence.'
- text: 'Pair the function `identity A` with the proof `is-equiv-identity A`.'
---

Every type is equivalent to itself. Package the identity function with the proof that it is an equivalence.

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
```

```rzk template
#def Equiv-identity (A : U)
  : Equiv A A
  := ?
```

```rzk solution
#def Equiv-identity (A : U)
  : Equiv A A
  := (identity A , is-equiv-identity A)
```

## Conclusion

Equivalence is reflexive: `identity A`, paired with its equivalence proof, makes `A` equivalent to itself.
