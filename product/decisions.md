# Key product decisions

Short record of decisions and why. Newest at the bottom.

- Deterministic vs non-deterministic split. Sending limits, unsubscribe handling, and CRM writes are deterministic and hard-coded. Reply drafting and personalization are non-deterministic, governed by guardrails plus an eval suite run on every change. Why: getting an unsubscribe or a sending cap wrong is a compliance and deliverability failure; those must be exact.
- No fully autonomous send without guardrails and evals. An AI rep can draft and send replies, but only inside guardrails (tone, claims, no pricing commitments) that are covered by evals. Why: one bad auto-reply can lose a deal or trigger spam complaints.
- Per-mailbox sending caps over a single global cap. Why: protects individual sender reputation; a domain-wide cap hides per-mailbox problems.
- Land on the deliverability and reply-handling wedge, not on autonomy claims. Why: autonomy is crowded and easy to over-promise; reliability is the durable differentiator.
