# Changelog

Keep a Changelog format. Every entry says what it means for someone running the previous
version, not what the diff did.

## [Unreleased]

### Added
- Encryption baseline: three tiers (public / git-crypt / never-committed), with `log/`
  keyed per year so a key grant is bounded to one year of source material.
- `bin/doctor` — preflight checks, all of them for failures that are otherwise silent.
- `bin/kata` — `--prepare`, interactive run, `--review`, `--dry-run`.
- `bin/mount-skills` — links skills into `~/.claude/skills`, never clobbering.
- `bin/install` / `bin/worktree-init` — machine wiring and git-crypt-safe worktrees.
- `.githooks/pre-commit` — refuses staged key material and plaintext on a tier-1 path.
- Skills: `pro-voice`, `kata-init`, `kata-release`.
- Katas: `read-a-subsystem`, `explain-it-to-a-twelve-year-old`. Tracks: systems, identity.
- Licensing: Apache-2.0 (code), CC BY 4.0 (prose), all rights reserved (`log/`).

### Known gaps
- `bin/kata` does not yet fetch feeds into the Scan block; `sources/feeds.opml` is a stub.
- No eval for `pro-voice`. The plan wants one before a second skill migrates onto it.
- `gitleaks` is not installed on the author's machine, so the pre-commit secret scan is
  skipped with a note. The two native guards run regardless.
