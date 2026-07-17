PR: https://github.com/rzk-lang/rzk-game-template/pull/new/adopt-v0.3.0

# Adopt the v0.3.0 engine and its authoring features

The 0.3.0 game spec is a breaking change, so the template migrates to it and showcases what it adds (the template exists to demonstrate the authoring surface, so it should use every feature, not merely keep building).

Migration: the table of contents moves from a flat `sections:` list to `chapters:` (an untitled first chapter renders at the top level; the second is titled), and inventories move from `name : type` strings to structured entries — dropping the old lines for the parameter `x` and the `λ-intro` action, which are no longer inventory entries.

Showcase: a `how-holes-work` page (lights up the header ❓ link); a structured inventory entry with a `type` override on the gated level; and a `forbidden` move (`recOR`) banning a built-in eliminator the inventory cannot reach. Prose, README, and the `engine-version` pin (→ v0.3.0) updated to match.

Verified by bundling under the v0.3.0 engine and playing every level headlessly (`loaded-play: OK`).
