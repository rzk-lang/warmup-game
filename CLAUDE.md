# CLAUDE.md

Guidance for Claude Code (claude.ai/code) when working in this repository.

## What this repo is

The **warm-up game**: the default Rzk tutorial, an on-ramp to Rzk's type theory
played by filling holes. It is **content, not code** — there is no Haskell
toolchain here. The prebuilt [`rzk-game`](https://github.com/rzk-lang/rzk-game)
engine and bundler are fetched at build time by
[`rzk-game-action`](https://github.com/rzk-lang/rzk-game-action), pinned via
`engine-version` in `.github/workflows/deploy.yml`.

It is the warm-up before the topic games (yoneda-game, and the future
modal-game / diruniv-game). Local planning notes live in the gitignored
`notes/` (`notes/plan.md`, `notes/conventions.md`).

## Structure

The game is data under `game/`:

- `game/game.yaml` — table of contents: `chapters[].sections[].items[]`, each
  item a `prose:` page or a `puzzle:` level. Roles (`extra`, `pretest`) and
  `prereqs`/`remedies` are set here.
- `game/levels/*` — prose (`.md`) and puzzles (`.rzk.md`). A puzzle carries
  front-matter (`id`, `title`, `statement`, optional `hints`, `inventory`,
  `forbidden`, `gated`) and three fenced blocks: ` ```rzk prelude ` (read-only,
  concatenated in order, first line `#lang rzk-1`), ` ```rzk template ` (the
  hole `?`), ` ```rzk solution `. A `## Conclusion` shows on success.

## Chapters

Points-to-morphisms arc. Authored: **Getting started**, **Functions**. Planned:
pairs (Σ), propositions as types, identity types, a taste of HoTT, a taste of
directed types. See `notes/plan.md`.

## Playtest locally

Typechecking runs in the engine, not here. From a `rzk-game` checkout built once
with `make build` (needs the wasm toolchain; the built `public/` can be reused):

```sh
# from the rzk-game checkout
make bundle GAME=/path/to/warmup-game/game/game.yaml   # -> public/game.json
node loadtest.mjs                                       # headless: load + play in wasm
make serve                                              # play in a browser
```

`make bundle` needs a native GHC ≥ 9.8 (`base ≥ 4.19`, for rzk's free-foil).
`rzk typecheck` on a scratch `.rzk` file is the quickest way to check a solution
term in isolation.

## Conventions (see `notes/conventions.md` for the full version)

- **American spelling.** No em-dash chains (two sentences, a colon, or
  parentheses instead).
- **Two prose registers.** Section prose (`bridge-in`, `summary`) sets up and
  reflects. Puzzle prose is short, second person, ends with a call to action;
  the takeaway goes under `## Conclusion`. Do not restate the goal type.
- **One hole per level.** Honest goal types (only the intended term fits).
- **Hints general to specific, revealed incrementally**; never give the whole
  term at once. `when-goal` only when the post-move goal is distinctive.
- **Postulate constraint.** Rzk natively has Π, Σ/×, `Unit`, identity types;
  **not** `Void`, `coprod`, `Nat`, funext, univalence. Keep content in the
  native fragment; never present a postulated type as if Rzk has it.
- **Naming.** `id`, `#def` name, and file stem coincide in the early chapters.
  The closing directed chapter follows sHoTT names (`hom`, `id-hom`, `Δ¹`).

## Workflow

Feature branch + PR; do not push to `main`. One-line commit messages in this
repo. Nikolai opens the PRs.
