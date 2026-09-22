---
name: kata-release
description: Cut a semver release of the kata practice and its skills, so another device can adopt a known version. Use when the user says "/kata-release", "cut a release", "tag a version", "release the kata repo", or wants to install this on a second machine at a pinned version. Proposes the bump level from the commits since the last tag and says why, writes the CHANGELOG entry, tags, and emits the bootstrap for a new device.
---

# /kata-release — cut a version

**One version for the whole repo**, covering katas and skills together. Per-skill
versioning is real monorepo tooling and nobody has asked for it. The rule instead: *a
skill that outgrows this repo leaves for its own repo, and not before.*

## The property this is built around

**A keyless clone already is the adopter distribution.** Clone without the git-crypt key
and every script, config, track and kata works; only the tier-1 files are noise. Nothing
has to be stripped or packaged, so a release is a tag plus an install path — not a build.

## Refuse to release when

Check these first and stop on any of them. A release is a thing other people pin to.

- The working tree is dirty. `git status --porcelain` must be empty.
- `bin/doctor` exits non-zero.
- `git-crypt status` reports anything unexpected — in particular any tier-1 path listed as
  *not encrypted*.
- The current branch is not `main`, or `main` is behind `origin/main`.

## Choosing the bump

Read `git log <last-tag>..HEAD`. Propose a level and **say which commits drove it** — a
bump nobody can trace is a number, not information.

| Bump | Means | Test |
| ---- | ----- | ---- |
| **MAJOR** | Config schema or log format changed so an existing install breaks | Would someone's `config/default.yml` stop working? Would `bin/kata --review` misread old entries? |
| **MINOR** | New track, kata, skill, automation or capability | Existing installs keep working untouched |
| **PATCH** | Fixes, source-list updates, doc corrections | Nothing anyone depends on changed shape |

Be strict at the boundary, because this is where version numbers stop meaning anything:

- **Adding a source is a PATCH.** Even a good one.
- **Changing what a track *means* is a MINOR.** New prompts are a patch; a redefined track
  is a new capability for anyone following it.
- **Renaming a config key is a MAJOR.** However small. Someone has that key in a file.
- **Adding a kata is a MINOR. Promoting a candidate to a kata is a MINOR.** The library is
  the product.

A MAJOR requires a migration note in the changelog saying what to change and in what
order. A MAJOR without one is not ready.

## Steps

1. Run the refusal checks. Report which passed.
2. `git log --oneline "$(git describe --tags --abbrev=0 2>/dev/null || echo '')"..HEAD`
   — with no tags yet, the first release is `v0.1.0` unless the user says otherwise.
   Do not open at `v1.0.0`: it claims a stability the practice has not earned until it has
   survived a few weeks of real use.
3. Propose the bump with its evidence. **Wait for confirmation.** Never tag unprompted.
4. Write the `CHANGELOG.md` entry — Keep a Changelog headings, newest first, grouped
   Added / Changed / Fixed / Removed. Every entry says what it means for someone running
   the previous version, not what the diff did.
5. Commit the changelog, tag `vX.Y.Z` annotated with the same summary, push both.
6. Emit the adopter bootstrap (below) and tell the user to run it on the other machine.

## The bootstrap this emits

```bash
git clone git@github.com:<owner>/maker-kata-and-skills.git
cd maker-kata-and-skills && git checkout vX.Y.Z

# Machinery works from here. Skip the next two lines to adopt without the practice record.
git-crypt unlock ~/.config/git-crypt/maker-kata-and-skills.key
git-crypt unlock ~/.config/git-crypt/maker-kata-and-skills.log-<year>.key

export KATA_PROFILE=work        # or personal
bin/install --apply
bin/doctor
```

Say plainly which lines an adopter (as opposed to the author on a second machine) should
skip, and that skipping them is expected rather than a degraded mode.
