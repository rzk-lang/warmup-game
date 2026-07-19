---
id: neg-coprod
title: De Morgan, one direction
statement: neg (coprod A B) → prod (neg A) (neg B)
hints:
- text: 'A refutation of `coprod A B` refutes each side. Build the pair of the two refutations.'
- text: 'Feed each injection to `k`: write `\ k → (\ a → k (inl A B a) , \ b → k (inr A B b))`.'
---

If a proof of `A ∨ B` is impossible, then neither side can hold on its own. From a refutation of the coproduct, build the pair of refutations of `A` and of `B`.

Build it.

```rzk prelude
#lang rzk-1
#data Void
#data coprod (A B : U)
  := inl (a : A)
  |  inr (b : B)
#def neg (A : U)
  : U
  := A → Void
#def prod (A B : U)
  : U
  := Σ (a : A) , B
```

```rzk template
#def neg-coprod (A B : U)
  : neg (coprod A B) → prod (neg A) (neg B)
  := ?
```

```rzk solution
#def neg-coprod (A B : U)
  : neg (coprod A B) → prod (neg A) (neg B)
  := \ k → (\ a → k (inl A B a) , \ b → k (inr A B b))
```

## Conclusion

To refute `A`, inject it on the left and hand it to `k`; to refute `B`, inject it on the right. Refuting a disjunction refutes both sides.
