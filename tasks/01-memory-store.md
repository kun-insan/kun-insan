# Task 01 — Memory store + schema validation

**Goal:** a local store for memory entries that follows [schema/memory-entry.schema.json](../schema/memory-entry.schema.json).

## Must
- Add / update / delete / list entries per block.
- Validate every entry against the schema.
- Update = newer wins, old version pushed to `history`.
- An `inferred` entry can't overwrite a `stated` one → return a conflict for the auditor.
- `due_for_review()` returns changing entries past `review_every_days`.
- Export/import the whole store as JSON (the user owns their data).
- Encrypted at rest (key held by the user).

## Done when
Tests cover: validation, history, stated-vs-inferred conflict, review due dates, export/import round trip.
