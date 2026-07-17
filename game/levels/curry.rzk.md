---
id: curry
title: Currying
statement: '(a : A) → (b : B) → C'
hints:
- text: 'Introduce both arguments `a` and `b`. The goal becomes `C`.'
- text: 'Now `f` wants a single pair. Build it from `a` and `b`: write `f (a , b)`.'
---

A function on pairs and a two-argument function carry the same information. Given `f` that takes one pair, build the version that takes the two components separately.

Build it.

```rzk prelude
#lang rzk-1
#def prod (A B : U)
  : U
  := Σ (a : A) , B
```

```rzk template
#def curry (A B C : U) (f : prod A B → C)
  : (a : A) → (b : B) → C
  := ?
```

```rzk solution
#def curry (A B C : U) (f : prod A B → C)
  : (a : A) → (b : B) → C
  := \ a b → f (a , b)
```

## Conclusion

Currying feeds the two arguments to `f` as a pair. This is the same currying you met for functions, now crossing the product.
