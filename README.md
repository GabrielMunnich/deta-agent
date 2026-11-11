# Deta for coding agents

This plugin teaches coding agents to work in [Deta](https://www.deta.studio), the drawing review and takeoff app for architecture, engineering and construction. Agents use the Deta CLI to read and edit drawing markups, takeoff tables, page scales and product libraries with your own Deta sign-in.

## Install

| Tool | Command |
| :-- | :-- |
| Claude Code | `claude plugin marketplace add GabrielMunnich/deta-agent && claude plugin install deta@deta` |
| Codex | `codex plugin marketplace add GabrielMunnich/deta-agent && codex plugin add deta@deta` |
| Gemini CLI | `gemini extensions install https://github.com/GabrielMunnich/deta-agent` |
| Antigravity | `agy plugin install https://github.com/GabrielMunnich/deta-agent` |

Requirements: Node 20+.

## Maintainers

One skill, `skills/deta/SKILL.md`, serves every tool. Each manifest finds it in the default `skills/` folder.

| Tool | Manifest | Format from |
| :-- | :-- | :-- |
| Claude Code | `.claude-plugin/plugin.json`, `.claude-plugin/marketplace.json` | https://code.claude.com/docs/en/plugins-reference, https://code.claude.com/docs/en/plugin-marketplaces, https://code.claude.com/docs/en/plugins/marketplace-reference |
| Codex | `plugin.json`, `.agents/plugins/marketplace.json` | https://developers.openai.com/codex/plugins/build |
| Gemini CLI | `gemini-extension.json` | https://geminicli.com/docs/extensions/reference/ |
| Antigravity | `.antigravity-plugin/plugin.json` | https://antigravity.google/docs/build-plugins, https://antigravity.google/docs/plugins |

Keep `version` the same in the four plugin manifests when you release.

Check changes with `claude plugin validate .` and, where installed, `agy plugin validate --strict .`.
