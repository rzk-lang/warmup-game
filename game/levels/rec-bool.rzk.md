---
id: rec-bool
title: The recursion principle for booleans
statement: Bool → C
inventory:
- name: ind-Bool
  synopsis: case analysis on a boolean (its induction principle)
hints:
- text: 'Use `ind-Bool` with a constant motive `\ _ → C`, then the two values.'
- text: 'Write `ind-Bool (\ _ → C) f t`.'
---

Define a function out of `Bool` by giving its value on `false` and on `true`. Derive recursion from `ind-Bool`.

Build it.

```rzk prelude
#lang rzk-1
#postulate Bool : U
#postulate false : Bool
#postulate true : Bool
#postulate ind-Bool
  ( C : Bool → U)
  ( f : C false)
  ( t : C true)
  : (z : Bool) → C z
```

```rzk template
#def rec-Bool (C : U) (f t : C)
  : Bool → C
  := ?
```

```rzk solution
#def rec-Bool (C : U) (f t : C)
  : Bool → C
  := ind-Bool (\ _ → C) f t
```

## Conclusion

A boolean is used by choosing between two values. Recursion is induction with a constant motive, exactly as for the coproduct.
