# Browser-extensions conventions

Workspace of browser extensions. Each extension lives under `extensions/` with its own source and build output.

## Structure

- `extensions/<name>/` — one extension per folder.
- `src/` — shared lib (background, content, options, popup).
- `tests/` — tests.
- `docs/` — development + release docs.

## Rules

- Manifest V3; currently Chrome-first, cross-browser (Firefox) planned.
- Run the PR pipeline (docker targets `lint` / `repo-hygiene` / `unit-test` / `build`) before merging — `test.yml` routes it through the `control-plane` PR router.
- Theme: `GitHub Dark Default`.

## CI

- `test.yml` — PR gate: calls the `control-plane` pull-request-router.
- `release.yml` — main: validate + timestamp tag + GitHub release.
