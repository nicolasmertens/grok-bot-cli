# Nick's fork of grok-bot-cli

Upstream: ScriptedAlchemy/grok-bot-cli. Kept close to upstream on purpose (JS, not a rewrite) so upstream releases merge cleanly.

## Patches on top of upstream
- `nick/descriptor-v3` (2026-10-06): accept Grok Bot gateway descriptor v3 (same entries layout as v2 plus `savedAtMs`; payload adds `vncProxy`, ignored). Multiple saved entries still fail AMBIGUOUS_ENTRIES on purpose (may be different accounts, see upstream issue #102). Same change offered upstream as branch `upstream-pr/descriptor-v3`.

## Install on a Mac
    npm ci && npm run build && npm pack && npm install -g ./grok-bot-cli-<version>.tgz
Check: `gbot --version` ends in `-nick.N`; `gbot bots list --json` lists the bots.

## Sync with upstream
    git fetch upstream && git merge upstream/main   # then rebuild, test, bump -nick.N, reinstall
Note: a plain `npm install -g grok-bot-cli` puts upstream back and breaks v3 until upstream supports it.
