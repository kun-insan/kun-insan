# Memory blocks

Small, empty slots, **one topic each**. They fill as the engine learns the user. Learning lives here, not in the model: models don't learn from use, the memory layer does.

## Default blocks
| Block | Holds | Default review age |
|---|---|---|
| Profile & identity | Name, role, languages, how they like to be spoken to | Stable |
| Goals & mission | Short and long goals, the mission | Monthly |
| Finance | Targets, rules for spending (no account numbers ever) | Weekly |
| Work | Projects, clients (by role, not private details), how they work | Monthly |
| Relationships & family | Who matters and how (relationship context only) | Every 3 months |
| Routine & health | Sleep, routine, recharge (sensitive: separate consent) | Monthly |
| Personality Notes | Forgot / repeated → gentle reminders ([spec](personality-notes.md)) | Ongoing |
| Agreed Advice | Advice + "agreed" + date ([spec](predictions.md)) | Ongoing |

Editions can add or remove blocks (see [../editions/](../editions/)).

## Every entry
- date
- source (conversation, voice note, meeting, app, sync)
- **stated** or **inferred**
- **stable** or **changing**, with review age
- confidence
- history (older versions kept)

Format: [schema/memory-entry.schema.json](../../schema/memory-entry.schema.json)

## Rules
- Newer wins; history stays.
- Inferred never overrides stated.
- The user can see, edit and delete any entry.
- Never stored: government ID numbers, card/bank account numbers, passwords, or anything the user asks to forget.

## Storage
Today: documents/notes the user owns (with an encrypted backup). Next: a local database + vector index on the user's own device or cloud account.
