---
id: uncurry
title: Uncurrying
statement: 'prod A B → C'
hints:
- text: 'Introduce the pair; call it `p`. The goal becomes `C`.'
- text: 'Feed the two components of `p` to `f` one at a time: write `f (first p) (second p)`.'
---

The reverse of currying. Given a two-argument function `f`, build the version that takes a single pair and passes its components along.

Build it.

```rzk prelude
#lang rzk-1
#def prod (A B : U)
  : U
  := Σ (a : A) , B
```

```rzk template
#def uncurry (A B C : U) (f : A → B → C)
  : prod A B → C
  := ?
```

```rzk solution
#def uncurry (A B C : U) (f : A → B → C)
  : prod A B → C
  := \ p → f (first p) (second p)
```

## Conclusion

Uncurrying projects the pair and applies `f` to the pieces. With currying, it shows that a function on pairs and a two-argument function are interchangeable.
