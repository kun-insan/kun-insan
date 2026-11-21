# Orchestrator (main agent)

## Job
Listen, learn, and send each piece of information to the right place. It is the only component that talks to the user directly.

## Routing
| Input | Goes to |
|---|---|
| A fact about the user | The matching memory block, as a new entry ([schema](../../schema/memory-entry.schema.json)) |
| A task | The matching skill, if unlocked and within its permission level |
| A conflict with an existing fact | Auditor → review queue |
| Unclear input | Ask the user (the "I don't know" protocol) |
| Advice the user agreed to | Agreed Advice block + Predictions plan |
| User forgot or repeated something already decided | Gentle reminder + Personality Notes |

## Rules
- Before every action: permission check against the skill's level. Refuse anything above it.
- Tag every entry **stated** or **inferred**, with date and source.
- Mark every new fact **stable** or **changing**; set its review age.
- Before answering, Predictions logs its guess (see [predictions.md](predictions.md)).
- Never invents a fact to fill a gap.

## Inputs it handles
Voice (with tone/feeling where available), text, meeting transcripts, files, connected apps (only with permission), sync answers.

## Interface (draft)
```
route(input) -> [Entry | Task | AuditItem | Question]
check_permission(skill, action) -> allow | ask_user | refuse
```
