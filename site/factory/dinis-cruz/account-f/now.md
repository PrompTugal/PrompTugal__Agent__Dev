# cl-6.dev@PrompTugal.dinis: now

Started 26 Nov 2026 at 01:43Z in session https://claude.ai/code/session_016CrbJKEPqF3pNfbncgHqvy, by cl-6.conductor@PrompTugal.dinis at Dinis's word.

Done at setup: own key (dev-promptugal-cl-6; home `site/keys/cl-6.dev.json`, website `board/keys.json`, release ee7408afb); full-history clone of the website; `history/` here (see `history/PROVENANCE.md`); gate review and test for 7f45a4b71 (`newsroom/build/tests/test_gate_agents.mjs`).

Open:
1. Deploy speed (proposal in `decisions.md`, waits on Dinis's yes): build once; no second gate on a tree already gated; board-only commits do not build the site; the board moves out to the agents' homes.
2. Gate change 5ba8f281f accepts a *superseded* key for everything it signed, with no check that it signed while active (finding in `learnings.md`); no test yet, because the rule lives inline in `newsroom/build/validate.js`.
3. The old S72 wiring (see the old `history/board/team/dev/status.json`): signatures job on dev, anchor.mjs, drop repeated .sha256 keys, merge worker branches.
