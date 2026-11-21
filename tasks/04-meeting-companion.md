# Task 04 — Meeting companion v1

**Spec:** [docs/use-cases/meeting-companion.md](../docs/use-cases/meeting-companion.md)

## Must
- Input: a meeting transcript (text) + the user's memory blocks.
- Output: (1) short summary, (2) **the user's own** action points with owners and dates if said, (3) alerts: anything off, unbalanced, or conflicting with memory.
- New facts from the meeting go to memory as `inferred`, source `meeting`.
- Level 1 only: produces output for the user; sends nothing to anyone else.
- Consent flag required on the input; refuse if missing.
- Arabic and English transcripts.

## Done when
Works on 3 synthetic transcripts (Arabic, English, mixed) with tests for the consent refusal.
