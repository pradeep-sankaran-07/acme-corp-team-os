# PRD: AI Reply Handling v2

- Owner: Diego Ramirez
- Status: In progress (Now)
- Last updated: 2026-06-20

## Problem
Reply handling v1 classifies replies but mislabels objections and books meetings too cautiously, so positive replies leak. CSMs report customers manually triaging replies, which defeats the point of an AI rep.

## Goals
- Lift positive-reply-to-meeting conversion.
- Reduce mislabeled replies (an objection read as not-interested).
- Keep auto-sent replies inside guardrails (no pricing commitments, on-brand tone).

## Non-goals
- Voice or SMS replies (later).
- Negotiation or contract handling.

## Requirements
1. Classify each reply into: interested, objection, question, out of office, unsubscribe, not now, wrong person.
2. For objections and questions, draft a response from approved objection-handling content; auto-send only when confidence is above threshold, else route to a human.
3. For interested replies, propose times and book when the lead picks one.
4. Every auto-send passes guardrail checks (tone, claims, unsubscribe honored) and is logged for evals.

## Success metrics
- Positive-reply-to-meeting conversion up.
- Manual reply triage down.
- Zero guardrail violations in the eval suite.

## Open questions
- Confidence threshold for auto-send vs human handoff.
- How to handle multi-thread replies on the same lead.
