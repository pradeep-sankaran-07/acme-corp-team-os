---
name: account-review
description: Produce a QBR-lite account review for an active customer (usage, results, risks, expansion).
when_to_use: Before a QBR or health review, or when a customer needs a status review. Trigger phrases include "account review for <customer>" and "prep the <customer> QBR".
inputs:
  - customer folder (customers/<slug>/): profile.md, summary.md, calls/, emails/
output_location: customers/<slug>/documents/account-review-<yyyy-mm-dd>.md
last_updated: 2026-06-24
---

# Skill: account-review

Produces a concise account review a CSM can take into a QBR. Model: `customers/northwind-software/documents/account-review-2026-05-20.md`.

## Step 1: gather
Read the customer folder. Pull the plan, recent calls and emails, results to date, and open items.

## Step 2: write the review
Sections:
1. Health - RAG with one line of justification.
2. Usage - reps, modules, CRM, channels, active ICPs.
3. Results - meetings booked, reply rates, pipeline sourced (use the customer's own figures; mark anything uncertain).
4. Risks - adoption, single-champion reliance, deliverability, renewal.
5. Expansion - seats, modules, segments.

## Step 3: human review (required)
End with a checklist to confirm figures and the plan with the customer before sending externally.

## Step 4: record
Write to the output location, refresh `summary.md`, append one line to `log.md`.
