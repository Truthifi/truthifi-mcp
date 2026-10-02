# Rules for agents editing this repository

- Docs and configuration only. Never add runnable server code, secrets, keys, internal URLs, ticket IDs or customer data.
- Any tool change: update `docs/tools.json`, `docs/tools.md`, the README tools table and `lhm.plugin.json` in the same commit, from the live tool list (https://truthifi.com/mcp-tools).
- State the tool count from `docs/tools.json`. Never hard-code a new count elsewhere without updating `tools.json` in the same commit.
- Keep `version` equal across `plugin.json`, `.claude-plugin/plugin.json`, `.claude-plugin/marketplace.json` (`metadata.version`), `.cursor-plugin/plugin.json`, `gemini-extension.json`, `lhm.plugin.json` and each `skills/*/SKILL.md` (`metadata.version`); the `validate` workflow checks this. `server.json` carries the registry version.
- Keep the name ("Truthifi"), description, website (https://truthifi.com/features/mcp) and endpoint identical everywhere.
- Quote every YAML `description` in `skills/*/SKILL.md`.
- Don't describe Truthifi as "read-only" without saying what is read-only (access to the user's bank and brokerage accounts). Three tools change data inside Truthifi.
- Run the `validate` workflow (push to a branch) before opening a PR.
