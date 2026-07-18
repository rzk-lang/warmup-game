---
id: not
title: Negation
statement: Bool → Bool
inventory:
- name: rec-Bool
  synopsis: recursion on a boolean (choose a value for false and for true)
- name: 'true'
  synopsis: the boolean true
- name: 'false'
  synopsis: the boolean false
- name: Bool
  synopsis: the type of booleans
hints:
- text: '`rec-Bool` takes the result type, then the value for `false`, then the value for `true`.'
- text: 'Negation sends `false` to `true` and `true` to `false`: write `rec-Bool Bool true false`.'
---

Negation swaps `true` and `false`. Build it with `rec-Bool`.

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
#def rec-Bool (C : U) (f t : C)
  : Bool → C
  := ind-Bool (\ _ → C) f t
```

```rzk template
#def not
  : Bool → Bool
  := ?
```

```rzk solution
#def not
  : Bool → Bool
  := rec-Bool Bool true false
```

## Conclusion

Negation is recursion returning the *other* value in each case. Proving that `not` is its own inverse, `not (not b) = b`, needs identity types and the (postulated, weak) computation rules, so it waits for a later chapter.
