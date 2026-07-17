---
id: first-hole
title: Your first hole
statement: A
hints:
- text: 'You are given a value `x : A`, and the goal asks for an `A`. Hand it back.'
---

The simplest possible proof: you are handed a value and asked for one of the same type. Read the context, find what fits the goal, and return it.

Fill it.

```rzk prelude
#lang rzk-1
```

```rzk template
#def first-hole (A : U) (x : A)
  : A
  := ?
```

```rzk solution
#def first-hole (A : U) (x : A)
  : A
  := x
```

## Conclusion

A hole is filled by any value of its goal type. Here the context already held one, so nothing had to be built.
