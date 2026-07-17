---
id: compose
title: Composition
statement: A → C
hints:
- text: 'Introduce the input `x`. The goal becomes `C`.'
- text: 'You have no `C` at hand, but `g` makes one from a `B`, and `f` makes a `B` from `x`. Chain them: `g (f x)`.'
---

Composition chains two functions: from `f : A → B` and `g : B → C`, build a function `A → C` that runs each input through `f` and then `g`. It is the most-used construction in all of type theory.

Build it.

```rzk prelude
#lang rzk-1
```

```rzk template
#def compose (A B C : U) (g : B → C) (f : A → B)
  : A → C
  := ?
```

```rzk solution
#def compose (A B C : U) (g : B → C) (f : A → B)
  : A → C
  := \ x → g (f x)
```

## Conclusion

Composition is nested application: run `f` first, then `g` on its result.
