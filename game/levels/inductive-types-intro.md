---
id: inductive-types-intro
title: Coproducts, booleans, natural numbers
role: bridge-in
---

Your first **inductive types**. Each is declared with the **`#data` command**, which generates the type's eliminators for you, and you take a value apart with **`match`** — one branch per constructor, the multi-constructor generalization of the pair pattern from Type formers. Here you build three: coproducts (with the empty type), booleans, and the natural numbers.

*By the end of this section you will be able to:* eliminate the empty type and swap a coproduct, define negation and conjunction on booleans, and double and add natural numbers.
