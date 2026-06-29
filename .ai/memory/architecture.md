# Architecture

No application code exists yet. This records the intended shape so early work stays
consistent. The repository currently holds project metadata (README, LICENSE) and
the Atlas AI workspace under `.ai/`.

## Intended shape

- A Next.js (App Router) app.
- User submits content from a client UI.
- A server-side route handler / server action calls the Vercel AI SDK to run the
  SEO analysis. AI keys and model calls stay server-side, never in the client.
- The model returns a structured assessment (findings: issue, why, fix), which the
  UI renders as explainable feedback rather than a single opaque score.
- Deployed on Vercel.

## Invariants

- Model/API keys are server-only; no provider calls from the browser.
- AI output is treated as a draft to be checked, not ground truth — surface
  reasoning so users can verify fixes.

## Current layout

- `.ai/` — Atlas AI workspace (config, memory, vocabulary, plans, research,
  decisions, results, skills). `.ai/config.json` is the source of truth for
  artifact locations.
- `AGENTS.md` / `CLAUDE.md` — agent instructions. `CLAUDE.md` imports `AGENTS.md`.
- `.agents/`, `.claude/`, `.cursor/` — generated agent surfaces.

## Unknowns (fill once code lands)

- App directory structure and module boundaries.
- Structured-output method (AI SDK `generateObject` / schema) and the schema shape.
- Whether analysis is streamed or returned whole.
- Data persistence and any database.
