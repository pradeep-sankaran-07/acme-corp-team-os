---
name: deal-brief
description: Draft a short sales decision brief for a prospect evaluating Acme Outbound, grounded in the prospect's context.
when_to_use: After discovery, when a prospect needs a decision document. Trigger phrases include "draft a deal brief for <prospect>".
inputs:
  - prospect folder (customers/<slug>/): profile.md, summary.md, calls/, emails/
  - company/overview.md, company/market.md, product/overview.md, product/strategy.md
  - the dominant value angle (human confirms)
output_location: customers/<slug>/documents/deal-brief-<yyyy-mm-dd>.md
last_updated: 2026-06-24
---

# Skill: deal-brief

Produces about 70 percent of a sales decision brief from prospect context. A human adds judgment and approves before it goes out. Model: `customers/cobalt-security/documents/deal-brief-2026-06-18.md`.

## Step 1: gather
Read the prospect folder and the company and product context. Note their current stack, pain, ICP, buyer, and what discovery surfaced. Never invent facts; list missing ones as open questions.

## Step 2: choose the dominant value angle (decision structure)
Lead with ONE angle, not all three:
- Pipeline volume: choose when the buyer's pain is not enough meetings and they have headroom to scale.
- Rep productivity / cost: choose when they are trying to avoid hiring or ramping SDRs.
- Deliverability and reply quality: choose when they are regulated, burned by spam, or drowning in manual reply triage.
Confirm the angle with the human, and record it in the brief.

## Step 3: draft the brief
Sections: dominant value angle; 1) situation; 2) why Acme Outbound (framed on the angle); 3) expected impact (illustrative, marked to-confirm, never invented); 4) proposed scope and plan; 5) pricing (placeholder unless known).

## Step 4: human review (required)
End with a checklist: is the angle right, are figures marked illustrative, are scope and next steps correct, who finalizes and sends.

## Step 5: record
Write to the output location, refresh `summary.md`, append one line to `log.md`.
