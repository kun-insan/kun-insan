# Architecture — كن إنسان engine

The open design of the engine. Diagram: [diagrams/engine-architecture-v0.1.drawio](diagrams/engine-architecture-v0.1.drawio) (open with [draw.io](https://app.diagrams.net)).

## Core idea: one engine, many instances

Every user gets their own **instance** of the same engine. An instance starts **empty**, with only guardrails, and becomes personal as it learns. The founder's instance is user #1. The engine is always kept separate from any user's data, so it can be copied without anyone's personal information.

**The product is the memory structure + architecture + guardrails. The model is swappable.** See [docs/runtime.md](docs/runtime.md).

## Layers

### 0. Guardrails (always on)
Fixed rules that never change, whatever the engine learns. Enforced in orchestrator code, not only in a prompt, so they hold for any model. → [docs/guardrails.md](docs/guardrails.md)

### 1. Inputs
- Voice notes (so it understands feeling, not only words)
- Text / chat
- Meetings (listen-only attendee)
- Connected apps (mail, calendar, files, notes, messaging), only with the user's permission
- Onboarding questions (first session) → [templates/onboarding-questions.md](templates/onboarding-questions.md)
- Human-first onboarding call (recorded with consent, AI note-taker)
- Periodic sync: yes / no / "changed to…"

### 2. Orchestrator (main agent)
Listens, learns, and routes each piece of information:
- a fact or idea → the right **memory block**
- a task → the right **skill**, within its permission level
- anything doubtful or conflicting → the **auditor**

→ [docs/blocks/orchestrator.md](docs/blocks/orchestrator.md)

### 3. Memory blocks (one topic each)
Small empty slots that fill as the engine learns the user. Default set: Profile & identity · Goals & mission · Finance · Work · Relationships & family · Routine & health · Personality Notes · Agreed Advice.

Every entry carries: **date · source · stated vs inferred · stable vs changing · review age · confidence**. The newer entry wins; the old one is kept as history. Format: [schema/memory-entry.schema.json](schema/memory-entry.schema.json). → [docs/blocks/memory-blocks.md](docs/blocks/memory-blocks.md)

### 4. Auditor (the watcher)
Flags anything conflicting, wrong or unclear and puts it in a **review queue** for the user. It never corrects on its own. → [docs/blocks/auditor.md](docs/blocks/auditor.md)

### 5. Predictions — the life coach (works from day one)
Quietly predicts what the user will say or decide, logs hit or miss per topic, and turns every piece of advice the user agreed to into a plan of small next steps. Permission level 1 (suggest) forever. → [docs/blocks/predictions.md](docs/blocks/predictions.md)

### 6. Unlock gate
A skill unlocks when Predictions reaches **8 correct out of 10 within two weeks** for that skill's topic. Accuracy, not fill level. → [docs/rules.md](docs/rules.md)

### 7. Skills / sub-agents (do, not only remember)
- Meeting companion (first use case) → [docs/use-cases/meeting-companion.md](docs/use-cases/meeting-companion.md)
- Finance skill (locked until earned)
- Feel AI (locked until earned) → [docs/blocks/feel-ai.md](docs/blocks/feel-ai.md)
- More skills, each unlocked by accuracy (free or as perks/paid tiers)

Each skill runs on the **permission ladder**:

| Level | Name | Can do |
|---|---|---|
| 1 | Suggest | Observe, listen, advise. Nothing leaves without the user. |
| 2 | Draft | Prepare drafts the user reviews and sends. |
| 3 | Act with approval | Prepare an action; the user confirms each time. |
| 4 | Act alone | Act inside limits the user set. |

Start only with actions that can be undone.

### 8. Outputs to the user
- Summary + the user's own action points
- Alerts (something off in a meeting or in the data)
- A plan of small steps + the next skill to unlock, in the "I don't know" format (tell me / give me access to / look at)
- Personality Notes reminders → [docs/blocks/personality-notes.md](docs/blocks/personality-notes.md)
- **Full visibility:** see, edit and delete every block

### 9. Runtime & data layer
- Model layer: swappable; only models that pass the **Kun Insan Certified** benchmark
- Source of truth: a user-owned store (documents/notes today → local DB + vector store), encrypted backup
- Privacy: user data private; one clearly defined section shared with the project, with separate consent
- Hardware guide by need: privacy / small / going big. The user chooses and owns it.

## Protocols

- **"I don't know" protocol:** when information is missing, say so and ask for exactly what's needed: *tell me 1, 2, 3* / *give me access to 1, 2, 3* / *look at 1, 2, 3*.
- **Onboarding:** a fixed first-session question list so the first output is already useful, plus one skill (Predictions) that works from day one.
- **Sync:** a light review at set intervals; changing facts are re-confirmed on their own cadence.
- **Always back to source:** every answer can point to where a fact came from.

## Data and privacy

**No personal data ever lives in this repository.** Synthetic examples only. → [docs/privacy-and-consent.md](docs/privacy-and-consent.md)
