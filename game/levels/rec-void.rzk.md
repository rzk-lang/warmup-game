---
id: rec-void
title: From falsity, anything
statement: Void → C
inventory:
- name: ind-Void
  synopsis: the induction principle for the empty type
hints:
- text: 'Recursion is the non-dependent case of induction. Feed `ind-Void` a constant motive.'
- text: 'The motive ignores its argument and returns `C`: write `ind-Void (\ _ → C)`.'
---

The empty type `Void` has no values, so from one you may conclude anything. Derive its recursion principle from the induction principle `ind-Void`.

Build it.

```rzk prelude
#lang rzk-1
#postulate Void : U
#postulate ind-Void
  ( C : Void → U)
  : (z : Void) → C z
```

```rzk template
#def rec-Void (C : U)
  : Void → C
  := ?
```

```rzk solution
#def rec-Void (C : U)
  : Void → C
  := ind-Void (\ _ → C)
```

## Conclusion

Recursion is induction with a constant motive. From `Void`, every type follows: this is *ex falso quodlibet*.
