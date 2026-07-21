---
id: quantifiers-intro
title: Quantifiers
role: bridge-in
---

The quantifiers are the dependent versions of conjunction and disjunction. **For all** `x`, `P x` is the dependent function type `(x : A) → P x`: a proof produces a proof of `P x` for every `x`. **There exists** an `x` with `P x` is the Σ-type `Σ (x : A) , P x`: a proof is a witness `x` paired with a proof of `P x`.

The same Rosetta stone as the start of this section, restricted to the quantifiers:

| English | Logic | Rzk |
| --- | --- | --- |
| for all `x`, `P x` | ∀`x`. `P x` | `(x : A) → P x` |
| there is an `x` with `P x` | ∃`x`. `P x` | `Σ (x : A) , P x` |

When `P` does not depend on `x`, these collapse to connectives you already know: `(x : A) → P` is implication `A → P`, and `Σ (x : A) , P` is conjunction `prod A P`. The quantifiers are what you get by letting the second component depend on the first.

The laws you proved for conjunction have quantified counterparts. Here you distribute a function over a conjunction, first in the propositional form and then in the "for all" form.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.11.
