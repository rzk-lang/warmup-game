---
id: first-hole
title: Your first hole
statement: A
hints:
- text: 'You are given a value `x : A`, and the goal asks for an `A`. Hand it back.'
---

This is your first definition to finish. It is handed a type `A` and a value `x : A`, and its goal is to produce something of type `A`. Look at what the context gives you, and fill the hole with something that fits.

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
