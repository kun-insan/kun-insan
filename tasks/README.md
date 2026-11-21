# Build tasks — pick one, send a PR

Each task is a ready spec. You can hand it to an AI coding assistant as the prompt. Small, focused PRs win.

| # | Task | Size |
|---|---|---|
| 01 | [Memory store + schema validation](01-memory-store.md) | S |
| 02 | [Predictions block + unlock gate](02-predictions-block.md) | M |
| 03 | [Auditor + review queue](03-auditor.md) | M |
| 04 | [Meeting companion v1](04-meeting-companion.md) | M |
| 05 | [Personality Notes](05-personality-notes.md) | S |
| 06 | [Orchestrator + permission checks](06-orchestrator.md) | L |
| 07 | [Kun Insan Certified benchmark](07-benchmark.md) | M |
| 08 | [Weekly sync flow](08-weekly-sync.md) | S |

## Rules for every task
- Synthetic data only. No real personal data, ever.
- Guardrails from [docs/guardrails.md](../docs/guardrails.md) are enforced in code.
- Arabic + English where there is user-facing text.
- Include tests. Sign commits (`git commit -s`).
- Open an issue "Taking: task NN" before you start, so two people don't build the same thing.

Language/stack: open. Propose it in your issue; first merged task sets the default.
