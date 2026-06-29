# Project AI Instructions

## What this repo is

`blazity-hackaton` – a hackathon project building an **AI SEO checker**: a web app
where marketing/content teams submit content and the tool returns explainable,
actionable SEO fixes (not a vague score). Stack: **Next.js (App Router) + Vercel AI
SDK + TypeScript, deployed on Vercel**. No application code exists yet – the repo is
still a scaffold (README, LICENSE, and the Atlas workspace under `.ai/`). See
`.ai/memory/` for stable context: product, architecture, stack, vocabulary.

## Structure

- `.ai/` — Atlas AI workspace. `.ai/config.json` is the source of truth for
  artifact locations (memory, vocabulary, plans, research, decisions, results).
- `AGENTS.md` / `CLAUDE.md` — agent instructions; `CLAUDE.md` imports this file.
- `.agents/`, `.claude/`, `.cursor/` — generated agent surfaces.

## Working rules

- Stack is decided (Next.js + Vercel AI SDK + TS on Vercel) but not yet scaffolded.
  No `package.json` exists, so do not assume `dev`/`build`/`test` scripts – confirm
  the package manager and commands once the app lands, then update
  `.ai/memory/stack.md`.
- AI model/API keys are server-only. Never call a model provider from the browser.
- Treat AI output as a draft to be checked – surface reasoning, don't trust blindly.
- When wiring the Vercel AI SDK or Next.js, prefer the plugin's official docs over
  training memory (APIs change). Default model: latest Claude via the AI SDK.
- Only Atlas tooling is a known safe command so far:
  `npx --yes @blazity-atlas/core@latest doctor` checks workspace health.
- Do not edit the `<!-- BEGIN/END ATLAS -->` managed block below by hand.
- Keep durable docs depersonalized (see Atlas Documentation Rules below).

<!-- BEGIN ATLAS: artifact-paths -->
## Atlas Artifact Paths

`.ai/config.json` is the source of truth for AI artifact locations in this repository.
Before writing plans, research, decisions, ADRs, results, memory, vocabulary, or skill outputs, resolve the destination through `artifactRoot`, `paths`, and `pathAliases`.
If an imported skill, template, or instruction mentions a different path, map it through `.ai/config.json` before reading or writing files.
Do not create new documentation roots unless `.ai/config.json` explicitly allows them.

## Atlas Documentation Rules

Durable documentation records needs, decisions, and reasons — never individuals or internal process.
Write "memory was needed to persist context across runs", not "<name> wanted memory".
Keep personal names, private schedules, internal-only references, and absolute local paths out of workspace artifacts.
<!-- END ATLAS: artifact-paths -->
