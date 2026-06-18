# AGENTS

## Project Overview
Mona Mayhem is an Astro + Node app for comparing GitHub contribution graphs between users in a retro arcade style UI.

Use these docs for context:
- [README](README.md)
- [Astro config](astro.config.mjs)
- [Package scripts](package.json)

## Where To Work
Primary runtime code lives here:
- [UI page](src/pages/index.astro)
- [API route](src/pages/api/contributions/[username].ts)
- [Static assets](public/)

Ignore workshop materials for app implementation tasks:
- [Workshop content](workshop/)
- [Workshop site docs](docs/)

## Build and Dev Commands
- Install: `npm install`
- Dev server: `npm run dev`
- Production build: `npm run build`
- Preview build: `npm run preview`
- Astro CLI passthrough: `npm run astro`

## Astro and TypeScript Conventions
- Keep UI in `src/pages/*.astro` and server logic in `src/pages/api/**/*.ts`.
- Keep dynamic API routes as bracket files, for example `[username].ts`.
- Use typed Astro handlers: `import type { APIRoute } from 'astro'`.
- Return JSON with explicit status and `Content-Type: application/json`.
- Validate route params and handle external fetch failures.
- Project uses strict TypeScript via `astro/tsconfigs/strict`; avoid implicit `any`.

## Runtime Mode
- This app is server-rendered (`output: 'server'`) with the Node adapter.
- Do not switch to static output when adding runtime GitHub data fetching.
- Keep `prerender = false` for dynamic API endpoints that fetch live data.

## Safe Change Pattern
1. Make the smallest focused change.
2. Run `npm run build` to catch Astro/TS issues.
3. If API behavior changed, test the endpoint in dev mode.
4. Keep docs changes separate from runtime code changes unless explicitly requested.
