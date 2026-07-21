---
id: eq-from-equiv
title: Equivalent types are equal
statement: Equiv A B → (A = B)
inventory:
- name: ua
  type: '(A : U) → (B : U) → Equiv (A = B) (Equiv A B)'
  synopsis: the univalence axiom (assumed)
- name: inv
  synopsis: extracts a left inverse from an equivalence
- name: Equiv
  synopsis: the type of equivalences between two types
hints:
- text: 'Univalence `ua A B` is an equivalence `Equiv (A = B) (Equiv A B)`. Invert it to go from an `Equiv A B` back to an `A = B`.'
- text: 'Invert the equivalence `ua A B` with `inv`. Recall `inv` takes the two related types first, then the equivalence.'
---

The univalence direction: turn an equivalence into an equality of types. Univalence is *assumed* here as `ua`, and the definition names that dependence with `uses (ua)` — an honest record that this proof rests on an axiom, not on the constructions of the earlier chapters. Feed the equivalence that `ua` provides through `inv`, the inverse map you extracted in the previous section.

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
#def UnivalenceAxiom
  : U
  := (A : U) → (B : U) → Equiv (A = B) (Equiv A B)
#assume ua : UnivalenceAxiom
#def inv (A B : U)
  : Equiv A B → (B → A)
  := \ e → first (first (second e))
```

```rzk template
#def eq-from-Equiv uses (ua)
  (A B : U)
  : Equiv A B → (A = B)
  := ?
```

```rzk solution
#def eq-from-Equiv uses (ua)
  (A B : U)
  : Equiv A B → (A = B)
  := inv (A = B) (Equiv A B) (ua A B)
```

## Conclusion

`inv` extracts a left inverse from any equivalence; applied to `ua A B`, it turns an equivalence of types into an equality. This round trip is what makes univalent foundations "univalent".
