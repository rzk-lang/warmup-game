---
id: rec-prod
title: The recursion principle for products
statement: prod A B → C
hints:
- text: 'Introduce a pair and name both components at once by pattern-matching: `\ (a , b) → ?`.'
- text: 'Now `a : A` and `b : B` are in scope; combine them with `f`: write `\ (a , b) → f a b`.'
---

The **recursion principle** for products: to define a function out of `prod A B` into any type `C`, it is enough to say what to do with the two components. You are given `f : A → B → C`; turn it into a function on pairs.

Build it.

```rzk prelude
#lang rzk-1
#def prod (A B : U)
  : U
  := Σ (a : A) , B
```

```rzk template
#def rec-prod (A B C : U) (f : A → B → C)
  : prod A B → C
  := ?
```

```rzk solution
#def rec-prod (A B C : U) (f : A → B → C)
  : prod A B → C
  := \ (a , b) → f a b
```

## Conclusion

Pattern-matching `\ (a , b) → …` names both components of the pair, and `f` combines them. That is the recursion principle for products.
