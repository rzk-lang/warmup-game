---
id: rev-partial
title: Reversal, without naming the path
statement: (x = y) → y = x
inventory:
- name: ind-path
  synopsis: 'path induction: reduces a goal about a path to the refl case'
hints:
- text: '`ind-path` takes its path last. Stop before that argument and what is left is a function waiting for one.'
- text: 'The motive and the base case are the ones you used in `rev`. The only new thing is where to stop: give `ind-path` five arguments, not six.'
---

You proved `rev` by applying `ind-path` to a path you had been handed. This time no path is handed to you.

You could introduce one yourself and finish as before. Do not. Note instead that the path is the last argument `ind-path` takes, so leaving it off already gives a function expecting exactly one. Build the reversal that way.

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
```

```rzk template
#def rev-partial (A : U) (x y : A)
  : (x = y) → y = x
  := ?
```

```rzk solution
#def rev-partial (A : U) (x y : A)
  : (x = y) → y = x
  := ind-path A x (\ w _ → w = x) refl y
```

## Conclusion

An eliminator is an ordinary function, so it can be applied to some of its arguments and left waiting for the rest. Stopping one argument early turns `ind-path` from a proof about a given path into the function that reverses any path — the same term, read as a map instead of as an induction.
