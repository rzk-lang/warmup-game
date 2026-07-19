---
id: pair-path
title: Paths between pairs (★)
statement: 'prod (first x = first y) (second x = second y)'
hints:
- text: 'The projections `first` and `second` are functions, so `ap` carries a path of pairs to a path in each component.'
- text: 'Apply `ap` to each projection and pair the results: write `(ap (prod A B) A (\ z → first z) x y p , ap (prod A B) B (\ z → second z) x y p)`.'
---

A path between pairs gives a path between each pair of components. From `p : x = y` in `prod A B`, extract the two component paths by applying `ap` to the projections.

Build it.

```rzk prelude
#lang rzk-1
#def ind-path
  ( A : U) (a : A)
  ( C : (x : A) → (a = x) → U)
  ( d : C a refl)
  ( x : A) (p : a = x)
  : C x p
  := idJ (A , a , C , d , x , p)
#def ap (A B : U) (f : A → B) (x y : A) (p : x = y)
  : f x = f y
  := ind-path A x (\ w _ → f x = f w) refl y p
#def prod (A B : U)
  : U
  := Σ (a : A) , B
```

```rzk template
#def pair-path (A B : U) (x y : prod A B) (p : x = y)
  : prod (first x = first y) (second x = second y)
  := ?
```

```rzk solution
#def pair-path (A B : U) (x y : prod A B) (p : x = y)
  : prod (first x = first y) (second x = second y)
  := (ap (prod A B) A (\ z → first z) x y p , ap (prod A B) B (\ z → second z) x y p)
```

## Conclusion

Each projection is a function, so `ap` carries a path of pairs to a path in each component. The converse, rebuilding a path of pairs from two component paths, is the harder half of characterising equality of pairs.
