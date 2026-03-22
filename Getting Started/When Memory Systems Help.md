---
tags:
  - type/guide
  - status/stable
created: 2026-03-22
---

# When Memory Systems Actually Help

A practical guide for deciding how much of this stack to deploy, and where.

## The Honest Baseline

Claude Code already navigates codebases well without persistent memory. Given a project directory, it can:

- Read `CLAUDE.md` for session orientation (already automatic)
- Explore file structure, read relevant files, search for context
- Reconstruct understanding of a project from source code and git history

For many users and many projects, **this is sufficient**. Don't add complexity you don't need.

## Where Persistent Memory Adds Genuine Value

### 1. Long time gaps between sessions
When you return to a project after weeks or months, reconstructing context from code alone misses the *why* — architectural decisions, dead ends explored, constraints that aren't visible in the code. A Decisions Log and Current State note close that gap instantly.

### 2. Many projects on one machine
As the number of active projects grows, `CLAUDE.md` alone doesn't scale. Semantic search across sessions lets you ask "what did we decide about X?" without knowing which file to look at.

### 3. Multiple machines
The vault as a git repo means pulling full context to any machine. Together with auto-captured sessions, machine-switching becomes seamless — pull the vault, start Claude Code, full context is there.

### 4. Team or handoff scenarios
A vault with well-maintained project notes is readable by humans and AI alike. New contributors (or future you) get up to speed from narrative notes, not by reverse-engineering code.

### 5. Application help systems
Obsidian running headless can serve vault notes as a wiki-style help system linked from or embedded in an application. This is Obsidian-as-CMS — a distinct and powerful use case beyond personal knowledge management.

## When It's Overkill

- **Single machine, active daily development** — `CLAUDE.md` + reading files is fine
- **Short-lived or experimental projects** — not worth the setup cost
- **Small vault with known contents** — you don't need search if you already know what's there

## The Obsidian MCP Question

An Obsidian MCP server (such as Basic Memory) gives Claude Code proactive search across the full vault without being directed to specific files. Useful when:

- The vault has grown large and relevant notes aren't obvious
- You want Claude to find architectural context without prompting
- Multiple projects are tracked in one vault

**Basic Memory** (`pip install basic-memory`) is recommended for multi-machine setups — it reads vault markdown directly from disk, no Obsidian app running required, and behaves identically on Mac and headless Linux servers.

> [!note] Start simple
> The vault alone (no claude-memory, no MCP) is already valuable. Add layers when you feel the friction of not having them — not before.

## References

- [[Deployment Patterns]] — which configuration fits your situation
- [[Your First Project]] — getting a project set up in the vault
