---
tags:
  - type/guide
  - status/stable
created: 2026-03-22
---

# Your First Project

How to set up a project in the vault and get Claude Code oriented to it.

## 1. Create the Project Folder

Inside `Projects/`, create a subfolder named after your project:

```
Projects/
└── My App/
    ├── Current State.md     ← required
    ├── Decisions Log.md     ← recommended
    └── Open Questions.md    ← optional
```

You can create these manually in Obsidian or from the terminal:

```bash
mkdir -p ~/code/vault/Projects/"My App"
```

---

## 2. Write Current State.md

This is the most important file. Claude reads it at session start to orient itself. Keep it accurate — a stale Current State is worse than none.

```markdown
---
tags:
  - project/active
  - type/current-state
  - status/building
created: YYYY-MM-DD
updated: YYYY-MM-DD
---

# Current State — My App

## What This Is
One paragraph describing the project — what it does, who it's for, why it exists.

## Where We Are
Current phase, what's working, what's in progress.

## What's Done
- [x] Completed thing
- [x] Another completed thing

## What's Still Missing
- [ ] Next thing to build
- [ ] Open question to resolve

## Immediate Next Steps
1. First thing to do
2. Second thing to do

## Key Decisions Made
- Why we chose X over Y
- Why the architecture is structured this way
```

---

## 3. Register the Project in CLAUDE.md

Open `CLAUDE.md` and add your project to the Active Projects section:

```markdown
## Active Projects
- [[Projects/My App/Current State]] — brief description of what this project is
```

Claude Code loads `CLAUDE.md` automatically. From that point forward, every session starts with Claude already knowing your active projects and knowing to read their Current State.

---

## 4. Add a Decisions Log (Recommended)

As you make architecture decisions, append them here. Either manually or via `promote-to-obsidian.py` if you're running the full stack.

```markdown
---
tags:
  - project/active
  - type/decisions-log
created: YYYY-MM-DD
---

# Decisions Log — My App

*Architecture and implementation decisions, newest first.*

## YYYY-MM-DD

- Chose X over Y because Z
- Decided not to implement W — added complexity with no clear benefit
```

---

## 5. Make the Vault Your Own (Git Setup)

This template is a starting point — you should detach it from the template remote and push to your own private repository so the vault is yours, portable, and not shared with anyone.

```bash
cd ~/code/vault

# Remove the template remote
git remote remove origin

# Create a new private repo on GitHub (or your preferred host), then:
git remote add origin git@github.com:<your-username>/<your-vault-repo>.git
git push -u origin main
```

From that point, commit and push normally as your vault grows:

```bash
git add Projects/"My App"/
git commit -m "project: My App - initial setup"
git push origin main
```

On any other machine, clone your private vault repo:

```bash
git clone git@github.com:<your-username>/<your-vault-repo>.git ~/code/vault
```

Now the project context is portable — `git pull` on any machine and Claude is immediately oriented.

---

## Session Protocol

**At session start:** Claude reads `CLAUDE.md` (automatic), then reads `Current State.md` for the active project.

**At session end:** Update `Current State.md` to reflect what changed, then append a session log:

```
Claude/Session-Logs/YYYY-MM-DD.md
```

This keeps the vault accurate without requiring manual curation between sessions.

---

## References

- [[When Memory Systems Help]] — deciding how much infrastructure to add
- [[Deployment Patterns]] — full stack vs vault-only
