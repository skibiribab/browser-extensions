# core

The real, browser-agnostic extension logic. Everything here must run identically in Chrome and Firefox — no `browser`/`chrome` platform specifics.

Examples of what lives here: "talk with ChatGPT", page snapshotting, clipboard automation — the actual behavior. Per-browser wiring (manifest, entrypoints, build) lives in `chrome/` and `firefox/`.

See issues: Core structure · Migrate Recorder logic.
