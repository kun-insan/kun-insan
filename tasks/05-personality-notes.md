# Task 05 — Personality Notes

**Spec:** [docs/blocks/personality-notes.md](../docs/blocks/personality-notes.md)

## Must
- Detect when a new request matches something already decided (same topic in Agreed Advice, an existing recurring item, a stated fact).
- Return one short, kind reminder with the original date, and options: keep / change.
- Log a note: what, when, resolution.
- Patterns (same thing ≥3 times) are surfaced as `inferred`, never acted on.

## Done when
Tests cover detection, the reminder text (AR + EN), and pattern surfacing.
