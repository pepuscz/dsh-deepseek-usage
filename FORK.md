# Compact usage UI fork

Upstream: https://github.com/dougen/dsh-deepseek-usage (MIT).
Baseline: v0.20.0, commit 87c7e2d (see Git ancestry for full SHA).

This fork replaces subscription gauges with a quiet inline quota summary with
explicit percentages; provider names are in tooltips. Reset times remain in tooltips.
Provider requests, settings, package identity and host API retain upstream compatibility.
Claude and Codex reuse existing DSH llm-pi-ai logins when no explicit usage token is set.
The owning DSH provider handles token refresh; this plugin never copies or refreshes tokens.
Expired saved logins are rejected. Standalone CLI installations alone are not imported.

## Upstream updates

Keep `upstream` pointing to dougen/dsh-deepseek-usage. Fetch upstream and merge
its reviewed release tag into this fork, resolve the small client UI delta,
then run `npm test` and visually check the original DSH app. Do not blindly
update the installed package from npm: that replaces the fork with upstream.
Install reviewed immutable Git snapshots and retain their SHA-256 archive checksum.
Compatibility is maintained by a small patch, not guaranteed for future breaking releases.

The package keeps its upstream name so existing DSH configuration and credentials
continue to work. This fork is installed from Git snapshots, not published to npm.
No runtime data or credentials belong in this repository.
