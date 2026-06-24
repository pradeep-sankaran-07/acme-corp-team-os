# customers/ map

One folder per customer or prospect. Start at `_index.md` for the list and stage.
- `_index.md` - master list (stage: prospect | onboarding | active | churned)
- `_template/` - copy to create a new customer
- `<slug>/profile.md` - stable facts (contacts, plan, stage)
- `<slug>/summary.md` - current status and health (RAG)
- `<slug>/calls/` - call summaries (append, never overwrite)
- `<slug>/emails/` - condensed email context (append)
- `<slug>/documents/` - produced artifacts (deal brief, account review)
