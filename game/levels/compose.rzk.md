---
id: compose
title: Composition
statement: A → C
hints:
- text: 'Introduce the input `x`. The goal becomes `C`.'
- text: 'You have no `C` at hand, but `f` makes a `B` from `x`, and `g` makes a `C` from a `B`. After introducing `x`, chain the two.'
---

Composition chains two functions: from `f : A → B` and `g : B → C`, build a function `A → C` that runs each input through `f` and then `g`.

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
