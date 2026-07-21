---
id: not-not-is-identity
title: Negating twice is the identity
statement: not (not b) = b
hints:
- text: 'Case-analyse `b` with `match`. In each branch the goal computes to a reflexivity, because `not (not …)` reduces on a concrete boolean.'
- text: 'Each branch reduces its goal to a reflexivity, so both bodies are `refl`. Fill them into `match b (…)`.'
---

The Negation section promised this: `not (not b) = b` for every boolean, once identity types are in hand. Now they are. Case-analyse `b` with `match`.

The difference from the matches in the Dependent types chapter is that the goal here mentions the very value being matched. The motive is read off the goal, abstracting `b`, so each branch is asked for the goal at *its* constructor: `not (not false) = false` and `not (not true) = true`. Both sides compute to the same boolean, so each branch is just `refl`.

Build it.

```rzk prelude
#lang rzk-1
#data Bool := false | true
#def not
  : Bool → Bool
  := \ b → match b
       ( false ⇒ true
       | true ⇒ false)
```

```rzk template
#def not-not-is-identity (b : Bool)
  : not (not b) = b
  := ?
```

```rzk solution
#def not-not-is-identity (b : Bool)
  : not (not b) = b
  := match b
       ( false ⇒ refl
       | true ⇒ refl)
```

## Conclusion

This is `match` carrying a *dependent* motive: the goal mentions the scrutinee, so each branch sees it refined at that constructor. Definitional computation then collapses both goals to a reflexivity, and `refl` closes them.
