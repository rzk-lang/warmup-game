# warmup-game

The default Rzk tutorial. An on-ramp to [Rzk](https://github.com/rzk-lang/rzk)'s type theory, played by filling holes: start from nothing, learn functions, pairs, a little logic, and identity types, and arrive at a first taste of directed types. No prior Rzk is assumed. It is the warm-up before the topic games ([yoneda-game](https://github.com/rzk-lang/yoneda-game) and others).

## How it works

The game is just data: a `game/game.yaml` table of contents and `game/levels/*` files. A level is either a puzzle (Rzk source in fenced `prelude` / `template` / `solution` blocks, plus Markdown prose) or a prose page. There is no Haskell toolchain here. [`rzk-game-action`](https://github.com/rzk-lang/rzk-game-action) fetches the prebuilt engine and bundler from a pinned [`rzk-game`](https://github.com/rzk-lang/rzk-game) release, bundles `game/` into `game.json`, assembles the static site, and `.github/workflows/deploy.yml` publishes it to GitHub Pages.

The pin lives in `deploy.yml` as the `engine-version` input. It is set to a released tag for reproducible builds; bump it to adopt a newer engine.

## Content

The chapters follow a points-to-morphisms arc. Authored so far:

- **Getting started** — how holes work (the header's ❓ link), a first trivial hole, a summary.
- **Functions** — identity, constant, composition, argument swapping, the ★ `S` combinator, and dependent application.

Later chapters (planned): propositions as types, identity types and path algebra, equivalences and univalence, sets and logic, and a closing taste of directed types.

## Playing locally

There is no build command in this repo; typechecking runs in the engine. To iterate on content off-CI, bundle `game/` from a [`rzk-game`](https://github.com/rzk-lang/rzk-game) checkout that has been built once (`make build`), then serve:

```sh
# from a rzk-game checkout
make bundle GAME=/path/to/warmup-game/game/game.yaml
make serve
```

## Authoring

Add a level by writing `game/levels/<name>.rzk.md` and referencing it from `game/game.yaml`. The `statement` and `template` hole, the `solution`, and any `inventory` must stay consistent: the solution must typecheck against the prelude and close exactly the hole the template leaves. The engine's [authoring guide](https://github.com/rzk-lang/rzk-game/blob/main/docs/authoring.md) has the file shapes and schema.
