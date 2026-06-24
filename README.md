# Acme Corp Team OS

A working demo of an AI "Team OS": one shared repository that gives every function (sales, customer success, product) the full context of the business plus a small library of reusable skills, kept current automatically by a daily routine.

This repo is a demonstration. Acme Corp and its product, customers, team and data are all fictional.

## The company being modeled
Acme Corp sells **Acme Outbound**, an AI BDR / outbound platform: AI SDR agents that source and enrich leads, run multichannel sequences (email and LinkedIn), handle replies and objections, book meetings, and sync to the CRM. See `company/overview.md` and `product/overview.md`.

## The four layers
1. Context - what the AI knows: `company/`, `product/`, `customers/`.
2. Skills - repeatable recipes that turn context into output: `.claude/skills/`.
3. Orchestration - a routine that keeps context fresh with no manual upkeep: `.claude/routines/` (runs every morning at 9am).
4. Inputs - where context comes from and where results go: Gmail and Calendar in, CRM out. See `integrations/`.

## How to use it
Point Claude Code (or Cowork, or Codex) at this folder and ask in plain language, for example:
- "What is the status of Vertex Analytics?"
- "What is on the Acme Outbound roadmap?"
- "Draft an account review for Northwind Software."

The map in `CLAUDE.md` and `index.md` lets the agent find the right file fast.

## How it stays current
Each person runs `daily-sync` against their own Gmail and Calendar. It appends new calls and emails into the right customer folder, refreshes `STATUS.md`, and commits the change. A scheduled task runs it every morning at 9am, so the repo history shows it staying up to date.

## Layout
See `index.md` for the full catalog.
