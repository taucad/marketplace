# Tau plugin marketplace

Catalogs for the Tau code-CAD plugin in Claude Code and Codex. The plugin itself installs from npm as [`@taucad/agent-plugin`](https://www.npmjs.com/package/@taucad/agent-plugin); this repository holds only the two catalog files, so adding the marketplace is a small clone.

## Install

Claude Code:

```sh
claude plugin marketplace add taucad/marketplace
claude plugin install tau@taucad
```

Codex:

```sh
codex plugin marketplace add taucad/marketplace
codex plugin add tau@taucad
```

Node 24 with npm 11 is the supported path; npm 10 fails on this dependency graph. See the [plugin README](https://github.com/taucad/tau/tree/main/packages/agent-plugin#readme) for setup and troubleshooting.

## Files

- `.claude-plugin/marketplace.json`: the Claude Code catalog.
- `.agents/plugins/marketplace.json`: the Codex catalog.

Both name the marketplace `taucad` and the plugin `tau`. Source and issues live in [taucad/tau](https://github.com/taucad/tau).
