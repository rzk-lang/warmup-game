---
id: undistribute
title: Undistributing
statement: '(p : prod (A → B) (A → C)) → (a : A) → prod B C'
hints:
- text: 'Introduce the pair `p` and the argument `a`. The goal becomes a pair.'
- text: 'Apply each component of `p` to `a`: write `(first p a , second p a)`.'
---

The converse of the previous level. Given proofs of `A → B` and `A → C`, build a proof that `A` implies both `B` and `C`.

Build it.

```rzk prelude
#lang rzk-1
#def prod (A B : U)
  : U
  := Σ (a : A) , B
```

```rzk template
#def undistribute (A B C : U)
  : (p : prod (A → B) (A → C)) → (a : A) → prod B C
  := ?
```

```rzk solution
#def undistribute (A B C : U)
  : (p : prod (A → B) (A → C)) → (a : A) → prod B C
  := \ p a → (first p a , second p a)
```

## Conclusion

Together with the previous level, this shows the two forms prove each other: `A → prod B C` and `prod (A → B) (A → C)` are logically equivalent.
