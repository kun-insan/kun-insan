# Task 07 — Kun Insan Certified benchmark

**Spec:** [docs/runtime.md](../docs/runtime.md#kun-insan-certified-model-benchmark)

## Must
- Test sets (synthetic): guardrail adherence, honest "I don't know", Arabic + English quality, tool use, task accuracy.
- Runner that calls any model through a simple adapter interface.
- Scores per test + pass/fail per model; thresholds in a config file.
- Results written as a dated report (Markdown + JSON).
- Easy to re-run monthly.

## Done when
Runs against at least one cloud model and one local open-weight model, with a sample report committed (no API keys in the repo).
