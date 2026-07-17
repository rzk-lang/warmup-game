# rzk-game-template

A starter [`rzk-game`](https://github.com/rzk-lang/rzk-game) game, ready to fork. It is a small but complete game over the `hom A x x` substrate, with one of each item type, so each level can be read and copied. Fork it, edit `game/`, and get a live site.

## How it works

The game is just data: a `game/game.yaml` table of contents and `game/levels/*` files. A level is either a puzzle (Rzk source in fenced `prelude` / `template` / `solution` blocks, plus Markdown prose) or a prose page. There is no Haskell toolchain here — [`rzk-game-action`](https://github.com/rzk-lang/rzk-game-action) fetches the prebuilt engine and bundler from a pinned [`rzk-game`](https://github.com/rzk-lang/rzk-game) release, bundles `game/` into `game.json`, assembles the static site, and `.github/workflows/deploy.yml` publishes it to GitHub Pages.

The pin lives in `deploy.yml` as the `engine-version` input. It is set to a released tag for reproducible builds; bump it to adopt a newer engine.

## What's inside

Two chapters cover the full authoring surface — the first untitled (its sections render at the top level), the second titled "More moves":

- **Getting started** — a `how-holes-work` page (which lights up the header's ❓ link), a bridge-in and an outcomes page, an identity puzzle carrying hints (one plain, one contextual), a self-check pre-test with remedies, a follow-on puzzle gated behind the pre-test, and a summary.
- **Gating and a bonus** — a mid-section note, a single gated puzzle that exercises the whole gate (a structured inventory with a `type` override, a `forbidden` built-in `idJ`, an ungranted shortcut, and a multi-block prelude), an optional ★ bonus, and a closing summary.

See the engine's [authoring guide](https://github.com/rzk-lang/rzk-game/blob/main/docs/authoring.md) for the file shapes, the schema, and the how-tos.

## Forking this template

Two things make a fork live:

1. **Edit `game/`.** Replace the table of contents and levels with your own. Keep the `game/levels/` layout and the front-matter shapes.
2. **Enable Pages.** After the first push to `main` deploys, set the repository's Pages source to the `gh-pages` branch (Settings → Pages). The site then goes live at the repository's Pages URL.
