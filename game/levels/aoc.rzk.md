---
id: aoc
title: The axiom of choice
statement: 'Σ (f : A → B) , (x : A) → R x (f x)'
hints:
- text: 'The result is a pair: the choice function, then the proof it works. Build `( ? , ? )`.'
- text: 'Build the pair whose function picks the first component of `g a`, and whose proof reads off the second.'
---

From `g`, which for each `x` gives a `y : B` together with a proof of `R x y`, build a single choice function `f : A → B` and a proof that `R x (f x)` holds for every `x`. Everything is pairing and projection.

Build it.

```rzk prelude
#lang rzk-1
```

```rzk template
#def ac (A B : U) (R : A → B → U) (g : (x : A) → Σ (y : B) , R x y)
  : Σ (f : A → B) , (x : A) → R x (f x)
  := ?
```

```rzk solution
#def ac (A B : U) (R : A → B → U) (g : (x : A) → Σ (y : B) , R x y)
  : Σ (f : A → B) , (x : A) → R x (f x)
  := ( \ a → first (g a) , \ x → second (g x))
```

## Conclusion

The choice function is `\ a → first (g a)`, and its correctness is `\ x → second (g x)`. In type theory, "for all `x` there exists `y`" already contains the choice function; extracting it is just projection.
