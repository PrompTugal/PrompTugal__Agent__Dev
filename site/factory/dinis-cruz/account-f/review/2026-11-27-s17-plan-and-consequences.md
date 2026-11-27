# S17: the /login/ key patch, its plan for revocation and retirement, and what it breaks (cl-6.dev, 27 Nov 2026)

Patch: `2026-11-27-s17-login-keys.patch` (website commit 54f9959fe, not released). Covers cl-6.security's a, b, c, d, f; e is a later step that needs Dinis.

## What the patch does
- `/login/key/` (new bare page, `assets/login/key-page.json`): CSP `default-src 'none'; script-src 'self'; style-src 'self'; img-src 'self'; connect-src 'self'; font-src 'self'; object-src 'none'; base-uri 'none'; form-action 'none'`; the frame guard runs before the key is used. Its words are data (`key-words.json`).
- `keyring.js` rewritten: make in the browser (the only place an extractable key exists), PBKDF2-SHA-256 600 000 rounds + AES-256-GCM, random salt and IV, parameters in the header and bound as AAD, passphrase of 12 or more characters; non-extractable keys in memory only; "Remember on this device" is an opt-in tick (IndexedDB `pt-keyring-2`); `sign()` needs `navigator.userActivation.isActive`; the old `pt-keyring` store and `pt.me` are deleted on load and the page says so; `add()` (the `#key=` import) throws.
- `login.js`: reports who is signed in (key held and fingerprint an active entry of `board/person-keys.json`); never signs; the `/login/` panel links to the key page. QR and camera code removed (the vendored jsQR stays on disk, still checked).
- `login.mjs`: `KEYRING_PAGES` has `login/key/` in place of `login/` (the content page no longer loads the key at all). Footer link added in `data/site/nav.json`.
- `person-key.mjs`: `issue` and `link` exit "retired"; `seal`, `open`, `verify` stay (public keys and existing envelopes), history untouched.
- `obs-view.js`: the paste-a-key-link box is replaced by a link to the key page.
- `test_keyring.mjs` (Node, WebCrypto): backup has no plain private half, wrong passphrase and a changed header refused, short passphrase refused, same key after unlock, signing without a gesture refused, fingerprint scheme, old store deleted. Checked in Chromium end to end: make, download, sign, reload (key gone), unlock from the file; no console or CSP errors. Gate OK (14 checks).

## What it breaks, so it is NOT released until Dinis says go
1. Dinis's drain: `newsroom/observability/sealed/dinis.json` is sealed to the agent-issued key. After this patch the old key cannot be loaded anywhere (it was only ever a link). Until Dinis has a browser-made key AND the sealed envelope is re-sealed to it, the Observability drain page cannot open the vault keys. Re-sealing needs someone who can open the current envelope (the issuing agent's session holds the private half; it may be gone). Open question for Dinis and the owner of the vaults: the safe order is (1) Dinis makes his key on the new page (needs the page live), (2) enrolment, (3) re-seal, (4) revoke.
   So the patch can go live without breaking anything only if the old browser key is not in use; otherwise release is a decision for Dinis (through cl-6.decisions).
2. `/talk/` and the observability page read `PTKeyring.person`, which is now set only when the key is held (memory, or remembered) and its fingerprint is an active entry of `board/person-keys.json`. Until Dinis's new key is enrolled they show "sign in".
3. `content/login.md` still describes the QR-code flow (content, not mine): it needs the conductor's or the content owner's rewrite; a suggested text is below.

## Revoking the two agent-issued keys (e) and retiring the tool (f)
- (f) is in the patch.
- (e) after Dinis's browser-made key is enrolled: `board/person-keys.json` gets the new entry (person, fingerprint, signing_fingerprint, JWKs public, `status: active`, `issued_by: "the person's own browser"`, `valid`), and the two agent-issued entries get `status: "revoked"`, `revoked_at`, `revoked_in` (the commit). No new sealing to an old key. A key change in `board/person-keys.json` is a one-line gate rule I add then: a revoked key may not become active again, and an active key must have an enrolment statement once the provenance design's `board/people-enrolments.json` exists.

## Suggested text for content/login.md (for whoever holds content)
"Editors make their own key on the [key page](key/index.html), in their own browser. The key is never made or held by an agent. A backup file sealed with your own passphrase is the only way back. Send the public key to Dinis; enrolment is a public, signed statement. Readers need no key."
