# Tau plugin marketplace

> Tau is code-CAD: a parametric model is code (replicad, OpenSCAD, JSCAD, Manifold, PicoVoxel, SMLib, tscircuit, build123d or PicoGK) and Tau evaluates it, checks its geometry with GeoSpec tests, renders screenshots and exports STEP, STL, 3MF or glTF. This repository holds the two catalog files that install the plugin, [`@taucad/agent-plugin`](https://www.npmjs.com/package/@taucad/agent-plugin), from npm into Claude Code and Codex. The full agent-facing guide is https://taucad.dev/llms.txt.

## Install

Needs Node.js 24 or later with its npm 11. Install the Tau CLI first; the plugin starts it:

```sh
npm install -g @taucad/cli@beta
```

Claude Code 2.1.275 or later: `claude plugin install tau --marketplace taucad/marketplace`. Older: `claude plugin marketplace add taucad/marketplace`, then `claude plugin install tau@taucad`.

Codex (no one-step form): `codex plugin marketplace add taucad/marketplace`, then `codex plugin add tau@taucad`.

Start a new session or thread afterwards. The plugin is not in the Anthropic or OpenAI plugin directories.

## Check

- Claude Code: `claude plugin list` shows `tau@taucad` enabled; `claude mcp list` shows `plugin:tau:tau … ✔ Connected`.
- Codex: `codex plugin list` shows `tau@taucad  installed, enabled`.

Troubleshooting, which kernel to use and what to tell the user: https://taucad.dev/llms.txt.

## Moving from `taucad/tau`

If `marketplace add` says `taucad` already exists with another source: `claude plugin marketplace remove taucad` (if it says not found, delete `extraKnownMarketplaces.taucad` from `~/.claude/settings.json`), then add it again. Codex: `codex plugin marketplace remove taucad`, delete `[plugins."tau@taucad"]` from `~/.codex/config.toml` if it remains, then add it again.

## Files

- `.claude-plugin/marketplace.json`: the Claude Code catalog.
- `.agents/plugins/marketplace.json`: the Codex catalog.

Both name the marketplace `taucad` and the plugin `tau`. Source and issues live in [taucad/tau](https://github.com/taucad/tau).
