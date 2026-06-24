# Gmail and Calendar (inputs)

Gmail and Calendar are the inputs that keep customer context current, via the `daily-sync` routine. 

## How access is authorized (per person)
- Each person authorizes their own Gmail and Calendar connectors. The routine runs as that person and reads only that person's own mailbox and calendar.
- One person's run never reads another person's inbox. Personal data stays scoped to its owner.
- The 9am scheduled task runs the routine automatically (see `config.yaml` schedule and `.claude/routines/daily-sync.md`).

## How the routine pulls
- Calendar: find meetings with a watch-list customer (by attendee domain), and pull any attached notes or transcript.
- Gmail: find threads with a watch-list customer (by domain and contacts), condense the relevant thread into the customer's `emails/`.
- Time window: first run scans all time to seed history; later runs scan only since the person's last sync time in `STATUS.md`.

## Privacy guardrail (must hold)
- Resolve every item to a customer by email domain first, then fuzzy name. Only touch customers on the watch list (`config.yaml`).
- Never create a customer from an unknown sender. Skip personal or unknown domains entirely. A private email must never become a new customer.
- Ignore anything that does not resolve to a watch-list customer.

## Note for this demo
Customers here are fictional, so a real Gmail or Calendar scan finds nothing about them. The routine still runs, records a heartbeat in `STATUS.md` and `log.md`, and commits, which is what the daily schedule demonstrates.
