# Task 02 — Predictions block + unlock gate

**Spec:** [docs/blocks/predictions.md](../docs/blocks/predictions.md)

## Must
- `predict(topic, question) -> prediction` logged **before** the user answers.
- `record(topic, actual)` → hit/miss.
- Rolling window: unlock a topic's skill at **8 correct of last 10 within 14 days** (configurable).
- `progress()` → per skill: score, what's missing, and up to 3 questions in the format "tell me / give me access to / look at".
- Agreed advice log: advice + agreed + date → `next_step()` returns one small step.
- Permission level 1 only: this block never triggers actions.

## Done when
Tests cover: window expiry, exact threshold, misses routed to the orchestrator, repeated misses (≥3 in a row) flagged to the auditor.
