# DECISIONS — udagram-monolith-to-microservices (append-only)

## D001 — Adopt AGENTS/PLAN/HANDOFF/DECISIONS handoff files (2026-10-15, Grok Bot for Anil)
- Decision: these repo files are the source of truth for agents; `/workspace/projects/BOARD.md` is only an index; claims via board.sh.
- Why: several agents (Codex, Cursor, agy) share this box and must not duplicate work.
- Alternatives rejected: one central board as source of truth.

## D002 — Preview the screenshot archive in the Cloud Agent environment (2026-10-17, Cursor Grok)
- Decision: Cloud Agent `install` checks `README.md` and `screenshots/*.png`. `start` serves the repo with `python3 -m http.server 8080` on the default image. Configuration stays in the dashboard environment, not a committed `.cursor/environment.json`.
- Why: the repository is a write-up and screenshot archive. It has no lockfile, tests, or service process. A static preview is the end-to-end development flow.
- Alternatives rejected: cloning the separate Udagram service repositories into this environment (they are different products and need database and cloud credentials); committing `.cursor/environment.json` (a repo file would override the personal dashboard environment).
