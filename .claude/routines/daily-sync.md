# Routine: daily-sync

Keep every customer's context current from a person's Gmail and Calendar, with no manual upkeep. Runs every morning at 9am as a scheduled task (see `config.yaml` schedule) and is also runnable by hand.

## Who runs it
Each person runs this against their own Gmail and Calendar, authorized individually. One person's run never reads another person's mailbox.

Inputs: the person, their Gmail and Calendar, the `watch_list` and `sources` in `config.yaml`, and `STATUS.md` for the last sync time.

## Time window
- First run for a person: scan all time, to seed history.
- Later runs: scan only since that person's last context refresh in `STATUS.md`.

## Account resolution (strict)
For each candidate email or calendar item:
1. Match by email domain against the watch list in `config.yaml`.
2. If the domain is ambiguous, fall back to fuzzy, typo-tolerant matching on the customer name.
3. Only ever update a customer already on the watch list. Never create a customer from an unknown sender.
4. Skip personal or unknown domains (`sources.matching.exclude_personal_domains`). A private email must never become a new customer.
Anything that does not resolve to a watch-list customer is ignored. Do not read or store unrelated personal content.

## What to do per matched item
- Call or meeting: condense with the `customer-call-summary` skill and append to `customers/<slug>/calls/`. Never overwrite.
- Email thread: condense and append to `customers/<slug>/emails/`. Never overwrite.
- After updating a customer: refresh `summary.md` and the customer's row in `customers/_index.md`. Append, do not rewrite history.

## Close out the run (every run, even with no new items)
1. Append one line to `log.md` per customer touched, plus a run line (date, person, items found).
2. Update `STATUS.md`: set the person's last context refresh to now, and refresh any touched customer's last update.
3. Commit and push so the GitHub history reflects the run:
   `git add -A && git commit -m "daily-sync: <date>" && git push`

## Guardrails
- Never fabricate. If a fact is unclear, record it as an open question in the customer summary.
- Token efficient: condense, reference sources by pointer, no long transcripts.
- This is a demo repo with fictional customers, so a scheduled run normally finds no real email and simply records a heartbeat commit. That is expected.
