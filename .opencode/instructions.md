# Browser-extensions conventions

Workspace of browser extensions. Client-side, mostly no backend.

## Structure

- `src/lib/` — the real, browser-agnostic logic (tests nested).
- `src/chrome/` — Chrome adapter: MV3 manifest, entrypoints, build (tests nested).
- `src/firefox/` — Firefox adapter: MV2 manifest, entrypoints, build (tests nested).
- `docker/` — CI Dockerfile (lint → structure → unit → build).

## Rules

- Real logic lives in `src/lib/` only; each browser adapts it.
- AI-assisted features (e.g., chat helper in Slack) are exploratory.
- The PR pipeline routes through the `control-plane` pull-request-router (builds `docker/Dockerfile` targets).
- Theme: `GitHub Dark Default`.

## CI

- `test.yml` — PR gate: calls the `control-plane` pull-request-router.
- `release.yml` — main: validate + timestamp tag + GitHub release.
