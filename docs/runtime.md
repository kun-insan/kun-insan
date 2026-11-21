# Runtime, models & hardware

## Core decision
**The product = memory structure + architecture + guardrails. The model is just the engine and can be swapped.** Users run it where they choose, so their data and memory live in a place they own, with free choice of model.

## How "keeps learning" really works
Models don't learn from use, local or cloud. Learning lives in the memory layer: memory blocks, decision logs, the auditor and the sync. That layer is the real product.

## Swappable models, same guardrails
Guardrails live in orchestrator code (permissions, auditor checks, approval steps), so they hold for any model.
- Smaller local models follow instructions less reliably → **route by task**: small local model for private/simple work, strong cloud model for hard work.
- If a cloud model is used, that task's data passes through the cloud during processing; memory still stays with the user. The user chooses per task or per block. **Private mode = local only.**

## Kun Insan Certified (model benchmark)
Users may choose any model, but only models that pass the benchmark are allowed. Re-run monthly as new models ship.

| Test | Passes when |
|---|---|
| Guardrail adherence | Never acts above permission; refuses guardrail breaks |
| Honest "I don't know" | Says it and asks for what's missing instead of guessing |
| Arabic + English | Clear, natural output in both |
| Tool use | Correct calls, correct arguments |
| Task accuracy | Correct on real tasks from founder testing (anonymized) |

Candidates are picked from results, not hype: strong cloud models (e.g. via a managed cloud service in the user's own account) and open-weight families run locally.

## Architecture sketch (MVP)
1. **User's device or account:** memory store + vector index, orchestrator, guardrails, auditor, skills with 4 permission levels, encrypted backup.
2. **Model router:** picks the model per task, local or cloud when the user allows.
3. **Inputs:** voice/text, meetings, files, connected apps.
4. **Outputs:** summaries, action points, alerts, reminders, Personality Notes.

## Hardware guide (we guide, you choose — we don't sell boxes)
| Need | Setup |
|---|---|
| Starting / small | Any modern laptop or a small desktop with plenty of unified memory: local memory + cloud models for heavy work |
| Full privacy | A machine that runs capable open models fully locally (high-memory workstation class) |
| Going big | Workstation / AI-box class hardware running large open models for a team |

Every tier is tested by the founder before it's recommended. Exact models and prices are listed in the guide at release time, because they change fast.
