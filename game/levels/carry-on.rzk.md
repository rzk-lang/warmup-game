---
id: carry-on
inventory:
- name: id-hom
  synopsis: the identity morphism at a point
statement: hom A x x
title: Carry on
---

This level was locked until the self-check was satisfied. That is a **prerequisite**: it is listed on this puzzle in `game.yaml` as `prereqs: [self-check]`, so the level only unlocks once the pre-test is cleared.

The goal is the identity again, but now the prelude grants you `id-hom`. Reach for the lemma instead of building the path by hand.

```rzk prelude
#lang rzk-1
#def Δ¹
  : 2 → TOPE
  := \ t → TOP
#def hom (A : U) (x y : A)
  : U
  := (t : Δ¹) → A [ t ≡ 0₂ ↦ x , t ≡ 1₂ ↦ y ]
#def id-hom (A : U) (x : A)
  : hom A x x
  := \ t → x
```

```rzk template
#def carry-on (A : U) (x : A)
  : hom A x x
  := ?
```

```rzk solution
#def carry-on (A : U) (x : A)
  : hom A x x
  := id-hom A x
```

## Conclusion

Reusing a granted lemma is the usual move once the basics are in hand. The inventory here only informs; the next level makes it binding.
