# Task 03 — Auditor + review queue

**Spec:** [docs/blocks/auditor.md](../docs/blocks/auditor.md)

## Must
- Check each new entry for: conflict with an existing entry in the same block, missing source/date, inferred-over-stated, stale changing facts.
- Never edit the store itself; only create review-queue items.
- `resolve(item, choice)` with choices keep_old / keep_new / changed_to(text) / delete → writes through the store with history.
- Guardrail check hook: given a planned action and its skill level, return allow / ask_user / refuse with a reason.

## Done when
Tests cover each check type and each resolution choice.
