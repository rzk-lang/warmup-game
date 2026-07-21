---
id: const
title: The constant function
statement: B → A
hints:
- text: 'Introduce the argument (the introduction move, or `\ ... → ?` by hand), even though you will not use it.'
- text: 'Introduce the argument, discard it with `_`, and return `x`.'
---

A constant function ignores its input and always returns the same value. You are given `x : A`; produce a function that returns `x` no matter what it is fed.

Build it.

```rzk prelude
#lang rzk-1
```

```rzk template
#def const (A B : U) (x : A)
  : B → A
  := ?
```

```rzk solution
#def const (A B : U) (x : A)
  : B → A
  := \ _ → x
```

## Conclusion

A constant function discards its input. The underscore `_` names an argument you do not intend to use.
