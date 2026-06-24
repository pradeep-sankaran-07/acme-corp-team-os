---
name: customer-call-summary
description: Turn a customer or prospect call transcript into a structured summary and append it to that customer's calls/.
when_to_use: After a call when there is a transcript or notes. Trigger phrases include "summarise the <customer> call" and "write up the discovery call".
inputs:
  - the transcript or notes (Gmail thread, calendar notes, or pasted text)
  - the customer folder (customers/<slug>/) for context
output_location: customers/<slug>/calls/<yyyy-mm-dd>-<topic>.md
last_updated: 2026-06-24
---

# Skill: customer-call-summary

Produces a tight call summary in a consistent format so cross-customer review is easy. Model: any file in `customers/northwind-software/calls/`.

## Step 1: read
Read the transcript or notes and the customer folder. Identify the date, attendees, and call type (discovery, kick-off, check-in, QBR, review).

## Step 2: write the summary
Sections:
1. Header - date, attendees, type.
2. Objective - the one-line purpose of the call.
3. Decisions - what was agreed (each a short line).
4. Next steps by owner - split into the customer's actions and Acme's actions, with named owners.
5. Details worth keeping - anything that matters later (deliverability, messaging, scope, timeline, risks).

Keep it condensed. Do not paste the raw transcript; reference where it lives.

## Step 3: append (never overwrite)
Write a new file in the customer's `calls/`. Refresh `summary.md` recent activity, and if a decision changes status or risk, update `summary.md` accordingly. Append one line to `log.md`.
