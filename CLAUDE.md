# Acme Corp Team OS

The shared context layer for Acme Corp. One repo that every agent and teammate works from, so anyone can act with the whole company in their head. When you work in this repo, this file governs how you behave.

This is a demo environment. Everything in it is fictional dummy data.

## Map: where information lives
Start here, then jump straight to the right folder. Do not scan the whole repo.

| If you need... | Go to |
| --- | --- |
| What Acme is, market, terms, team | `company/` |
| Product specs, strategy, roadmap, PRDs, decisions | `product/` |
| A customer or prospect (status, calls, emails, docs) | `customers/` (start at `customers/_index.md`) |
| A reusable recipe (call summary, brief, review) | `.claude/skills/` |
| The routine that keeps context fresh | `.claude/routines/` |
| How inputs connect (Gmail, calendar, CRM) | `integrations/` |
| What changed and how fresh things are | `log.md` and `STATUS.md` |
| Full catalog | `index.md` |

Each major folder has its own `CLAUDE.md` map; read it first when you enter that folder.

## Team roster
- Maya Chen - CEO - maya@acme.com
- Diego Ramirez - Head of Product - diego@acme.com
- Priya Nair - Head of Sales - priya@acme.com
- Lena Vossen - Founding Account Executive - lena@acme.com
- Sam Okafor - Customer Success Manager - sam@acme.com

## Operating norms
- Be token efficient. Short, plain Markdown. Reference long sources by pointer.
- Never fabricate facts. Ground claims in a named file. If unsure, say so.
- Human in the loop: customer-facing artifacts (briefs, reviews) end with a review step. The skill does about 70 percent; a person finishes.
- Keep context fresh: the daily routine appends, it never overwrites history.
- Privacy: only read or create customers on the watch list in `config.yaml`. Skip personal or unknown email domains.
- No em dashes in files.

## Systems
- Inputs are Gmail and Calendar (per person), pulled by `.claude/routines/daily-sync.md`. Results sync to the CRM (see `integrations/crm.md`).
- Every environment-specific value lives in `config.yaml`.
- Agents (Claude Code, Cowork, Codex) all work from this repo.
