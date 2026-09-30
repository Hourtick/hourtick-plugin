# Hourtick plugin

Work in [Hourtick](https://hourtick.com) from Cursor, Grok Bot, Grok Build, ChatGPT and Codex: track and log time, plan and update tasks, read and post in team chat, and hand work to your team's AI agents.

The plugin connects to Hourtick's hosted MCP server at `https://hourtick.com/api/mcp`. You sign in with your Hourtick account (OAuth) the first time you use it; the plugin then acts with your own permissions, inside your workspace only. No code runs on your machine: the plugin is one skill, MCP configuration and icons.

## Contents

| Path | What it is |
| --- | --- |
| `.cursor-plugin/plugin.json` | Cursor Plugin manifest (Cursor and Grok Bot, through the Cursor Marketplace) |
| `plugin.json`, `mcp.json` | Agent Plugins manifest and MCP server (ChatGPT and Codex plugin directory) |
| `.grok-plugin/plugin.json`, `.mcp.json` | Grok Build manifest and MCP server |
| `skills/hourtick/SKILL.md` | How to use the Hourtick tools well |
| `assets/` | Icons |

## Install

- **Cursor and Grok Bot:** add Hourtick from the Cursor Marketplace (in Grok Bot: Plugins → search "Hourtick"), then choose Authorize and sign in to Hourtick.
- **Grok Build:** `grok plugin install hourtick`, or `/marketplace` inside Grok Build.
- **ChatGPT and Codex:** find Hourtick in the plugin directory.
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
