# S9: keys with no ssh field (26 Nov 2026, cl-6.dev)

110 entries of board/keys.json are active with no ssh key (cl-6.security says 109 at an earlier read), so no check that reads `ssh` can accept them, while the article gate still does. The commit prepared on the local branch `prep/keys-superseded` of the website clone (not pushed; patch beside this file: `2026-11-26-s9-keys-superseded.patch`, applies to dev at the time) marks 87 of them superseded. 21 are held (another operator's lane) and 2 are held (current cl-6 sessions whose entry lacks the ssh field).

How I decided (evidence, not guess): an entry is marked only if (1) its agent is `*@PrompTugal.dinis` and not one of the 41 cl-6 sessions in the conductor's sessions list, and (2) it did not commit in the last 48 hours. "Last use" is the newest commit in this repository whose author or Agent: trailer names the agent (agent level; keys do not sign commits here without an ssh field). A "session ended" claim is therefore: not in the cl-6 list and no recent commit; I cannot see the old sessions themselves. Where a cl-6 successor with an active ssh key exists it is named.

The commit needs an operator's signature: the keys.json check (lib/keys-changes.mjs) reports every one of these entries as a change not signed by its own agent, because none of those agents can sign for an ended session. That is correct. It goes in once Dinis's key is published, as he is the only operator. `superseded_in` is not set: it needs the id of the commit that carries the change, so a second tiny commit adds it, as for the earlier entries.

## Marked superseded (87)

| id | agent | last_use | commits | successor | evidence |
|---|---|---|---|---|---|
| synthetic-promptugal | synthetic@PrompTugal.dinis | never | 0 | synthetic-promptugal-cl-6 | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits); replaced by synthetic-promptugal-cl-6 |
| observability-promptugal | observability@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| accountant-promptugal | accountant@PrompTugal.dinis | 2026-11-16T06:53 | 48 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T06:53 (48 commits) |
| librarian-promptugal | librarian@PrompTugal.dinis | 2026-11-12T13:01 | 37 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-12T13:01 (37 commits) |
| dev.graphs-promptugal-2 | dev.graphs@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| dev.verify-b-promptugal | dev.verify@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| claims-issuer-promptugal | observability@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| designer.experiments-b-promptugal | designer.experiments@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| customers-b-promptugal | customers@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| backup-b-promptugal | backup@PrompTugal.dinis | never | 0 | backup-promptugal-cl-6 | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits); replaced by backup-promptugal-cl-6 |
| dev.search-promptugal-2 | dev.search@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| dev.pages-b-promptugal | dev.pages@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| dev.data-b-promptugal | dev.data@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| dev.portugal-b-promptugal | dev.portugal@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| investors.packs-promptugal | investors.packs@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| journalist.newsroom-promptugal | journalist.newsroom@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| reporter.newsroom-promptugal | reporter.newsroom@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| social-watch-promptugal | social.watch@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| conductor.fringe-promptugal | conductor.fringe@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| place.aljezur-promptugal | place.aljezur@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| site.aljezur-promptugal | place.aljezur@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| place.vila-do-bispo-promptugal | place.vila-do-bispo@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| site.vila-do-bispo-promptugal | place.vila-do-bispo@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| place.alcoutim-promptugal | place.alcoutim@PrompTugal.dinis | 2026-11-16T02:59 | 2 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T02:59 (2 commits) |
| place.quarteira-promptugal | place.quarteira@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| place.portugal-promptugal | place.portugal@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| site.portugal-promptugal | place.portugal@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| place.monchique-promptugal | place.monchique@PrompTugal.dinis | 2026-11-16T04:44 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T04:44 (1 commits) |
| site.monchique-promptugal | place.monchique@PrompTugal.dinis | 2026-11-16T04:44 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T04:44 (1 commits) |
| place.albufeira-promptugal | place.albufeira@PrompTugal.dinis | 2026-11-16T20:16 | 8 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T20:16 (8 commits) |
| place.vila-real-de-santo-antonio-promptugal | place.vila-real-de-santo-antonio@PrompTugal.dinis | 2026-11-16T03:26 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T03:26 (1 commits) |
| place.sao-bras-de-alportel-promptugal | place.sao-bras-de-alportel@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| place.lagos-promptugal | place.lagos@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| site.lagos-promptugal | place.lagos@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| place.algarve-promptugal | place.algarve@PrompTugal.dinis | 2026-11-16T15:27 | 19 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T15:27 (19 commits) |
| place.lagoa-promptugal | place.lagoa@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| site.lagoa-promptugal | place.lagoa@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| place.faro-promptugal | place.faro@PrompTugal.dinis | 2026-11-16T00:11 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T00:11 (1 commits) |
| place.olhao-promptugal | place.olhao@PrompTugal.dinis | 2026-11-16T00:34 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T00:34 (1 commits) |
| place.tavira-promptugal | place.tavira@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| place.castro-marim-promptugal | place.castro-marim@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| place.silves-promptugal | place.silves@PrompTugal.dinis | 2026-11-16T15:33 | 14 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T15:33 (14 commits) |
| site.silves-promptugal | place.silves@PrompTugal.dinis | 2026-11-16T15:33 | 14 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T15:33 (14 commits) |
| place.portimao-promptugal | place.portimao@PrompTugal.dinis | 2026-11-16T00:28 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T00:28 (1 commits) |
| site.portimao-promptugal | place.portimao@PrompTugal.dinis | 2026-11-16T00:28 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T00:28 (1 commits) |
| place.loule-promptugal | place.loule@PrompTugal.dinis | 2026-11-16T01:30 | 2 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T01:30 (2 commits) |
| data.places-promptugal | data.places@PrompTugal.dinis | 2026-11-16T15:32 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T15:32 (1 commits) |
| viz.places-promptugal | viz.places@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| detective.places-promptugal | detective.places@PrompTugal.dinis | 2026-11-16T20:11 | 18 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T20:11 (18 commits) |
| site.aveiro-promptugal-2 | place.districts@PrompTugal.dinis | 2026-11-16T05:29 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T05:29 (1 commits) |
| site.leiria-promptugal-2 | place.districts@PrompTugal.dinis | 2026-11-16T05:29 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T05:29 (1 commits) |
| security-promptugal-2 | security@PrompTugal.dinis | 2026-11-24T11:12 | 50 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-24T11:12 (50 commits) |
| site.albufeira-promptugal | place.algarve.central@PrompTugal.dinis | 2026-11-21T07:32 | 2 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-21T07:32 (2 commits) |
| site.loule-promptugal | place.algarve.central@PrompTugal.dinis | 2026-11-21T07:32 | 2 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-21T07:32 (2 commits) |
| site.quarteira-promptugal | place.algarve.central@PrompTugal.dinis | 2026-11-21T07:32 | 2 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-21T07:32 (2 commits) |
| site.faro-promptugal | place.algarve.central@PrompTugal.dinis | 2026-11-21T07:32 | 2 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-21T07:32 (2 commits) |
| site.sao-bras-de-alportel-promptugal | place.algarve.central@PrompTugal.dinis | 2026-11-21T07:32 | 2 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-21T07:32 (2 commits) |
| site.olhao-promptugal | place.algarve.central@PrompTugal.dinis | 2026-11-21T07:32 | 2 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-21T07:32 (2 commits) |
| site.tavira-promptugal-2 | place.algarve.east@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| site.castro-marim-promptugal-2 | place.algarve.east@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| site.vila-real-de-santo-antonio-promptugal-2 | place.algarve.east@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| site.alcoutim-promptugal-2 | place.algarve.east@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| site.algarve-promptugal-2 | place.algarve.east@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| site.lisboa-promptugal-2 | place.districts@PrompTugal.dinis | 2026-11-16T05:29 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T05:29 (1 commits) |
| site.porto-promptugal-2 | place.districts@PrompTugal.dinis | 2026-11-16T05:29 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T05:29 (1 commits) |
| site.coimbra-promptugal-2 | place.districts@PrompTugal.dinis | 2026-11-16T05:29 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T05:29 (1 commits) |
| site.braga-promptugal-2 | place.districts@PrompTugal.dinis | 2026-11-16T05:29 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T05:29 (1 commits) |
| site.viana-do-castelo-promptugal-2 | place.districts@PrompTugal.dinis | 2026-11-16T05:29 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T05:29 (1 commits) |
| site.vila-real-promptugal-2 | place.districts@PrompTugal.dinis | 2026-11-16T05:29 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T05:29 (1 commits) |
| site.braganca-promptugal-2 | place.districts@PrompTugal.dinis | 2026-11-16T05:29 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T05:29 (1 commits) |
| site.viseu-promptugal-2 | place.districts@PrompTugal.dinis | 2026-11-16T05:29 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T05:29 (1 commits) |
| site.guarda-promptugal-2 | place.districts@PrompTugal.dinis | 2026-11-16T05:29 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T05:29 (1 commits) |
| site.santarem-promptugal-2 | place.districts@PrompTugal.dinis | 2026-11-16T05:29 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T05:29 (1 commits) |
| site.castelo-branco-promptugal-2 | place.districts@PrompTugal.dinis | 2026-11-16T05:29 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T05:29 (1 commits) |
| site.portalegre-promptugal-2 | place.districts@PrompTugal.dinis | 2026-11-16T05:29 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T05:29 (1 commits) |
| site.setubal-promptugal-2 | place.districts@PrompTugal.dinis | 2026-11-16T05:29 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T05:29 (1 commits) |
| site.evora-promptugal-2 | place.districts@PrompTugal.dinis | 2026-11-16T05:29 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T05:29 (1 commits) |
| site.beja-promptugal-2 | place.districts@PrompTugal.dinis | 2026-11-16T05:29 | 1 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit 2026-11-16T05:29 (1 commits) |
| data.b-promptugal | data.b@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| weather.b-promptugal | weather.b@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| civic.b-promptugal | civic.b@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| events.b-promptugal | events.b@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| startups.b-promptugal | startups.b@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| travel.b-promptugal | travel.b@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| videos.b-promptugal | videos.b@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| library.b-promptugal | library.b@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |
| cyber.b-promptugal | cyber.b@PrompTugal.dinis | never | 0 | None | not among the 41 cl-6 sessions of the conductor's list (2026-11-26-sessions.json); last commit none: the key was never used for a commit (0 commits) |

## Held: another operator or team lane, how it is governed is A8, Dinis's (21)

| id | agent | last_use | commits | why |
|---|---|---|---|---|
| journalist-connections-vicky-promptugal-c | journalist-connections@PrompTugal.vicky | 2026-11-11T06:18 | 8 | another operator or team lane (PrompTugal.vicky); how those lanes are governed is A8, Dinis's |
| curator-vicky-3-promptugal | curator@PrompTugal.vicky | 2026-11-26T12:51 | 127 | another operator or team lane (PrompTugal.vicky); how those lanes are governed is A8, Dinis's |
| designer-vicky-promptugal | designer@PrompTugal.vicky | never | 0 | another operator or team lane (PrompTugal.vicky); how those lanes are governed is A8, Dinis's |
| writer-angelo-promptugal | writer@PrompTugal.angelo | 2026-11-10T08:49 | 13 | another operator or team lane (PrompTugal.angelo); how those lanes are governed is A8, Dinis's |
| writer-jose-promptugal | writer@PrompTugal.jose | 2026-11-07T20:16 | 1 | another operator or team lane (PrompTugal.jose); how those lanes are governed is A8, Dinis's |
| gamma-ray-promptugal | gamma-ray@web-summit.dinis | 2026-11-10T00:39 | 9 | another operator or team lane (web-summit.dinis); how those lanes are governed is A8, Dinis's |
| conductor.B.vicky-promptugal | conductor.B@PrompTugal.vicky | never | 0 | another operator or team lane (PrompTugal.vicky); how those lanes are governed is A8, Dinis's |
| journalist-portugal-vicky-promptugal-c | journalist-portugal@PrompTugal.vicky | 2026-11-20T08:51 | 20 | another operator or team lane (PrompTugal.vicky); how those lanes are governed is A8, Dinis's |
| weather-vicky-promptugal | weather@PrompTugal.vicky | never | 0 | another operator or team lane (PrompTugal.vicky); how those lanes are governed is A8, Dinis's |
| conductor.fringe-vicky | conductor.fringe@PrompTugal.vicky | never | 0 | another operator or team lane (PrompTugal.vicky); how those lanes are governed is A8, Dinis's |
| conductor.fringe-angelo | conductor.fringe@PrompTugal.angelo | never | 0 | another operator or team lane (PrompTugal.angelo); how those lanes are governed is A8, Dinis's |
| conductor-vicky-3-promptugal | conductor@web-summit.vicky | 2026-11-11T21:08 | 4 | another operator or team lane (web-summit.vicky); how those lanes are governed is A8, Dinis's |
| journalist-europe-vicky-promptugal-c | journalist-europe@PrompTugal.vicky | 2026-11-21T15:45 | 7 | another operator or team lane (PrompTugal.vicky); how those lanes are governed is A8, Dinis's |
| journalist-ai-vicky-promptugal-2 | journalist-ai@PrompTugal.vicky | 2026-11-26T14:54 | 25 | another operator or team lane (PrompTugal.vicky); how those lanes are governed is A8, Dinis's |
| checker-vicky-promptugal-c | checker@PrompTugal.vicky | 2026-11-17T10:17 | 53 | another operator or team lane (PrompTugal.vicky); how those lanes are governed is A8, Dinis's |
| dev-vicky-promptugal-c | dev@PrompTugal.vicky | 2026-11-11T21:26 | 16 | another operator or team lane (PrompTugal.vicky); how those lanes are governed is A8, Dinis's |
| reviewer-vicky-promptugal-3 | reviewer@PrompTugal.vicky | 2026-11-26T15:46 | 90 | another operator or team lane (PrompTugal.vicky); how those lanes are governed is A8, Dinis's |
| reporter-vicky-promptugal | reporter@PrompTugal.vicky | 2026-11-14T10:37 | 1 | another operator or team lane (PrompTugal.vicky); how those lanes are governed is A8, Dinis's |
| analyst-vicky-promptugal | analyst@PrompTugal.vicky | 2026-11-23T10:23 | 21 | another operator or team lane (PrompTugal.vicky); how those lanes are governed is A8, Dinis's |
| conductor-jose-promptugal | conductor@PrompTugal.jose | never | 0 | another operator or team lane (PrompTugal.jose); how those lanes are governed is A8, Dinis's |
| local-jose-promptugal | local@PrompTugal.jose | 2026-11-16T23:55 | 1 | another operator or team lane (PrompTugal.jose); how those lanes are governed is A8, Dinis's |

## Held: a current cl-6 session whose entry lacks the ssh field; the owner fixes its own entry (2)

| id | agent | last_use | commits | why |
|---|---|---|---|---|
| researcher-promptugal-cl-6 | cl-6.researcher@PrompTugal.dinis | 2026-11-26T02:34 | 1 | a current cl-6 session; its key entry lacks the ssh field: the owner fixes the entry |
| cl-6.curator-promptugal | cl-6.curator@PrompTugal.dinis | 2026-11-26T02:42 | 2 | a current cl-6 session; its key entry lacks the ssh field: the owner fixes the entry |
