---
id: self-check
statement: hom A x x
title: Self-check
---

A pre-test. It doubles as a self-assessment: solve it to show you are ready, or tap "I already know this" to skip ahead. Either way it satisfies the prerequisite on the next level.

If you get stuck, the level offers **remedies** — labelled pointers back into the game or out to the web. They are set on the puzzle in `game.yaml`, not in this file.

This one is the identity again, so it is a quick check rather than a new idea.

```rzk prelude
#lang rzk-1
#def Δ¹
  : 2 → TOPE
  := \ t → TOP
#def hom (A : U) (x y : A)
  : U
  := (t : Δ¹) → A [ t ≡ 0₂ ↦ x , t ≡ 1₂ ↦ y ]
```

```rzk template
#def self-check (A : U) (x : A)
  : hom A x x
  := ?
```

```rzk solution
#def self-check (A : U) (x : A)
  : hom A x x
  := \ t → x
```

## Conclusion

Cleared. The next level was locked behind this one; it is now open.
