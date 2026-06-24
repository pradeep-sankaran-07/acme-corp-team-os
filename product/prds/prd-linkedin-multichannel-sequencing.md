# PRD: LinkedIn Multichannel Sequencing

- Owner: Diego Ramirez
- Status: Planned (Next)
- Last updated: 2026-06-18

## Problem
Email-only sequences cap reply rates. Customers (for example Brightwave Media) ask for LinkedIn steps interleaved with email in a single sequence, run by the AI rep.

## Goals
- Allow LinkedIn steps (connection request, message, InMail) inside an email sequence.
- One unified view of touches and replies per lead across channels.

## Non-goals
- Mass connection spam. Respect per-day LinkedIn action limits.

## Requirements
1. Sequence builder supports LinkedIn step types with their own timing.
2. Per-account LinkedIn action limits (deterministic caps) to protect the account.
3. Replies from LinkedIn feed the same reply-handling pipeline as email.
4. Analytics attribute meetings to the channel mix.

## Success metrics
- Positive reply rate up for multichannel vs email-only sequences.
- No LinkedIn accounts flagged for over-limit activity.

## Open questions
- Native API vs assisted actions for LinkedIn.
