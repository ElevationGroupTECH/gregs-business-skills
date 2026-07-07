# Contributing / Maintainer Notes

> Short, but important — read before editing skills in this repo.

## Source of truth

The **active, working skills live outside this repo** in the maintainer's Claude config:

```
~/.claude/commands/projekt-starten.md      ← active DE source (richest version)
~/.claude/commands/projekt-review.md       ← active DE source (richest version)
```

These active files are the **single source of truth** for the German skills. They are
deliberately rich (Impact/Resources guiding principle, Patterns A–D, Program level, …).

This repo (`plugins/...`) is the **distribution copy** — what the marketplace/update
mechanism serves to users.

## Golden workflow (do not blind-overwrite SKILL.md)

The conflict that motivated these notes was caused by a full-body overwrite of `SKILL.md`
from an out-of-date local copy. Avoid that:

1. **Edit the active file first** (`~/.claude/commands/<skill>.md`).
2. **Apply changes to the repo `SKILL.md` surgically** — as conceptual units placed at
   heading anchors, **not** by regenerating/overwriting the whole file. The repo's
   `origin/main` is the curated truth (it may contain independently-added work). Take
   `origin/main` as the base and add only what is genuinely new.
   - German repo `SKILL.md` has **no** YAML frontmatter — it starts at `# Title`;
     `name`/`description` live in `.claude-plugin/plugin.json`.
   - English (`project-kickoff`, `project-review`): translate only the new sections and
     splice them into the existing curated EN body — never re-translate the whole file.
     Keep the established EN glossary (Polish Score, bird's-eye view, Money+Time+Emotion…).
3. **Bump the version** in all four `plugins/*/.claude-plugin/plugin.json` to the same new
   number (semver: feature = minor). Keep DE and EN of a skill on the same version.
4. Keep `.claude-plugin/marketplace.json`, `README.md` (DE, GitHub default) and
   `README.en.md` in sync if user-facing capabilities changed. `README.de.md` no longer
   exists — the German README is `README.md`.
5. **Never `git push --force`** on `main` (multi-session repo). Always create a
   `backup/...` branch before reset/rebase. In doubt: `git rebase --abort` → ask the maintainer.
6. **Pre-push sanity gate (mandatory):** `git diff origin/main --stat` must show only the
   intended change (e.g. the new feature lines + 4× plugin.json + README one-liners).
   If full-body changes appear, body noise leaked → stop and redo.
7. **Never commit** `*.bak-*` backup files (ignored via `.gitignore`).

## Three project levels (must stay in sync across all four skills)

`/projekt-starten` ↔ `/project-kickoff` create them, `/projekt-review` ↔ `/project-review`
review them. The typology must be identical in all four:

- **Small** — flat, numbered files
- **Large** — letter-prefixed root docs (A/B/C/F…) + numbered subfolders
- **Program** — umbrella level (own CLAUDE.md + A/B/C/F, `A` = *program description*)
  over multiple **subprojects**, each itself a complete large project

PM hierarchy: **Portfolio › Program › Project**.

## Languages

Every skill ships DE + EN. German `projekt-*`, English `project-*`. EN tracks DE — when
DE changes, splice the equivalent change into the curated EN (don't re-translate wholesale).
