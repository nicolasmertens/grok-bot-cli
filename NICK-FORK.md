# Nick's fork of grok-bot-cli

Upstream: ScriptedAlchemy/grok-bot-cli. Kept close to upstream on purpose (JS, not a rewrite) so upstream releases merge cleanly.

## Patches on top of upstream
- `nick/descriptor-v3` (2026-10-06): accept Grok Bot gateway descriptor v3 (same entries layout as v2 plus `savedAtMs`; payload adds `vncProxy`, ignored). With several saved entries, use the newest `savedAtMs` instead of failing AMBIGUOUS_ENTRIES. Fixed the fleet's Grok Bot thread capture (agent-session-shipper "gbot: JSONDecodeError").

## Install on a Mac
    npm ci && npm run build && npm pack && npm install -g ./grok-bot-cli-<version>.tgz
Check: `gbot --version` ends in `-nick.N`; `gbot bots list --json` lists the bots.

## Sync with upstream
    git fetch upstream && git merge upstream/main   # then rebuild, test, bump -nick.N, reinstall
Note: a plain `npm install -g grok-bot-cli` puts upstream back and breaks v3 until upstream supports it.
