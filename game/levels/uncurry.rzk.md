---
id: uncurry
title: Uncurrying
statement: 'prod A B → C'
hints:
- text: 'Introduce the pair; call it `p`. The goal becomes `C`.'
- text: 'Feed the two projections of `p` to `f`, one argument at a time.'
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

Rzk also lets a lambda take the pair apart as it binds it, writing `\ (a , b) → f a b` instead of projecting `p` twice. That notation comes into its own with the induction principle for products, a few levels on.
