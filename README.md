# Claude Memory — Obsidian Vault Template

A pre-configured Obsidian vault that pairs with [claude-memory](https://github.com/rjames-dev/claude-memory) to give Claude Code persistent, structured memory across sessions. The vault provides the human-readable narrative layer; claude-memory provides the deep technical archive.

**Not sure if you need all of this?** Read [`Getting Started/When Memory Systems Help.md`](Getting%20Started/When%20Memory%20Systems%20Help.md) first — the vault alone (no claude-memory) is already useful for many workflows.

## Getting Started

Three guides are included in the `Getting Started/` folder:

| Guide | What it covers |
|---|---|
| [When Memory Systems Help](Getting%20Started/When%20Memory%20Systems%20Help.md) | Honest assessment of when each layer earns its complexity |
| [Deployment Patterns](Getting%20Started/Deployment%20Patterns.md) | Vault only vs full stack vs production server — which fits you |
| [Your First Project](Getting%20Started/Your%20First%20Project.md) | How to set up a project folder and get Claude oriented to it |

## Setup

This vault is cloned automatically by `setup-hooks.sh` during claude-memory installation.
You do not need to clone it manually.

If you want to set it up manually:

```bash
git clone https://github.com/rjames-dev/obsidian-vault-template ~/code/vault
```

Then open Obsidian → **Open folder as vault** → point to `~/code/vault`.

> **Important:** This template repo is a starting point, not your vault's home. Once cloned, detach from this remote and push to your own private repository so your vault is portable and personal:
> ```bash
> cd ~/code/vault
> git remote remove origin
> git remote add origin git@github.com:<you>/<your-vault>.git
> git push -u origin main
> ```

## Folder Structure

```
vault/
├── Calendar/          # Calendar and scheduling notes
├── Claude/
│   ├── Knowledge-Base/    # Distilled facts, patterns, learnings
│   │   └── Learnings Log.md   # Auto-populated by promote-to-obsidian
│   ├── Scratch/           # Temporary drafts (gitignored)
│   └── Session-Logs/      # Per-session logs (auto-written by agent)
├── Events/            # Events and happenings
├── Projects/          # One subfolder per project
│   └── <Project Name>/
│       ├── Current State.md   # Living project status
│       ├── Decisions Log.md   # Architecture decisions (auto-appended)
│       └── Open Questions.md  # Unresolved questions
├── Research/          # Background knowledge and references
└── CLAUDE.md          # Auto-loaded by Claude Code every session
```

## How It Works

1. **claude-memory** captures every Claude Code session automatically via PreCompact hook
2. After significant sessions, run `promote-to-obsidian.py <snapshot_id>` to write insights here
3. The agent writes: session log, decisions, learnings — based on what the session contains
4. Obsidian becomes a live, auto-populated knowledge base of your development work

## Making It Your Own

- Edit `CLAUDE.md` to add your active projects
- Add `[[Projects/<Name>/Current State]]` links for each project you start
- The vault is a private git repo — push to your own remote to keep it portable

## What Gets Committed

- All `.md` notes
- `.obsidian/` config (plugins, theme, hotkeys) — keeps settings in sync across machines
- `CLAUDE.md`

**Not committed:** `workspace.json` (machine-specific), Scratch/ contents, `.DS_Store`
