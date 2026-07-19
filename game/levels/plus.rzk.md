---
id: plus
title: Addition
statement: ℕ
hints:
- text: 'Recurse on `m` with `rec-ℕ`. The base returns `n`, and each step adds one to the running result.'
- text: 'Write `rec-ℕ ℕ n (\ _ ih → succ ih) m`.'
---

Addition by recursion on the first argument: `plus zero n` is `n`, and `plus (succ m) n` is one more than `plus m n`. Build it with `rec-ℕ`.

Build it.

```rzk prelude
#lang rzk-1
#data ℕ := zero | succ (n : ℕ)
```

```rzk template
#def plus (m n : ℕ)
  : ℕ
  := ?
```

```rzk solution
#def plus (m n : ℕ)
  : ℕ
  := rec-ℕ ℕ n (\ _ ih → succ ih) m
```

## Conclusion

Recursion on `m`: the base returns `n`, and each `succ` adds one to the running total `ih`. That is addition, and it computes definitionally.
