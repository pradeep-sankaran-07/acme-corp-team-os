# index: where everything lives

The catalog for the Acme Corp Team OS. Route here, then open the right file. Each folder also has its own `CLAUDE.md` map.

## Core
- CLAUDE.md - behavior and the top-level map
- config.yaml - all environment-specific values
- README.md - what this is and how to use it
- log.md - append-only activity history
- STATUS.md - freshness and last sync

## Context
- company/ - overview, market, glossary, team
- product/ - overview, strategy, roadmap, decisions, prds/
- customers/ - _index.md plus one folder per customer

## Skills (.claude/skills)
- customer-call-summary - summarise a call
- deal-brief - draft a sales decision brief for a prospect
- account-review - prep a customer review (QBR-lite)

Run each via the matching command in `.claude/commands/`.

## Orchestration (.claude/routines)
- daily-sync - morning ingest of calls and emails, commits to git

## Integrations
- integrations/gmail-calendar.md - inputs
- integrations/crm.md - where results go
