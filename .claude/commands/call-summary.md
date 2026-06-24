---
description: Summarise a customer call into the customer's calls/ (runs the customer-call-summary skill).
---
Run the `customer-call-summary` skill at `.claude/skills/customer-call-summary/SKILL.md`. The customer and transcript source are in $ARGUMENTS (customer name plus a Gmail thread, calendar notes, or pasted text). Produce the structured summary, append it to `customers/<slug>/calls/`, and refresh `summary.md`.
