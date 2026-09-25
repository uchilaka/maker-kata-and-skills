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
- `/kata-today` — a run menu that launches each practice block, with catch-ups first.
  It ships a signed Apple Journal Shortcut (`skills/kata-today/shortcuts/`) for voice
  entries: import it once per Mac instead of building it by hand.
- `.githooks/pre-commit` — refuses staged key material and plaintext on a tier-1 path.
- Skills: `pro-voice`, `kata-init`, `kata-release`.
- Skill: `make-design-system` — adapts one of 68 curated `DESIGN.md` inspirations into an
  original design system for Claude Design. The catalog is vendored from
  VoltAgent/awesome-claude-design (MIT) and regenerated with `scripts/build-catalog`;
  `scripts/check-design-md` catches dangling token references, missing sections and
  surviving source brand names offline.
- Katas: `read-a-subsystem`, `explain-it-to-a-twelve-year-old`. Tracks: systems, identity.
- Licensing: Apache-2.0 (code), CC BY 4.0 (prose), all rights reserved (`log/`).
- Markdown linting: one `.markdownlint-cli2.yaml` read by both the CLI and the VS Code
  extension, a warn-only pre-commit check over staged `*.md`, and a `Brewfile` pinning
  `markdownlint-cli2` and `gitleaks`. `.vscode/` settings travel with the clone, so
  lint-on-save needs no per-machine setup. A repo-wide run must name its paths —
  `markdownlint-cli2 "**/*.md"` — because the config sets no `globs:` on purpose: config
  globs are appended to command-line paths, which would widen the hook from the files you
  staged to the whole repo.

### Fixed

- `bin/doctor` no longer reports a loaded launchd agent as missing. The schedule check
  piped `launchctl list` into `grep -q` under `pipefail`, so the producer died of SIGPIPE
  and the pipeline returned 141 rather than grep's 0. `bin/doctor` can now exit 0 on a
  correctly installed machine, which was not previously reachable.

### Known gaps

- `bin/kata` does not yet fetch feeds into the Scan block; `sources/feeds.opml` is a stub.
- No eval for `pro-voice`. The plan wants one before a second skill migrates onto it.
