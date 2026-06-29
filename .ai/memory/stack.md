# Stack

Web app built on Next.js (App Router) with the Vercel AI SDK, deployed to Vercel.
TypeScript. The application code does not exist in the repository yet; this records
the chosen direction.

## Decided

- Framework: Next.js (App Router).
- Language: TypeScript.
- AI: Vercel AI SDK (`ai`), used from server-side route handlers / server actions.
- Default model provider: Claude (latest Opus/Sonnet) via the AI SDK Anthropic
  provider, unless changed. Prefer the latest, most capable model for analysis.
- Hosting: Vercel.

## Tooling notes

- Atlas (`@blazity-atlas/core`) manages the AI workspace:
  `npx --yes @blazity-atlas/core@latest doctor`.
- This repo carries the Vercel Claude Code plugin; its AI SDK / Next.js docs are
  authoritative over training memory when wiring the SDK.

## Unknowns (fill once scaffolded)

- Package manager (npm / pnpm / bun) and lockfile.
- Run / build / test commands (none exist yet — do not assume `dev`/`build`/`test`
  until `package.json` lands).
- UI layer choice (e.g. shadcn/ui, Tailwind) and component library.
- Whether AI Gateway is used for model routing.
- Required env vars (e.g. provider API key).
