---
tags:
  - type/research
  - topic/obsidian
  - topic/claude-code
  - topic/mcp
created: 2026-04-23
---

# Obsidian Enhancement Projects

*Research into GitHub projects that enhance Obsidian vaults, specifically for Claude Code workflows. Compiled April 23, 2026.*

---

## Memory & Context Persistence

| Project | Stars | Summary |
|---------|-------|---------|
| [claude-mem](https://github.com/thedotmack/claude-mem) | 66k | Community standard for Claude Code persistent memory. Auto-captures sessions, compresses with Claude SDK, injects relevant context into future sessions. MCP search tools + web viewer UI. Updated April 22, 2026. |
| [claude-code-memory-setup](https://github.com/lucasrosati/claude-code-memory-setup) | 309 | Obsidian + Claude Code token reduction (claims 71.5x fewer tokens). `/resume` and `/save` commands, Zettelkasten-based vault structure. |
| [claude-memory-compiler](https://github.com/coleam00/claude-memory-compiler) | 880 | Hooks capture sessions → LLM extracts decisions/lessons → outputs `[[wikilinks]]` markdown natively compatible with Obsidian graph view. |

---

## Claude Code ↔ Obsidian Direct Integration

| Project | Stars | Summary |
|---------|-------|---------|
| [Claudian](https://github.com/YishenTu/claudian) | 9k | Embeds Claude Code directly inside Obsidian. Inline editing with diff preview, `@mention` vault files, plan mode, MCP support, multi-tab conversations. Updated April 22, 2026. |
| [claude-obsidian](https://github.com/AgriciDaniel/claude-obsidian) | 3.1k | Autonomous knowledge system (Karpathy LLM Wiki pattern). Claude extracts entities, builds cross-referenced wiki pages, `/autoresearch` and `/wiki` commands. |

---

## MCP Servers for Obsidian

Gives Claude Code live read/write access to the vault.

| Project | Stars | Summary |
|---------|-------|---------|
| [mcp-obsidian](https://github.com/MarkusPfundstein/mcp-obsidian) | 3.5k | Most mature. Read/write vault via Obsidian Local REST API plugin. Python. |
| [obsidian-claude-code-mcp](https://github.com/iansinnott/obsidian-claude-code-mcp) | 259 | Zero-config — Claude Code auto-discovers vault via WebSocket. Supports Claude Desktop simultaneously. |
| [obsidian-mcp-server](https://github.com/cyanheads/obsidian-mcp-server) | 465 | Most feature-complete — atomic frontmatter, tag management, regex search, soft-delete, JWT/OAuth auth. |
| [obsidian-mcp-tools](https://github.com/jacksteamdev/obsidian-mcp-tools) | 783 | Semantic search + Templater execution (Claude Code triggers your vault templates). |
| [mcpvault](https://github.com/bitbonsai/mcpvault) | — | Lightweight, provider-agnostic. Works with Claude Code, Claude Desktop, ChatGPT, Gemini CLI, IntelliJ. |

---

## Auto-Populate Vault from External Sources

| Project | Stars | Summary |
|---------|-------|---------|
| [Nexus AI Chat Importer](https://github.com/Superkikim/nexus-ai-chat-importer) | 157 | Imports Claude.ai, ChatGPT, Mistral conversations into Obsidian as formatted Markdown. CLI mode for automated pipelines. Updated April 21, 2026. |

---

## Core Obsidian Plugins Worth Having

| Plugin | Stars | Why it matters |
|--------|-------|----------------|
| [Obsidian Git](https://github.com/Vinzent03/obsidian-git) | 10.6k | Auto-commit/push vault — syncs across machines, makes session notes git artifacts. Updated April 16, 2026. |
| [Smart Connections](https://github.com/brianpetro/obsidian-smart-connections) | 4.9k | Local semantic search — surfaces related notes as you work. Works with Claude. |
| [Smart Composer](https://github.com/glowingjade/obsidian-smart-composer) | 2.2k | AI chat inside Obsidian with `@filename` context, apply edits inline. Works with Claude. |
| [Dataview](https://github.com/blacksmithgu/obsidian-dataview) | 8.8k | Query vault as a database — turn Claude-written frontmatter into live dashboards. |

---

## Priority Recommendations

For this vault's use case (Claude Code + persistent context + session logging):

1. **[[claude-mem]]** — replace or complement `rjames-dev/claude-memory`; community standard with 66k stars
2. **[[Claudian]]** — unified Claude Code + Obsidian environment; most direct integration
3. **[[obsidian-claude-code-mcp]]** — zero-config vault auto-discovery for Claude Code via WebSocket
4. **[[mcp-obsidian]]** — mature MCP server for scripted vault read/write from hooks
5. **[[Nexus AI Chat Importer]]** — auto-populate vault from Claude.ai web conversations via CLI
6. **[[claude-code-memory-setup]]** — explicit Obsidian + Claude Code token-reduction architecture

---

## Related

- [[Deployment Patterns]]
- [[When Memory Systems Help]]
