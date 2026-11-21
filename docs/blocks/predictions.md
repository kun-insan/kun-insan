# Predictions block — your life coach

## Job
Advise and guide the user to unlock the other skills, so they start advising too. It's the user's **life coach**: it walks with them through every stage of the journey toward an organized life and a clear mission.

## What it keeps
Every piece of advice the user **agreed** to, with its date (advice + "agreed"). Nothing agreed gets lost.

## The plan
From the agreed advice it builds a short plan of quick focus points, **always small steps**, because people like going step by step. One small next step at a time, then the next.

## How it scores
1. Before the user answers or decides, it quietly predicts what they will say.
2. It compares and logs **hit** or **miss** per topic.
3. This scoreboard drives the unlock gate: **8 correct out of 10 within two weeks** opens that topic's skill.

## What the user sees
Which skill is closest to unlocking and exactly what's missing, in the guardrail format:

> "Finance skill: 7 of 10 correct predictions. Answer these 3 questions to open it: 1) … 2) … 3) …"

## Role and limits
- Coach and guide only. It never acts and never decides for the user. **Permission level 1 (Suggest) forever.**
- Advice on psychological state belongs to [Feel AI](feel-ai.md) once unlocked; serious cases go to a qualified human.
- **Day-one skill:** works from the first session, so the user always knows the next step.
- **Misses are learning, not blame:** a miss updates the right block; repeated misses go to the auditor.

## Data (draft)
```json
{"topic": "finance", "prediction": "will postpone purchase", "actual": "postponed", "hit": true, "date": "2026-01-01"}
{"advice": "draft posts before publishing", "agreed": true, "date": "2026-01-01", "next_step": "write tomorrow's post as a draft first"}
```
