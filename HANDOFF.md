# HANDOFF — udagram-monolith-to-microservices

## Updated
2026-10-17 | Cursor Grok (Cloud Agent env-setup) | branch `cursor/udagram-preview-env-9396`

## Current task / claim
No board claim. This session set up a Cloud Agent environment. UMM-1 stays open and unclaimed. `/workspace/projects/board.sh` is not on this VM, so checkpoint was not run.

## Done this session
- Confirmed the checkout is `README.md` plus 12 PNG screenshots. No package manifest or app server.
- Documented the preview in `AGENTS.md` and decision D002.
- `install` passed twice (`archive ok: README.md + 12 png screenshots`).
- `start` serves the archive on port 8080. A second run sees it already up and exits 0.
- Browser check: README text, screenshot index, kubectl pods image, and Docker Hub image all render.
- Draft environment build `bld-20261017-96676fb8-2f6d-4a47-ad87-4e1045e34ba4` from snapshot `snapshot-20261017-b49c800f-72d6-4630-93c9-d29c56973d20`. A fresh agent booted that build. Python 3.12.3. Archive check passed. `/tmp/cursor/start-user/` was absent on that boot (saved environment has no `start` until Save). Running the start command there served README and a PNG with HTTP 200.

## Verified (with evidence)
- Local install x2, curl of README and all 12 screenshots (byte sizes match disk), browser screenshots under `/tmp/computer-use/`.
- Fresh agent `bc-f10c0535-3b77-549e-9815-5417fa45262f` reported build id `bld-20261017-96676fb8-2f6d-4a47-ad87-4e1045e34ba4`.

## Unverified
- Dashboard Save (user action). After Save, a new agent should show `/tmp/cursor/start-user/` and port 8080 without a manual start.

## Broken / half-done
- (none)

## Next 3 steps (smallest first)
1. Anil clicks Save on the environment card.
2. Optional: open a new Cloud Agent and confirm port 8080 is already serving `/README.md`.
3. UMM-1 only if Anil revives product work.

## Blockers / questions for Anil
- (none)

## How to resume
```sh
cd /workspace
python3 -m http.server 8080 --bind 0.0.0.0
# http://127.0.0.1:8080/README.md
# http://127.0.0.1:8080/screenshots/
```
