# Architecture — كن إنسان engine (MVP base)

This document describes the open design of the engine. It's the reference for anyone who wants to understand or build on it.

## Core idea: one engine, many instances

Every user gets their own **instance** of the same engine. An instance starts **empty**, with only guardrails, and becomes personal as it learns. The founder's instance is the first one. The engine is always kept separate from any user's data.

## Components

### 1. Guardrails
Always-on rules that no user, skill or memory can override: honesty, safety, human rights, privacy, and age-appropriate limits (separate versions per age group are planned). Guardrails define what the AI will never do and when it must say "I can't do this."

### 2. Orchestrator
The main loop. It listens to the user, decides what each piece of information is, and routes it:
- a fact or idea → the right **memory block**
- a task → the right **skill**, within its permission level
- anything doubtful → the **auditor**

### 3. Memory blocks
Empty, typed slots (e.g. work, goals, people, preferences, routines). Each entry is stored with:
- date
- source: *stated* by the user or *observed*
- confidence and review cadence (some facts are stable, others change and get re-confirmed)

### 4. Auditor / Watcher
A dedicated block that acts like an auditor. It filters anything conflicting, wrong or unclear, and raises it to the user instead of silently guessing.

### 5. Skills (4 permission levels)
Capabilities the orchestrator can call. Each skill runs at a permission level the user grants:

| Level | Name | Can do |
|---|---|---|
| 1 | Observe | Read and listen only (e.g. attend a meeting silently) |
| 2 | Advise | Summarize, recommend, draft |
| 3 | Act with approval | Prepare an action; the user confirms |
| 4 | Act within limits | Act on its own inside limits the user set |

### 6. Milestones (earned abilities)
Abilities unlock by **proven accuracy** for that user, not by how full a block is. This keeps quality high and makes the user part of the process: you get out what you put in.

## Protocols

- **Onboarding questions:** every new user starts with a fixed set of questions so the first output is already useful.
- **"I don't know" protocol:** when information is missing, the AI says so and asks for exactly what it needs: *tell me…* / *give me access to…* / *look at 1, 2, 3…*
- **Live sync:** on a regular cadence the user confirms which facts still hold and which have changed.

## First use case

**Meeting companion.** The AI attends meetings in listen-only mode (level 1) with full background from one source of truth, then sends the user a summary, their action points, and an alert if something was off. Acting after the meeting (levels 3–4) comes later, through milestones.

## Data and privacy

- User data is private to the user. Only a clearly defined section, with separate consent, is shared with the project.
- Separate consent for data use and for anything published.
- Built on standard legal frameworks and existing, audited cloud security services.
- **No personal data ever lives in this repository.**

## What's open and what isn't (for now)

| Open (this repo) | Invited builders only |
|---|---|
| Vision, principles, architecture | Engine implementation |
| Interfaces and specs | Guardrail tuning and evaluation sets |
| Roadmap and discussions | Hosted service and infrastructure |

As the engine matures, more moves into the open.
