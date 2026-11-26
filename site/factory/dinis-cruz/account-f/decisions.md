# cl-6.dev@PrompTugal.dinis: decisions

## 2026-11-26: the deploy-speed proposal (for Dinis, before I change CI)

Measured by the conductor on 26 Nov (run 45735222327): about 11 minutes a push; validate job 5 min, release job 4 min; the site is 2,471 pages and 26,000 files, built and gated twice. Never weaken a check.

What the workflow does today (`.github/workflows/deploy-pages.yml`, read on 26 Nov): `validate` builds and runs `newsroom/build/validate.js` on the pushed commit; `release` (needs validate) runs `tag_release.sh`, which numbers, rebuilds and runs the gate again on the numbered tree *before* it commits or tags, then rsyncs and deploys.

1. **Drop the duplicate gate on dev pushes (recommended first).** The gate in `tag_release.sh` already runs on the exact tree that ships, before anything is committed, tagged or deployed, so a red tree is never numbered. The `validate` job on a dev push is the same gate on almost the same tree. Keep `validate` for pull requests, `work/**` and `main` (where there is no release), and let the dev release job run alone. Saves about 5 minutes; no check removed (the gate runs once, on the shipping tree). Risk: a red push now fails in the release job, not in validate; the failure is as visible. Needs a trial run to confirm the 11 minutes become about 6.
2. **Build once.** The version is written into every page, so a pre-numbered build cannot be reused as is. Options: (a) as 1; (b) make the version a post-build step (a small substitution over the output) so validate's tree is the release tree; (b) is bigger and changes the build, so not first.
3. **Board-only commits skip the site build.** Split the gate into checks that need the built pages and checks that read only source and data (schemas, keys, status files). A commit touching only `board/` (and `history/`-style files) runs the second group. The site must still deploy because `/board/` is served; for that, reuse the previous release's built tree and overlay `board/`. Needs care; second.
4. **Move the board out.** The board served at promptugal.news/board/ is most of the churn. Each agent's home repository now holds its own state (as this one does); once agents write there, board-only pushes to the website stop. This is the conductor's and Dinis's plan; I help by making the website's board read-only for agents as they move.

Asking Dinis: yes to 1 (I will try it on a branch and report the measured time), and which of 3 and 4 first.

## 2026-11-26 02:13Z: Dinis's yes, relayed

cl-6.conductor@PrompTugal.dinis relayed Dinis's word typed in its session (session_016CrbJKttr9TiHHDsuGnmF1): "yes, go ahead with dev's deploy-speed proposal". Conditions from the conductor: send the change to cl-6.security before it ships; the workflow and release scripts are devops' area too (say so in the commit); never weaken a check; report the before and after run times once live.

State at 02:15Z: the edit to `.github/workflows/deploy-pages.yml` (validate job `if: github.ref != 'refs/heads/dev'`; release job `if: !cancelled() && needs.validate.result != 'failure' && ...`) was refused by the session's auto-mode classifier ("Undermining Oversight": it reads the change as switching off a check). Nothing was changed in the workflow. Waiting on Dinis to allow it (a permission rule for editing the workflow, or his word in this session).
