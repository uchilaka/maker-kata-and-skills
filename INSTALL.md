# Install

Runbook. Commands in order; prose only where a step bites.

The repo is a filing cabinet with a locked drawer. Anyone can read the labels and take the
blank forms. The drawer needs a key. One folder never goes in the cabinet at all.

## 1. Clone and unlock

```bash
git clone git@github.com:uchilaka/maker-kata-and-skills.git
cd maker-kata-and-skills
```

**A clone without the key looks like binary garbage in `log/`, `journal/` and
`sources/private/`. That is correct, not broken** — and it is also the adopter
distribution: every script, config, track and kata works without a key.

```bash
brew install git-crypt                    # 0.8.0 or later
git-crypt unlock ~/.config/git-crypt/maker-kata-and-skills.key
git-crypt unlock ~/.config/git-crypt/maker-kata-and-skills.log-2026.key
```

Order matters, and this is the step that goes wrong:

```text
   clone ──▶ install git-crypt ──▶ unlock ──▶ doctor ──▶ first run
                                     │
                                     ↳ skipped? every tier-1 file is
                                       ciphertext, and writing over one
                                       destroys real content
```

`bin/kata` and `bin/doctor` both refuse to run on a locked repo. That guard has no
override, on purpose.

## 2. Shell

```bash
export KATA_PROFILE=personal     # or work — see step 4
export EDITOR=vim
```

Both are checked by `bin/doctor`. `bin/kata` refuses rather than guessing `KATA_PROFILE`,
because guessing wrong on a work machine is the case that matters.

## 3. Wire it in

```bash
bin/install              # dry run — prints every change outside the repo
bin/install --apply      # hooks + skills + launchd agent
bin/doctor               # must exit 0
```

`bin/install --apply` wires `core.hooksPath`, mounts the skills into `~/.claude/skills`,
and loads a weekday 07:15 agent that runs `bin/kata --prepare`. It never opens a terminal
— an agent that does trains you to dismiss it.

Restart Claude if a mounted skill does not show up. It has been seen appearing
mid-session, but that is not guaranteed.

## 4. On a work machine, decide the key question first

Does this machine hold the git-crypt key at all?

If it runs MDM, DLP, or a backup agent, unlocking here puts your decrypted journal on
monitored hardware — **the encryption buys nothing against the party most likely to read
it.** Either accept that deliberately, or skip the unlock and keep personal notes in
`/private` (tier 2, gitignored, never committed, backed up outside git).

Also confirm the machine's policy permits a personal repo and personal git identity.

## 5. Worktrees

```bash
bin/worktree-init <slug> [branch] [base-ref]
```

Use this, never a plain `git worktree add`. git-crypt keeps its key in `$GIT_DIR`, a
worktree gets its own and does not inherit it, and the failure is misleading: git rolls
the worktree back, so you get a missing directory rather than a broken one. The wrapper
installs every named key and verifies decryption before it returns.

## Daily

```bash
bin/kata              # prepare if needed, open the entry, commit and push
bin/kata --prepare    # render only (what the agent runs)
bin/kata --review     # compile REVIEW.md from the log history
```

## Verify the encryption after any .gitattributes change

```bash
git check-attr filter -- log/$(date +%Y)/01/01.md    # -> git-crypt-log-<year>
git check-attr filter -- log/LICENSE                 # -> unspecified
```

`git-crypt status` says "encrypted" without naming *which* key, so it cannot tell you a
year has rolled onto the default key. Re-run the check each January. The pre-commit hook
catches the same class of failure at commit time.

## Uninstall

```bash
bin/install --uninstall --apply
```

Unloads the agent, unmounts the skills, unsets the hook path. The repo and its history are
untouched.
