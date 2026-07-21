---
id: type-formers-intro
title: Type formers
role: bridge-in
---

Every type former in Rzk is fixed by a small set of rules, and it is worth seeing them laid out. Compare the product `prod A B` with the function type `A → B`:

- **Formation** — when is it a type? `prod A B` is a type whenever `A` and `B` are types; likewise `A → B` is a type whenever `A` and `B` are types.
- **Constructors** (introduction rules) — how do you build a value? A pair `(a , b)` is a value of `prod A B` whenever `a : A` and `b : B`; a λ-abstraction `\ x → e` is a value of `A → B` whenever `e : B` for every `x : A`.
- **Eliminators** (elimination rules) — how do you use one? The projections `first z` and `second z` take a `prod A B` apart; application `f x` uses an `A → B`.

The eliminators come with **computation** rules that tie them to the constructors: `first (a , b)` is `a`, `second (a , b)` is `b`, and `(\ x → e) a` is `e` with `a` substituted for `x`.

Elimination can also be packaged as a single principle. The **recursion principle** defines a function *out of* a type into any other type; the **induction principle** is its dependent version, defining a dependent function. For a pair, both come down to one move: match it as `\ (a , b) → …`, naming the two components at once. There is also a **uniqueness** principle, that every pair equals `(first z , second z)`; it needs identity types, and in Rzk it holds on the nose.

*By the end of this section you will be able to:* state the recursion and induction principles for products by pattern-matching on a pair.

*Further reading:* the [HoTT Book](https://homotopytypetheory.org/book/), §1.5.
