# كن إنسان — Kun Insan (Be Human)

> **For all humans. No race, no religion, no color. Just a greater, better Earth for all humans. And humans lead it.**
>
> لكل البشر. لا عرق، لا دين، لا لون. فقط أرض أعظم وأفضل لكل البشر. والإنسان هو اللي يقودها.

An AI that doesn't pretend to be human. It helps humans be better humans.

**كن إنسان** is an open AI engine you receive *empty*, with only guardrails. It learns from you (voice or text), adapts to you, and guides you to do things the right way, honestly and clearly, without noise.

It is **created, not a creator**. You direct it. It won't do everything for you, and it tells you plainly when something is right, when it's wrong, and when it can't help.

**Target: 8 billion people.** Any background, any country. It speaks from science and evidence, never compares you to anyone else, and never lies to you.

**Everything is open.** The full engine design, every block spec, the rules, the prompts, the templates and the build tasks are in this repo under Apache 2.0.

---

## The goal

As you progress through the stages and unlock skills, **you grow**, until your life is organized and you know your mission in this life. A complete journey built on work, sincerity, honesty and trust.

It's a **two-way journey**: you feed it until it truly understands you, and you learn how to work with it. Always for the benefit of the human and human nature (فطرة الإنسان), nothing else. → [docs/journey.md](docs/journey.md)

## Principles

1. **Clarity and transparency.** No noise, no flattery, no hidden agendas.
2. **Says "I don't know."** When it lacks information it asks for exactly what it needs instead of guessing.
3. **Your data is yours.** Private by default, runs where you choose, on hardware you own if you want.
4. **Earned abilities.** New skills unlock when the AI proves it's accurate *for you*, not because it's full of data.
5. **Human in charge.** It advises; you decide. It acts only within the permissions you grant.
6. **For everyone.** No discrimination by race, religion, color, gender or belief. Guided by human rights.
7. **No comparison.** No two people get the same benefit. It only helps you become the best version of yourself.

## How it works

```
You (voice · text · meetings · apps)
   │
   ▼
Orchestrator ──▶ Memory blocks (one topic each; every fact dated, sourced, stable/changing)
   │                    │
   │                    └─▶ Auditor ──▶ review queue (you resolve conflicts)
   │
   ├─▶ Predictions / Life Coach ──▶ Unlock gate (8 of 10 correct within 2 weeks)
   │                                       │
   ├─▶ Skills (4 permission levels) ◀──────┘
   │
   └─▶ Guardrails (always on, enforced in code, for any model)
```

| Read this | For |
|---|---|
| [ARCHITECTURE.md](ARCHITECTURE.md) | The full engine design |
| [docs/guardrails.md](docs/guardrails.md) | Rules that never change |
| [docs/rules.md](docs/rules.md) | Unlock by accuracy, permissions, sync, visibility |
| [docs/blocks/](docs/blocks/) | Spec for every block |
| [docs/runtime.md](docs/runtime.md) | Swappable models, certification benchmark, hardware guide |
| [docs/privacy-and-consent.md](docs/privacy-and-consent.md) | Data, consent, legal frameworks |
| [docs/editions/](docs/editions/) | Versions per age group |
| [docs/use-cases/](docs/use-cases/) | First use case: meeting companion |
| [prompts/](prompts/) | System prompts (Arabic + English) |
| [templates/](templates/) | Start your own empty instance today |
| [schema/](schema/) | Memory entry format |
| [tasks/](tasks/) | Ready-to-build specs: pick one and send a PR |
| [diagrams/](diagrams/) | Architecture diagram (draw.io) |

## Status

**Phase 0: founder testing.** The founder is user #1 and tests the engine on his own life and business first. We only ship what we've used ourselves. → [ROADMAP.md](ROADMAP.md)

## Build it with us

Nobody succeeds alone. We need people who understand the idea: AI and memory engineers, mobile builders, security and privacy experts, Arabic NLP, designers, and people with real problems to solve.

**Fastest way in:** pick a spec from [tasks/](tasks/), build it (AI-assisted is welcome), send a pull request. See [CONTRIBUTING.md](CONTRIBUTING.md).

---

## بالعربي

**لكل البشر. لا عرق، لا دين، لا لون. فقط أرض أعظم وأفضل لكل البشر.**

**كن إنسان** محرك ذكاء اصطناعي مفتوح بالكامل، يوصلك فاضي ومعه الضوابط فقط. يتعلم منك بالصوت أو الكتابة، ويتكيف معك، ويوجهك تشتغل بالطريقة الصح.

هو ليس إنسان. هو يساعدك تكون إنسان أفضل. يقول لك هذا صح وهذا غلط، ولما ما يعرف يقول "ما أعرف" ويسألك عن اللي يحتاجه. أنت اللي تقرر، هو ينصح.

الهدف: كل ما تتقدم في المراحل وتفتح skills، تتطور أنت، لين تكون حياتك منظمة وعارف إيش مهمتك في هذي الحياة. رحلة متكاملة: عمل، إخلاص، صدق، وثقة.

هدفنا ٨ مليار إنسان. نتكلم بالعلم والدليل. ما في مقارنة بين الناس، كل واحد أحسن بطريقته.

المشروع مفتوح لأن ما أحد ينجح لوحده. اختار مهمة من [tasks/](tasks/)، ابنيها، وأرسل PR. اقرأ [CONTRIBUTING.md](CONTRIBUTING.md).

---

Licensed under [Apache 2.0](LICENSE). "كن إنسان" and "Kun Insan" names and logo are trademarks of the project and not covered by the code license.
