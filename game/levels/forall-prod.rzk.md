---
id: forall-prod
title: For-all distributes over "and"
statement: '((x : A) → prod (P x) (Q x)) → prod ((x : A) → P x) ((x : A) → Q x)'
hints:
- text: 'Build a pair of two dependent functions. Each takes an `x` and projects `k x`.'
- text: 'Write `\ k → (\ x → first (k x) , \ x → second (k x))`.'
---

If for every `x` both `P x` and `Q x` hold, then `P` holds for all `x` and `Q` holds for all `x`. This is distribution of "for all" over conjunction, the quantified version of the earlier `distribute`.

Build it.

```rzk prelude
#lang rzk-1
#def prod (A B : U)
  : U
  := Σ (a : A) , B
```

```rzk template
#def forall-prod (A : U) (P Q : A → U)
  : ((x : A) → prod (P x) (Q x)) → prod ((x : A) → P x) ((x : A) → Q x)
  := ?
```

```rzk solution
#def forall-prod (A : U) (P Q : A → U)
  : ((x : A) → prod (P x) (Q x)) → prod ((x : A) → P x) ((x : A) → Q x)
  := \ k → (\ x → first (k x) , \ x → second (k x))
```

## Conclusion

The same projection trick as `distribute`, now under a binder: give each side the function that projects `k x`. "For all" commutes with "and".
