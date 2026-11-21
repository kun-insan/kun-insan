# Task 06 — Orchestrator + permission checks

**Spec:** [docs/blocks/orchestrator.md](../docs/blocks/orchestrator.md)

## Must
- `route(input)` → Entry / Task / AuditItem / Question (see the routing table in the spec).
- Skill registry: each skill declares name, topic, max permission level (1–4), locked/unlocked.
- `check_permission(skill, action)` enforced in code before any action; refuse above level; level 3 always asks the user.
- Calls Predictions before answering decisions.
- Model router interface: `pick_model(task, privacy_mode)`; private mode = local only.
- Never fills a gap with an invented fact: unknown → Question in the "tell me / give me access to / look at" format.

## Done when
End-to-end test: synthetic user says 5 things → correct blocks, one conflict queued, one locked skill refused, one question asked.
