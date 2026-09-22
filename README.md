# maker-kata-and-skills

A daily practice that rehearses a craft rather than just reading about one, plus the
Claude Code skills that run it. Published so it can be forked; the practice record itself
stays encrypted.

**Status: early.** The machinery runs; the practice has not yet survived a month of real
use, which is the only test that matters. See **[INSTALL.md](INSTALL.md)**.

## Three tiers

```
┌─ tier 0 · public ────────────────────────────────────────┐
│  bin/  config/  practice/  skills/  sources/  README     │
│  plaintext — the machinery, meant to be taken            │
├─ tier 1 · encrypted (git-crypt) ─────────────────────────┤
│  log/  journal/  sources/private/  REVIEW.md             │
│  ciphertext here, plaintext on any machine with the key  │
├─ tier 2 · never committed ───────────────────────────────┤
│  /private/                                               │
│  gitignored, local to one machine, backed up elsewhere   │
└──────────────────────────────────────────────────────────┘
```

Think of it as a filing cabinet with a locked drawer. Anyone can read the labels and take
the blank forms. The drawer needs a key. And one folder never goes in the cabinet at all.

A clone without the key is the adopter distribution: every script, config and template
works, and only the tier-1 files are noise.

## Licence

Apache-2.0 for code, CC BY 4.0 for written content. `log/` is reserved — see `log/LICENSE`
for why.
