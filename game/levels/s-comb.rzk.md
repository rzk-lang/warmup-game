---
id: s-comb
title: The S combinator
statement: A → C
hints:
- text: 'Introduce the input `x`. Both `f` and `g` will use it.'
- text: '`f` wants an `A` and a `B`. Give it `x`, and get the `B` from `g x`: `f x (g x)`.'
---

The `S` combinator is a classic: given `f : A → B → C` and `g : A → B`, it feeds one shared input to both. Together with the constant function it can express every other combinator, which is how variable binding can be translated away entirely.

Build it.

```rzk prelude
#lang rzk-1
```

```rzk template
#def s-comb (A B C : U) (f : A → B → C) (g : A → B)
  : A → C
  := ?
```

```rzk solution
#def s-comb (A B C : U) (f : A → B → C) (g : A → B)
  : A → C
  := \ x → f x (g x)
```

## Conclusion

`S` shares one argument between two functions. The constant function of the previous level is its partner `K`.
