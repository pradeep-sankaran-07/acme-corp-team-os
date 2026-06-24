# CRM (where results go)

Acme's customers run on Salesforce or HubSpot. In a production Team OS, the CRM is the system of record for the customer list (source of truth) and the place finished outputs are written back.

## In this demo
- Source of truth for the customer list is represented by the watch list in `config.yaml` (in production this would sync from Salesforce or HubSpot).
- Outputs (deal briefs, account reviews, call summaries) live in each `customers/<slug>/` folder. In production, key fields and notes would also be written back to the CRM record.
- No live CRM connection is configured here; this file documents the intended flow.

## Intended flow (production)
1. Customer and prospect lists sync from the CRM into the watch list.
2. The daily routine condenses calls and emails into the customer folders.
3. Artifacts and status updates are pushed back to the CRM so reps see them in context.
