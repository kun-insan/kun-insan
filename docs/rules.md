# Rules of the engine

## 1. Unlock by accuracy, not by fill level
A skill unlocks when the engine predicts what the user would say or decide and gets it right at a high rate, several times.

- **Threshold (v1):** 8 correct predictions out of 10, within two weeks, on that skill's topic.
- This is the shield: it keeps quality high and makes the user put in the effort. You get out what you put in.
- Unlocks can be free milestones, perks, or paid tiers.
- The threshold will be tuned from real data.

## 2. Four permission levels
Suggest → Draft → Act with approval → Act alone (within limits). Every skill declares its maximum level. Start only with actions that can be undone. See [ARCHITECTURE.md](../ARCHITECTURE.md#7-skills--sub-agents-do-not-only-remember).

## 3. Stable or changing
Each fact is marked when it enters:
- **Stable** (e.g. place of birth): never asked about again.
- **Changing**: has a review age. Defaults: money/finance weekly · goals monthly · relationships every three months.

## 4. Sync
A light review at set intervals (default: weekly, ~30 minutes): quick review of facts and conflicts, then a few new questions based on the user's week. Answers: yes / no / "changed to…". Voice answers are welcome.

## 5. Full visibility
The user can see, edit and delete everything in every block, at any time.

## 6. Onboarding questions
Every new user starts with a fixed list of first-session questions so the first output is already good. See [templates/onboarding-questions.md](../templates/onboarding-questions.md).

## 7. Stated vs inferred
Every entry is tagged **stated** (the user said it) or **inferred/observed** (the engine concluded it). Inferred facts never override stated ones and are confirmed at the next sync.

## 8. Newer wins, history stays
When a fact changes, the new one wins and the old one is kept as history ("PM on infra team, previously search").

## 9. Misses are learning, not blame
A wrong prediction updates the right block. Repeated misses on the same topic go to the auditor's review queue.

## 10. Feeding rules (for best accuracy)
- One topic per conversation; label the first line ("Work:", "Family:")
- Say **Decided** or **Thinking**
- Give recordings one line of context
- Say "save" before switching topics
- On big decisions, the engine asks: "How sure are you?"
