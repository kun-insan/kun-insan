# Auditor (the watcher)

## Job
Filter anything **conflicting, wrong or unclear** and put it in a review queue for the user to resolve. It **never corrects on its own**.

## Checks
1. **Conflict:** a new fact contradicts an existing one ("meets Saturdays" vs "meets Sundays").
2. **Source:** a fact has no source or date.
3. **Inferred vs stated:** an inferred fact is about to override a stated one → blocked, queued.
4. **Stale:** a changing fact passed its review age → added to the next sync.
5. **Guardrails:** a planned action or output breaks a guardrail → stopped, explained.
6. **Repeated misses:** Predictions missed the same topic several times → queued for review.
7. **Drafts to other people:** any claim in a message the user will send is checked against the user's own words and records.

## Review queue item
```json
{
  "type": "conflict | missing_source | stale | guardrail | repeated_miss",
  "block": "Work",
  "old": "...",
  "new": "...",
  "question_for_user": "Which one is right now?",
  "created": "2026-01-01"
}
```

## Resolution
The user answers: keep old / keep new / "changed to…" / delete. The orchestrator writes the result with history.
