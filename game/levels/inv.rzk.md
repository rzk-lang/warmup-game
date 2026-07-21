---
id: inv
title: The inverse of an equivalence
statement: Equiv A B → (B → A)
hints:
- text: 'An equivalence `e` packs its forward function with a proof it is one. The inverse you want lives inside that proof: `second e` is the `is-equiv` structure.'
- text: 'From `second e`, take `first` for the retraction pair `(r , …)`, then `first` again for its function `r : B → A`.'
---

An equivalence `e : Equiv A B` carries more than its forward function `A → B`: buried in the proof that it *is* an equivalence sits a two-sided inverse. Extract the **retraction**, the left inverse `B → A`, by projecting into that proof.

This is a small but useful move — the univalence section needs exactly this to turn the equivalence `ua` provides back into an equality.

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
```

```rzk template
#def inv (A B : U)
  : Equiv A B → (B → A)
  := ?
```

```rzk solution
#def inv (A B : U)
  : Equiv A B → (B → A)
  := \ e → first (first (second e))
```

## Conclusion

The retraction is `first (first (second e))`: `second e` is the `is-equiv` proof, its first half is the retraction pair `(r , …)`, and `first` of that is the map `r : B → A`. Reaching into a structure with the projections is all it takes — and this `inv` is the tool the next section uses.
