---
id: quantifiers-intro
title: Quantifiers
role: bridge-in
---

The quantifiers are the dependent versions of conjunction and disjunction. **For all** `x`, `P x` is the dependent function type `(x : A) → P x`: a proof produces a proof of `P x` for every `x`. **There exists** an `x` with `P x` is the Σ-type `Σ (x : A) , P x`: a proof is a witness `x` paired with a proof of `P x`.

The laws you proved for conjunction have quantified counterparts. Here you distribute a function over a conjunction, first in the propositional form and then in the "for all" form.

*By the end of this section you will be able to:* show that implication distributes over conjunction, and that "for all" distributes over conjunction.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.11.
