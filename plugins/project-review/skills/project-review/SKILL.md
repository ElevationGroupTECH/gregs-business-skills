---
name: project-review
description: Project Review with Polish Score — honest assessment, automatic fixes, celebration at 9+. Bring your project back to a polished state.
---

# Project Review — Polish Check

This skill brings a grown project back to a polished state. Projects grow over time like a tree without pruning — files accumulate, structures erode, changelogs drift apart, clutter piles up. This review takes a bird's-eye view of the project, autonomously fixes what's obvious, and suggests everything else as concrete tasks.

> **Part of a pair:** This skill keeps projects polished. Its partner `/project-kickoff` sets them up clean — with structure, description, changelog, and CLAUDE.md. Together they form a cycle: Kickoff → Work → Review → Polish → Keep working.

The skill always refers to the project folder you're currently working in. The benchmark is the project structure from `/project-kickoff`.

---

## Phase 0: Orientation — Where Am I?

Before anything happens: **Make sure we're in the right project folder.**

1. **Check the current folder:**
   - Is there a `CLAUDE.md`? Are there project files (01-Project-Description... or A - Project-Description...)?
   - If yes → Project recognized, continue with Phase 1
   - If no → Ask: "Which project folder should I review? Give me the path or tell me which project you mean."

2. **If an argument was passed** (path): Use it.

3. **Identify project type:**
   - Numbered root files (01-, 02-...) → **Small project** (flat structure)
   - Letter prefix (A -, B -, C -...) + numbered folders → **Large project**
   - Neither → Note as a finding ("Project structure doesn't match any standard schema")

---

## Phase 1: Assessment — What Do We Have?

First build a complete picture, **before** changing anything.

### Layer 1: CLAUDE.md

Read and check the CLAUDE.md:

- **Does it exist?** If not → critical finding
- **Is it concise enough?** The CLAUDE.md gets loaded at every conversation start. It should be brief and precise — target: under 80 lines. Anything longer wastes context window.
- **Is the file overview accurate?** Are all actually existing project files listed? Are any missing? Are files mentioned that no longer exist?
- **Are the rules correct?** Do they reference the right files? Are paths correct?
- **Is there a project review rule?** (After 10 tasks → review)
- **Is there a Context Compact rule?** (After compact → re-read project description + changelog)
- **Is it current?** Does the description still match the actual project state?

### Layer 2: Project Files (Content)

Read all root documents (01/02/03... or A/B/C...) and check:

**Project Description (01 or A):**
- Is it complete? (Title, overview, people involved, target audience, timeline, file structure)
- Is it current? Does it still match the actual project progress?
- Are there contradictions with the actual state?

**Tasks/Changelog (02 or B+C):**
- Are task statuses current? (Does ✅/🔄/⬜ match reality?)
- Are tasks cleanly numbered? (Continuous numbering, no gaps, no duplicates)
- Is the sort order correct? (✅ top → 🔄 → ⬜ → ⚙️ → ◆ bottom)
- Are the phases still sensible? Or has a phase grown so large it should be split?
- Are the milestones still sensible and current?
- **Log Index:** Is it complete? Do the log numbers check out? Are all logs listed?
- **Changelog:** Chronologically correct (newest first)? Are all completed tasks logged?
- Are there log entries that are obviously missing? (e.g., files that exist but aren't logged anywhere)

**Decision Log (if present):**
- Is the index current?
- Are decisions documented with rationale?
- **Reality check:** For each decision, verify it still reflects the current state. Decisions document the moment they were made — but if things changed afterwards (e.g., a prefix was renamed, a phase restructured), the decision needs an addendum or should be marked as superseded. Otherwise Claude reads an old decision and acts on it, even though reality has long since moved on.

**Cross-Reference Check (systematic):**

This is one of the most common issues in grown projects: The same information lives in multiple places and drifts apart. Systematically check:

- **URLs:** If a URL appears in the sitemap AND in the task list, they must be identical. Every URL appearing in more than one file → verify consistency.
- **File names and paths:** Do references to files/folders in CLAUDE.md, project description, tasks → match the file system?
- **Phase names and prefixes:** Are the same names used everywhere — tasks, changelog, decision log, and CLAUDE.md?
- **Status indicators:** If the project description says "Phase 1a in progress" and the CLAUDE.md says the same — does that still match the task list?
- **People and roles:** Are team members named consistently everywhere?

For every contradiction: Identify the source of truth (usually the tasks file or the file system) and note all other locations as findings.

---

### Layer 3: Impact / Resources Clarity (standalone strategic check)

> **Why standalone?** Polish hygiene (structure, completeness, consistency, currency, cleanliness) says: "The project is well-maintained." It does **not** say: "The project is working on the right things."
>
> A project can be at 100% polish and still fail at homeopathic micro-optimizations while the massive levers sit untouched. This dimension is therefore **scored separately** — as 0-2 points on top of the Polish Score, because it's a **strategic question**, not a hygiene question.

**The principle in brief (for Claude instances without TDB context):**
> **Value = Impact ÷ Resources (Money + Time + Emotion)**
>
> Three resource dimensions, not two. Emotion (mental drag, energy, security) is the most underestimated resource.
> - 🚀 Massive impact (3-10×): include in plan
> - ⚡ Medium + low-hanging fruit: include if AI/Claude can do it solo / automated
> - 🐭 Homeopathic (<5%): drop, even if technically elegant

**What's checked here concretely:**

1. **Are tasks prioritized by impact?**
   - Does the task list have an **Impact column** (🚀 / ⚡ / 🐭 or similar)?
   - Are massive-impact tasks in early phases, homeopathic ones in late phases or not at all?
   - Or is it just whatever's easy that gets done, instead of what works?

2. **Are resources estimated across three dimensions?**
   - Does the task list have an **Effort column** with Money + Time + Emotion (€/⏰/💚 or similar)?
   - Is Emotion explicitly named as a resource? (nerve factor, maintenance frustration, complexity stress)
   - Or is everything calculated only in hours — as if the other two dimensions didn't exist?

3. **Are hype arguments identified and called out?**
   - Are there decision-log entries of the kind "rejected because it solved no concrete problem"?
   - Or are tasks accepted just because they're "industry standard" / "cool" / "you should"?
   - Watch for indicators in changelog and decisions: "solves no concrete problem", "wife test", "compound", "opportunity costs"

4. **Is "don't implement" a visible option?**
   - Are there tasks with status "rejected" or "consciously not done"?
   - Or only "open", "in progress", "done"? (That would be suspicious — means: nobody is saying no.)

5. **Are compound effects recognized?**
   - Are tasks that mutually reinforce each other (e.g., SEO × Content × Backlinks for a website) recognizable as a connected leverage phase?
   - Or scattered isolated across the list, as if they were independent?

6. **Who's doing the work?**
   - Is it clear which tasks Claude can do autonomously, which need input, and which the human must decide?
   - (e.g., "Who" column or "Claude" column with ✅/⚠️/❌)
   - Things Claude can do solo should be **preferred**, because human time is expensive.

**Scoring (max 2.0 points):**

| Score | Meaning |
|---|---|
| **2.0 / 2.0** 🎯 | Tasks prioritized by impact, effort across 3 dimensions, anti-pattern awareness in the decision log, "don't implement" visible. Massive levers first. |
| **1.5 / 2.0** 👍 | Impact recognized and mostly accounted for. One dimension missing (often: Emotion is not named). |
| **1.0 / 2.0** ⚠️ | Tasks mixed — some by impact, some by convenience. Principle not explicitly anchored. |
| **0.5 / 2.0** 🚨 | Task list is a to-do wall without prioritization. Whatever's easy gets done. |
| **0 / 2.0** 🐭 | Pure tool/feature collection without impact awareness. Optimization trap active. |

**Findings in this category are especially important.** They show whether the project is strategically healthy — not just tidy. A Polish Score without an Impact Score is like a well-kept garden with no harvest.

**Other Project Files:**
- Are they still relevant? Or outdated?
- Are there content duplications between files?
- Are there contradictions between files?
- Are file names descriptive and correctly versioned (V01, V02...)?

### Layer 3: Folders and File Structure

- **List all folders** and briefly look inside (file list, don't read contents)
- **Check xold/:**
  - Are there files in it that clearly have nothing to do with the project anymore?
  - Are there files identical to current versions (true duplicates)?
  - Are there extremely large files just wasting space?
  - DON'T delete based on age alone! A project can sit idle for months — age alone means nothing.
- **Orphaned files:** Are there files in the project folder that aren't referenced in any project file and serve no recognizable purpose?
- **Temporary files:** `.tmp`, `.bak`, lock files, `node_modules` that don't belong, etc.
- **Does the folder structure fit the project?** Are thematic folders still sensible, or has the project evolved in a different direction?
- **Overgrown files:** Are there individual files that have grown disproportionately large (>300 lines) and should be split?

---

## Phase 2: Immediate Fixes — What's Obvious?

After the assessment: Fix everything that's clearly wrong and can be corrected risk-free, **do it yourself right away.** This includes things like:

- **Fix sort order:** Tasks in the right sequence (✅ → 🔄 → ⬜ → ⚙️ → ◆)
- **Complete log index:** Add missing entries to the log index
- **Update CLAUDE.md file overview:** Add missing files, remove non-existent ones
- **Close numbering gaps:** Fix task numbering
- **Fix obvious typos** in project files
- **Remove temporary files** (.tmp, .bak, lock files)
- **Move empty or useless files** to xold/
- **Fix chronology:** Put changelog in the right order (newest first)

**DON'T do yourself** (suggest only):
- Rename files that are referenced elsewhere (could break references)
- Restructure the project (from flat to subfolders or vice versa)
- Merge or split phases
- Rewrite or shorten content (except CLAUDE.md if obviously too long)
- Delete files from xold/ (always suggest with rationale)
- Split the project

---

## Phase 3: Review Summary

Output the review report directly in chat. Structure:

```
## Project Review: [PROJECT NAME]
📅 Date: [DATE]
📂 Folder: [PATH]
🔍 Type: [Small/Large]

### Polish Score: [X.X] / 10  [EMOJI]

| Category | Score | Details |
|---|---|---|
| 🏗️ **Structure** | [X.X] / 2.0 | [1 sentence — what's good/bad] |
| 📋 **Completeness** | [X.X] / 2.0 | [1 sentence — what's good/bad] |
| 🔗 **Consistency** | [X.X] / 2.0 | [1 sentence — what's good/bad] |
| 🕐 **Currency** | [X.X] / 2.0 | [1 sentence — what's good/bad] |
| 🧹 **Cleanliness** | [X.X] / 2.0 | [1 sentence — what's good/bad] |
| | **[X.X] / 10** | |

### Impact Score: [X.X] / 2.0  [EMOJI]

> **Strategic add-on dimension** — scored separately, because hygiene and impact are two different questions.
> Polish-100% says: "well-maintained". Impact Score says: "working on the right things".

| Aspect | Rating |
|---|---|
| 🎯 Tasks prioritized by impact? | [✅/⚠️/❌] [Note] |
| 💰⏰💚 Effort estimated across 3 dimensions? | [✅/⚠️/❌] [Note] |
| 🚫 Anti-patterns identified (no hype)? | [✅/⚠️/❌] [Note] |
| ❌ "Don't implement" visible as an option? | [✅/⚠️/❌] [Note] |
| 🔗 Compound effects recognized and bundled? | [✅/⚠️/❌] [Note] |
| 👤 "Who does the work?" clarity? | [✅/⚠️/❌] [Note] |

**Impact Summary** (1-2 sentences): [Strategic assessment — are we working on the right things, or polishing grains of sand?]

**The 5 Categories in Detail:**

**🏗️ Structure** (max 2.0) — The skeleton: Does the right form exist?
- CLAUDE.md present, concise enough (<80 lines), rules correct?
- Project type recognizable (letters/numbers)? Files named correctly?
- Folder hierarchy sensible? xold/ present?
- File overview in CLAUDE.md matches the file system?

**📋 Completeness** (max 2.0) — The substance: Is all the content there?
- Project description complete (title, people involved, tech, timeline)?
- Tasks with phases, milestones, numbering?
- Changelog with log index and log entries?
- Decision log present (for large projects)?
- Are files or content obviously missing?

**🔗 Consistency** (max 2.0) — The logic: Does nothing contradict itself?
- URLs in sitemap = URLs in task list?
- Phase names and prefixes the same everywhere?
- File references in CLAUDE.md match the file system?
- Decisions reflect the current state?
- People, roles, status indicators identical everywhere?

**🕐 Currency** (max 2.0) — The freshness: Is everything up to date?
- Task statuses match reality?
- Changelog documents all completed work?
- Dates in documents are current?
- Tasks correctly sorted (✅ → 🔄 → ⬜ → ⚙️ → ◆)?
- CLAUDE.md describes the current phase?

**🧹 Cleanliness** (max 2.0) — The hygiene: Is there clutter lying around?
- xold/ tidy? No massive, useless files?
- No temporary artifacts (.tmp, .bak, logs, .DS_Store)?
- No orphaned files without reference?
- No overgrown monster files (>300 lines)?
- No AI artifacts (ChatGPT citations, debug leftovers)?

**Overall Scale:**
- 0–1: 🤯  |  1–2: 🤬  |  2–3: 😱  |  3–4: 😫  |  4–5: 🥵
- 5–6: 🧐  |  6–7: 🤔  |  7–8: 😀  |  8–9: 🤩💪  |  9–10: 🏆🏆🏆

> [REVIEW SUMMARY — 1-3 sentences, honest and direct]

The review summary is the heart of the assessment. It appears right below the score and should nail in 1-3 sentences how the project is doing. The rule: DON'T BE DIPLOMATIC. Say it like it is — honest, human, with character. The assessment should sting when things are bad and should dazzle when things are good.

Orientation by score range (examples, DON'T copy verbatim — find your own words!):

**0–2:** "Total disaster." / "This isn't a project, it's a folder with files in it." / "Everything is missing here. Literally everything." / "Phew... where do you even start?" / "What on earth happened here?"

**2–4:** "Oh dear." / "Let's be honest here: this is a proper mess." / "Basic structure is there — but that's where it ends." / "A bit more effort wouldn't have killed anyone." / "Consistently tried hard — as they'd write on a school report card."

**4–6:** "Functional, but you can feel the neglect." / "This can be better — and you know it too." / "Solid foundation, but there's dust growing on top." / "Halftime: You can work with it, but it's no fun."

**6–7:** "Pretty decent already, structure clearly visible." / "You can tell someone's been thinking around here." / "A few quirks, but rock-solid underneath."

**7–8:** "There's a lot of really nice stuff in here!" / "Claude feels at home here — and you can tell by the quality of its work." / "Well maintained, just a few growing pains."

**8–9:** "Impressive. This is what a project looks like when someone takes it seriously." / "Top 5% — this is a treat for an AI." / "Almost polished to perfection. Almost."

**9–10:** "Just wow." / "Top 1%. A dream of a project structure." / "Nothing to do here. Outstanding." / "If every project looked like this..."

IMPORTANT: These examples are just inspiration. The summary should be specific to the project — what's concretely good or bad. Don't waffle in generalities — name names.

### ✅ What's Good
- [Points that are in order — important for context!]

### 🔧 Fixed Immediately
- [What was automatically repaired, with brief rationale]

### ❓ Decisions Needed

Some findings I can't resolve on my own — I need a decision here. Each open topic is presented clearly so it can be decided quickly:

| Nr | Topic | Option A | Option B | Recommendation |
|---|---|---|---|---|
| 1 | [Short description] | [Option A + what changes] | [Option B + what changes] | [Which option and why] |

For each decision:
- **What's the problem?** (1 sentence — what contradicts itself or is unclear)
- **Which files are affected?** (so it's clear what changes)
- **What do I recommend?** (always give a clear recommendation, don't just throw options out there)
- **What happens if we do nothing?** (consequence of non-decision)

After each decision is made: Implement immediately and log it in the decision log.

### 📋 Recommended Tasks — The Path to 10/10
[Numbered list of concrete tasks that DON'T need a decision — I can do these right away. Prioritized, with score impact:]

| Nr | Task | Priority | Score Impact | Rationale |
|---|---|---|---|---|
| 1 | ... | 🔴 High | +0.5 | ... |
| 2 | ... | 🟡 Medium | +0.3 | ... |
| 3 | ... | 🟢 Low | +0.1 | ... |

> **Forecast:** If all tasks completed + all decisions made → [new score] / 10 [EMOJI]

### 💡 Strategic Considerations
- [Split the project? Redefine phases? Restructure?]
- [Things learned that should be captured]
- [Direction for the next phase]
```

**Priorities:**
- 🔴 **High:** Directly impairs work (e.g., CLAUDE.md missing, changelog outdated, contradictions)
- 🟡 **Medium:** Should be done soon (e.g., clean up xold, remove duplications, rethink phases)
- 🟢 **Low:** Nice-to-have (e.g., add decision log retroactively, standardize file names)

---

## Phase 4: Next Steps

After the summary:

1. **Ask if tasks should be executed:**
   > "Those are the things I found. Want me to tackle the tasks now? Or do you want to discuss specific ones first?"

2. **If approved:** Work through tasks in order. For bigger interventions (restructuring, project splits), check back before proceeding.

3. **Update changelog:** At the end, write a log entry:
   ```
   ### LOG-XXX — [DATE] — Project Review (Polish)
   - Review completed: [count] findings, [X] fixed immediately
   - Immediately fixed: [list]
   - Recommended tasks: [list or reference to review output]
   - Polish Score: [before] → [after]
   ```

4. **If all tasks are done → Recalculate score and celebrate the polish achievement!**

   Recalculate the score. If it's now at 9+:

   ```
   ---

   ## 🏆🏆🏆 POLISH ACHIEVED!

   **Score: [X.X] / 10** (before: [old score])

   [HERE COMES THE CELEBRATION — see below]

   This project is now ready for the next 100 tasks.
   Have fun working on it! 🚀
   ```

   The celebration should be funny, vivid, and motivating. Be creative! Here are some directions as inspiration (DON'T copy, invent your own variations!):

   - **Scent metaphors:** "This project smells like a fresh spring breeze and freshly cut grass now. Before, it smelled more like... let's just say: a shared apartment kitchen on a Sunday morning."
   - **Hotel metaphors:** "Welcome back to the 5-star project hotel. The towels are folded, the pillows are fluffed, and there's a little chocolate sitting on the changelog."
   - **Dentist metaphors:** "This is what a project feels like after a professional cleaning. Everything sparkles, everything shines, and you think: Why didn't I do this three months ago?"
   - **Car wash metaphors:** "Fresh out of the car wash. Paint polished, interior vacuumed, that little pine tree air freshener dangling from the CLAUDE.md's rearview mirror."
   - **Mise en place:** "Mise en place. Everything in its place, the knives sharpened, the ingredients prepped. Now we can cook."
   - **Marie Kondo:** "Marie Kondo would be proud. Every file sparks joy. The xold folder breathes a sigh of relief."
   - **AI perspective:** "If I had a heart, it would be beating faster right now. This project is like a tidy living room with a fireplace, a cup of tea, and a good book. I WANT to work here."

   IMPORTANT: Always project-specific! Reference concrete things that were cleaned up. "The book URL now points to /books/ everywhere instead of three different paths" is better than "Everything is tidy."

   If the score stays under 9, still celebrate the progress:
   > "From [old score] to [new score] — that's a noticeable difference! [Name 1-2 concrete improvements]. For a full 10 we'd still need [what], but the project is significantly more workable now."

---

## Key Principles

- **Bird's-eye view, not ant's-eye view:** Don't dive into code or execution files. Only check the project framework (CLAUDE.md, project files, structure).
- **Understand first, act second:** Read everything completely before changing anything.
- **Conservative with deletions:** Rather move to xold/ one too many times than delete one too many times. When actually deleting (cleaning up xold), always suggest — never do it yourself.
- **The goal is polish:** After the review, the project should feel like it was freshly set up — Claude enjoys working in it, everything is in its place, nothing contradictory, nothing overdue.
- **No over-engineering:** Don't unnecessarily add files or structures. The project should stay lean, not get bloated.
