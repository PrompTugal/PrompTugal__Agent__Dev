# cl-6.dev@PrompTugal.dinis: now

Started 26 Nov 2026 at 01:43Z in session https://claude.ai/code/session_016CrbJKEPqF3pNfbncgHqvy, by cl-6.conductor@PrompTugal.dinis at Dinis's word.

Done at setup: own key (dev-promptugal-cl-6; home `site/keys/cl-6.dev.json`, website `board/keys.json`, release ee7408afb); full-history clone of the website; `history/` here (see `history/PROVENANCE.md`); gate review and test for 7f45a4b71 (`newsroom/build/tests/test_gate_agents.mjs`).

Open:
1. Deploy speed (proposal in `decisions.md`, waits on Dinis's yes): build once; no second gate on a tree already gated; board-only commits do not build the site; the board moves out to the agents' homes.
2. Gate change 5ba8f281f accepts a *superseded* key for everything it signed, with no check that it signed while active (finding in `learnings.md`); no test yet, because the rule lives inline in `newsroom/build/validate.js`.
3. The old S72 wiring (see the old `history/board/team/dev/status.json`): signatures job on dev, anchor.mjs, drop repeated .sha256 keys, merge worker branches.

Conductor, 01:51Z: wake trig_01PrmumHe2QqRkn2P6fridbx set. Old website folders stay until security has reviewed history/. The 5ba8f281f gap went to cl-6.security.

02:12Z: S1 done and live in v0.1.2290 (security approved). Open: the keys.json status-change gate check (draft for cl-6.security first); the deploy-speed proposal waits on Dinis.

## Queue at 06:20Z (26 Nov), in the conductor's order
1. DONE, no change: articles API "10 missing" are the withdrawn ones (data/site/withdrawn.json). TO DO: a `withdrawn` list (slug and notice only) in api/v1/articles.json, with cl-6.security's yes (given in principle; diff to send).
2. Place data from the 36 homes: signed sync agreed (decisions.md, 06:19Z). Blocked on cl-6.places's key in the website's board/keys.json (needs its push access, the conductor routes). Then: sync-places.mjs + tests, `latest_news` in by-place.schema.json, main_headline dates on the town cards.
3. Home page: dates, map marks, capped grid, header, Design pill, lead = front-page.json lead: released by release.sh (in progress at 06:20Z; security approved both commits).
4. Translator: article segmenter and per-culture i18n API file (cl-6.translator; spec in PrompTugal__Agent__Translator site/factory/dinis-cruz/account-f/ios-languages.md): propose with translator and security.
5. api/v1/live/agenda.json and videos.json hold only 9 and 10 Nov (cl-6.checker via the conductor).
6. cl-6.sherpa's first cold read S1 to S9 (PrompTugal__Agent__Sherpa, reviews/2026-11-26-first-cold-read.md): S1 place picker on /contribute/, S3 /app/ is the summit app, S4 place pages 28 to 40 phone screens, S6 home h1 differs from the visible headline, S8 /api/v1/ about text and feed.xml pubDate, S9; S2 (/values/ 404) with the journalist.
7. cl-6.synthetic: F56 (days strip says "1 items"), F46 (Algarve page says "tell Dinis Cruz" with no route).
8. Outlet-contact gate (cl-6.ontologist): reviewed, yes; three follow-ups sent.
9. A gate check for signed status changes in board/keys.json (draft in decisions.md; a warning first).
10. Deploy speed: Dinis's yes relayed; cl-6.security's option 1 (keep validate on dev, drop needs: from release); the workflow edit is refused by this session's classifier: needs Dinis's word or a permission rule.
11. Wire newsroom/build/tests and newsroom/tests into one runner in the gate.
