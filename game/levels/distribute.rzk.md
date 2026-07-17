---
id: distribute
title: Distributing over "and"
statement: '(f : A → prod B C) → prod (A → B) (A → C)'
hints:
- text: 'Introduce `f`, then build a pair `(? , ?)` of two functions.'
- text: 'Each side takes an `a` and projects `f a`: write `(\ a → first (f a) , \ a → second (f a))`.'
---

A function into a conjunction splits into two functions. Given `f` that proves `B` and `C` together from any `A`, build the pair of `A → B` and `A → C`.

Build it.

```rzk prelude
#lang rzk-1
#def prod (A B : U)
  : U
  := Σ (a : A) , B
```

```rzk template
#def distribute (A B C : U)
  : (f : A → prod B C) → prod (A → B) (A → C)
  := ?
```

```rzk solution
#def distribute (A B C : U)
  : (f : A → prod B C) → prod (A → B) (A → C)
  := \ f → (\ a → first (f a) , \ a → second (f a))
```

## Conclusion

Distributing over a conjunction means projecting the result of `f` on each side.
