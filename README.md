# Hourtick plugin

Work in [Hourtick](https://hourtick.com) from Cursor, Grok Bot, Grok Build, ChatGPT, Codex, Devin and Factory Droid: track and log time, plan and update tasks, read and post in team chat, and hand work to your team's AI agents.

The plugin connects to Hourtick's hosted MCP server at `https://hourtick.com/api/mcp`. You sign in with your Hourtick account (OAuth) the first time you use it; the plugin then acts with your own permissions, inside your workspace only. No code runs on your machine: the plugin is one skill, MCP configuration and icons.

## Contents

| Path | What it is |
| --- | --- |
| `.cursor-plugin/plugin.json` | Cursor Plugin manifest (Cursor and Grok Bot, through the Cursor Marketplace) |
| `plugin.json`, `mcp.json` | Agent Plugins manifest and MCP server (ChatGPT and Codex plugin directory) |
| `.grok-plugin/plugin.json`, `.mcp.json` | Grok Build manifest and MCP server |
| `devin/` | Devin plugin (`.devin-plugin/plugin.json`, the MCP server, the skill, the logo) |
| `factory/`, `.factory-plugin/marketplace.json` | Factory Droid plugin, and this repo as a Droid plugin marketplace |
| `skills/hourtick/SKILL.md` | How to use the Hourtick tools well, and how to account for work as an agent |
| `assets/` | Icons |

## Install

- **Cursor and Grok Bot:** add Hourtick from the Cursor Marketplace (in Grok Bot: Plugins → search "Hourtick"), then choose Authorize and sign in to Hourtick.
- **Grok Build:** `grok plugin install hourtick`, or `/marketplace` inside Grok Build.
- **ChatGPT and Codex:** find Hourtick in the plugin directory.
- **Devin:** Customize → Plugins → Add plugin → From repository: `Hourtick/hourtick-plugin`, subdirectory `devin`. Connect Hourtick when Devin asks. To run Devin as an Hourtick agent started by Hourtick, see https://hourtick.com/agents/devin
- **Factory Droid:** `droid plugin marketplace add Hourtick/hourtick-plugin`, then `droid plugin install hourtick@hourtick-plugin` (or `/plugins` in Droid), and sign in with `/mcp`.
- **Any other MCP client:** add `https://hourtick.com/api/mcp` as a remote MCP server. Guides for each app: https://hourtick.com/install.md

## Usage

Ask in plain language, for example:

- "What did I work on today, and what's missing from my timesheet?"
- "Show my open tasks and what's blocked."
- "Log 1.5 hours on Brand identity for yesterday, design work."
- "Post a status update in #general."

Nothing needs configuring: no API keys or variables. The plugin can't delete time entries or send invoices, and it only sees the workspace you signed in to.

## Support

https://hourtick.com/contact · [Privacy](https://hourtick.com/privacy) · [Terms](https://hourtick.com/terms)

## License

MIT, © WeCode A/S. See [LICENSE](LICENSE).
