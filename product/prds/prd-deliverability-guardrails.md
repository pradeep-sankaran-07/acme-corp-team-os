# PRD: Deliverability Guardrails

- Owner: Diego Ramirez
- Status: In progress (Now)
- Last updated: 2026-06-22

## Problem
A few customers saw reply rates drop after scaling volume; the root cause was deliverability, not messaging. The system should protect the sending domain automatically.

## Goals
- Keep customers out of spam as they scale volume.
- Make sending limits deterministic and visible.

## Non-goals
- Buying or rotating domains for customers (a service, not the product).

## Requirements
1. Per-mailbox daily sending caps (deterministic, hard-coded ceilings the AI cannot exceed).
2. Domain health monitoring (bounce rate, spam-complaint rate, blocklist checks).
3. Automatic pause of a mailbox when the spam-complaint rate crosses a threshold, with an alert.
4. Warmup schedule for new mailboxes before they join live sending.

## Success metrics
- Spam-complaint rate held under target as volume scales.
- Fewer customer-reported deliverability incidents.

## Open questions
- Default caps by mailbox age and provider (Google vs Microsoft).
