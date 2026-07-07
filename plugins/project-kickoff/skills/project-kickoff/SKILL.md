---
name: project-kickoff
description: Set up new projects properly — structure, description, changelog, CLAUDE.md. Just talk, Claude builds the rest.
---

# Project Kickoff

This skill sets up a new project cleanly — with project description, log file, CLAUDE.md, and a clean structure. Based on a proven methodology for cleanly setting up business projects with AI.

> **Part of a pair:** This skill starts projects clean. Its partner `/project-review` (alias `/review-project`) keeps them clean — with a polish score, automatic fixes, and honest feedback. Together they form a cycle: Start → Work → Review → Clean → Continue working.

---

## 🎯 Top Principle: Impact / Resources (binding for every project started here)

**Before anything is created — this decision principle is the compass for everything that follows in the skill. The skill works standalone — all necessary definitions are contained here.**

```
Value = Impact (effect on the business goal) ÷ Resources (Money + Time + Emotion)
```

### Three resource dimensions — consider for every task evaluation

1. **💰 Money** — licenses, tools, external service providers, purchases
2. **⏰ Time** — you, your team, maintenance, handover, learning curve
3. **💚 Emotion** — annoyance factor, frustration, energy. **Most often underestimated resource.** When work is annoying or a setup is fragile and complicated, that destroys more value than any money saving brings.

### Impact hierarchy

- 🚀 **Huge impact** (3-10× effect): include in plan, almost regardless of cost
- ⚡ **Medium + low-hanging fruit**: include if Claude can do it solo / automated
- 🐭 **Homeopathic** (<5%): drop, even if technically elegant

### Additional filters

- **Layperson test** (in software terms, the "least knowledgeable user" test): could someone with zero prior knowledge operate this in an emergency? → if no, reduce complexity.
- **Compound effects:** Some levers multiply (SEO × Content × Backlinks). Those first.
- **Opportunity costs:** What are we NOT doing if we do this?
- **Whole-system optimization:** Does this affect the system, or only a component that was already fine?
- **Who does the work?** You/your team = expensive. Claude = around the clock and cheap. Automated > one-off.

### Consequence for every newly created project

- Task tables include a column **"Effort"** (3-dimensional rating) + existing columns
- The CLAUDE.md of every project references the principle above (top filter section)
- Task prioritization: Huge-Impact > Compound-Effect > Low-Hanging-Fruit > Rest
- Recommendations are filtered through the CEO lens BEFORE being voiced: "What would a CEO think, not a nerd?"

---

## Process

### Phase 1: Determine project folder

1. **Ask for the project folder:**
   - Was a path given as an argument? → use it
   - Otherwise: "In which folder should the project live? Give me the path, or tell me where it belongs thematically (e.g. Marketing, Products, Customers), and I'll suggest a place in your company structure."
   - If the folder doesn't exist yet: create it (after confirmation)

2. **Switch to the project folder** and work there.

---

### Phase 2: Understand the project (briefing)

This is the most important step. The user will typically send a **voice message** — unstructured, jumping around, with tangents. That's normal and intended!

3. **Tell the user:**
   > "Tell me about the project! Just talk freely — wild and chaotic is totally fine. I'll sort it out for you. Tell me:
   > - What kind of project is this? (Book, congress, course, workshop, marketing campaign, software, ...)
   > - Who is it for? (Target audience)
   > - What is the goal?
   > - Who is involved? (Joint venture, team, customers...)
   > - Is there any prior work? (Positioning, concept, existing files...)
   > - Are there deadlines or a timeframe?
   > - Which tools/platforms will be used?
   >
   > If you already have files (positioning, concept, notes), just tell me where they are — I'll read them in."

4. **When the user answers:** Take everything in, even chaotic parts. DO NOT interrupt. Only when they're done, summarize structured.

5. **If the user references existing files** (e.g. a congress positioning, a concept paper): Read them in and use as basis.

6. **Optional: Handover protocol from a planning chat**

   Common case: User has already planned the project in a separate context window and brings a handover protocol (as pasted text or file). The handover protocol typically contains: context, what's already done, target state, next steps, files & references.

   When the user brings a handover protocol:
   - Read it completely and use as **primary information source**
   - Cross-check with project description (if any) — handover protocol takes precedence on conflicts
   - Identify missing info from the protocol and ask specifically
   - **Don't re-ask** what's already in the handover protocol!

7. **Optional: Pull in a Speak transcript as a source**

   Common case: The project starts from a voice recording in the Speak app ("Check my Speak app", "there's a recording from my run", "transcript from the call with X"). The user expects Claude to grab the transcript and use it as source material.

   When the user references a Speak transcript (or it's contextually obvious):
   - Use `mcp__speak__speak_list_transcripts` (optionally with `search` filter) to find the recording
   - Pull the full text via `mcp__speak__speak_get_transcript`
   - **Don't just reference — actually save it in `04-Sources/` (or appropriate subfolder) as a structured `.md` file:**
     - Naming: `YYYY-MM-DD-Speak-Transcript-[short-title].md`
     - Layout: frontmatter (ID, date, speakers), summary of key points, quotes block (for marketing), full-text reference
   - Identify speakers (the project owner is usually Speaker 1) and label them by name in the summary where derivable
   - Reference as source material in `A - Project Description` and `D - Methodology` (or matching docs)

   **Why save instead of just referencing?** Transcript IDs can change, the Speak app may be offline, and the project should explain itself even without Speak access. Copying once into the project stabilizes the source.

---

### Phase 3: Ask follow-up questions

7. **Ask clarifying questions** — only what's truly missing or unclear. Typical gaps:
   - Project title (if not named)
   - Target audience more precisely
   - People involved and their roles
   - Technical platform / tools
   - Budget or resources (only if relevant)
   - Access credentials (backend, frontend) — if it's a digital project

   **Don't ask too many questions at once!** Maximum 3-5 questions that are really needed.

8. **Ask about milestones:**
   > "Are there clear milestones or phases? A milestone is a measurable result that closes a phase — e.g. 'Manuscript done', 'Page live', 'Campaign launched'. If you have phases, we'll define a milestone for each."

   Milestones are shown with ◆ (diamond) and visualized in the log file:
   ```
   ◆ M1: Manuscript done                ✅ done
   │
   ◆ M2: Cover + layout approved        🔄 in progress
   │
   ◆ M3: Book published                 ⬜ open
   ```

9. **Determine project size / level:**
   Ask the user (or estimate yourself):
   > "Is this a small project, a large project — or a **program** (an overarching umbrella over several related subprojects)?"

   **Small** = workshop, single campaign, manageable scope, few files expected
   **Large** = book, congress, course with many modules, software — many files from different areas
   **Program** = several related projects that serve a shared goal and are coordinated together. Standard project-management hierarchy: **Portfolio › Program › Project** (PMI/IPMA). Examples: a series of case studies, a book series, several parallel client projects under one roof, a product area with multiple sub-products.

   When in doubt: **start small.** You can always add subfolders later — and a large project can later be **"pulled up" into a program** by laying a program level on top (existing projects become subprojects — do **not** restructure/rename, just add the umbrella).

---

### Phase 4: Create project structure

When enough info is in, create the following files:

#### Mandatory files (always):

##### Small project: numbered files

```
[Projectfolder]/
├── CLAUDE.md
├── 01-Project-Description-[NAME]-V01.md
├── 02-Log-[NAME].md
├── 03-[Other-File]-V01.md
├── ...
└── xold/
```

##### Large project: letter prefix for root documents + numbered subfolders

For large projects with thematic subfolders, numbered root files (01-, 02-) collide with numbered folders. So: **letter prefix** for root documents, numbers for subfolders.

```
[Projectfolder]/
├── CLAUDE.md
├── A - Project-Description-[NAME]-V01.md  ← Always read
├── B - Tasks-[NAME].md                    ← Always read (phases, tasks, milestones, specs)
├── C - Log-[NAME].md                      ← Read log index (logs as needed)
├── D - [Other-File].md                    ← e.g. sitemap, concept
├── E - [Other-File].md                    ← e.g. style guide
├── F - Decisions-[NAME].md                ← Decision log (optional, recommended)
├── 01-[thematic-folder]/                  ← e.g. positioning, manuscript
├── 02-[thematic-folder]/                  ← e.g. images, competition
├── ...
└── xold/
```

**Rule:** The letter files (A, B, C...) are the documents Claude reads at every session start. Numbers (01-, 02-...) are for subfolders.

**Workbench folder (mandatory for large projects):** Every large project also gets a numbered **workbench folder** — as the **last number** of the thematic folders (e.g. `07-Workbench` when 01–06 are taken). Purpose: the ONLY place for temporary things (test screenshots, snapshot dumps, throwaway scripts, intermediate results) — so the top project level stays clean (only project files + numbered folders live there). Rules (belong in the workbench as a `README.md`): ① nothing permanent here, ② put-back duty — whoever puts something down clears it away once the task is done, ③ never reference it from project files, ④ a workbench not emptied → empty it at the next `/project-review`. Difference from `xold/`: workbench = active work, emptied immediately; `xold/` = archive / trash antechamber. For **small projects** (flat) the workbench is optional — create it only when temporary artifacts are foreseeable.

##### Program: Umbrella Level + Complete Subprojects

A **program** is the umbrella over several related projects (PM hierarchy **Portfolio › Program › Project**). You can work **inside a subproject** (advancing one concrete project) **or in the program** (overarching concept, naming conventions, analysis, creating new subprojects).

```
[Program folder]/
├── CLAUDE.md                                   ← Program entry point (lists subprojects, points down)
├── A - Program-Description-[NAME]-V01.md       ← overarching concept (always read)
├── B - Tasks-[NAME].md                         ← program-wide tasks/milestones
├── C - Changelog-[NAME].md                     ← log index + logs
├── F - Decisions-[NAME].md                     ← decision log (recommended)
├── G - [overarching convention].md             ← optional, e.g. naming/standards
├── [NN-Subproject-1]/                          ← each a complete "large project"
│   ├── CLAUDE.md  +  A/B/C/F  +  thematic subfolders
├── [NN-Subproject-2]/
├── ...
└── xold/
```

**Program rules:**
- The program level has its **own** CLAUDE.md + A/B/C/F (same letter logic as a large project). Focus: the overarching layer — concept, naming conventions, output strategy, creating/managing subprojects. Here `A` is the **program description** (not a project description).
- Each **subproject** is internally a complete large project with its **own** CLAUDE.md + A/B/C/F + subfolders. The subproject CLAUDE.md points upward ("read program A first"); the program CLAUDE.md lists the subprojects.
- **When working in a subproject:** read the program `A` (concept) first, then the subproject CLAUDE.md/A/B.
- **Pulling up an existing large project:** do NOT restructure/rename (churn risk). Just lay the program umbrella on top; the existing project becomes a subproject.
- **Don't over-engineer:** only choose program when several related projects truly exist or are clearly foreseeable. A single project stays small/large.

---

#### a) Project Description (01 / A)

   Content:
   - Project title
   - Quick summary (What? For whom? Why?)
   - People involved (roles)
   - Project type (joint venture, own project, customer project...)
   - Target audience
   - Format / scope
   - Platform / technology
   - Timeline / deadlines
   - File structure (what's in the folder)
   - Access credentials (if known)
   - Next steps

#### b) Tasks & Log

For **small projects** everything is in one file (`02-Log`). For **large projects** it's split into two files:

##### Small project: one file (02-Log)

Contains everything: task tables, milestones, log index, logs.

```
# Log: [PROJECT-NAME]

> **Legend:**
> - 📄 = Page task (creating/editing a page)
> - ⚙️ = Code review / technical task
> - ◆ = Milestone
> No icon = general task

## Tasks by phases

### Phase 1 — [PHASE-NAME]

> Status: 🔄 In progress

| No | Task | Claude | Impact | Effort | Needs | Risk | Rollback | Status |
|---|---|---|---|---|---|---|---|---|
| [PRE]-01 | 📄 Create homepage | ✅ | 🔴 | 💰🟢 ⏰🟡 💚🟢 | — | 🟢 | — | ✅ Done |
| [PRE]-02 | Configure robots.txt | ✅ | 🟡 | 💰🟢 ⏰🟢 💚🟢 | — | 🟢 | Revert | ⬜ Open |
| [PRE]-03 | ⚙️ Code review Phase 1 | ✅ | 🟡 | 💰🟢 ⏰🟡 💚🟢 | Boss: sign-off | 🟢 | — | ⬜ Open |
| ◆ | **Milestone: [MEASURABLE RESULT]** | | | | | | | ⬜ Open |

## Milestones (overview)

◆ M1: [Description]      ✅ done
│
◆ M2: [Description]      🔄 in progress

## Log index (quick view)

| Log | Date | Description |
|-----|------|-------------|
| LOG-001 | [DATE] | Project start — setup, structure, CLAUDE.md |

## Log entries (newest first!)

### LOG-001 — [DATE] — Project start
- Project created and structured
```

##### Large project: two separate files (B + C)

For large projects, task descriptions and logs grow independently. Both in one file becomes unmanageable. So: **separate tasks and log.**

**`B - Tasks-[NAME].md`** — What's ahead? (Planning)

```
# Tasks — [PROJECT-NAME]

> Phases, tasks, milestones, and detail specs.
> For the change log (what was done?) → see `C - Log-[NAME].md`

## Tasks by phases

### Phase 1 — [PHASE-NAME]

> Status: 🔄 In progress

| No | Task | Claude | Impact | Effort | Needs | Risk | Rollback | Status |
|---|---|---|---|---|---|---|---|---|
| [PRE]-01 | 📄 Create homepage | ✅ | 🔴 | 💰🟢 ⏰🟡 💚🟢 | — | 🟢 | — | ✅ Done |
| [PRE]-02 | ⚙️ Complex component (→ see Task description) | ✅ | 🔴 | 💰🟢 ⏰🔴 💚🟡 | — | 🟡 | Revert | ⬜ Open |
| [PRE]-03 | ⚙️ Code review Phase 1 | ✅ | 🟡 | 💰🟢 ⏰🟡 💚🟢 | Boss: sign-off | 🟢 | — | ⬜ Open |
| ◆ | **Milestone: [MEASURABLE RESULT]** | | | | | | | ⬜ Open |

## Task descriptions

> Detail specs for complex tasks needing more than one row.
> Not every task needs this — only those where concept, architecture, or special requirements must be documented.

### [PRE]-02 — [Task title]

**What:** [description]
**Where:** [location]
**Technical architecture:** [details]
**Implementation steps:** [1, 2, 3...]

## Milestones (overview)

◆ M1: [Description]      ✅ done
│
◆ M2: [Description]      🔄 in progress
```

**`C - Log-[NAME].md`** — What was done? (History)

```
# Log — [PROJECT-NAME]

> Change log. What was done when?
> For tasks and planning → see `B - Tasks-[NAME].md`

## Log index (quick view)

> Newest first, oldest last.

| Log | Date | Description |
|-----|------|-------------|
| LOG-001 | [DATE] | Project start — setup, structure, CLAUDE.md |

---

## Log entries (newest first!)

### LOG-001 — [DATE] — Project start
- Project created and structured
- Project description created (V01)
- Task file created
- Log file created
- CLAUDE.md configured
```

##### Rules for both variants

   **Rating columns for tasks:**

   Every task table includes — besides No, Task, and Status — these rating columns:

   | Column | Meaning | Values |
   |--------|---------|--------|
   | Claude | Can Claude do the task solo? | ✅ = yes, solo \| ⚠️ = partial (needs input) \| ❌ = no (human needed) \| — = n/a |
   | Impact | How much does the task contribute to goal? | 🔴 high \| 🟡 medium \| 🟢 low |
   | Effort | 3-dimensional resource estimate | 💰[level] money / ⏰[level] time / 💚[level] emotion (each 🟢 low / 🟡 medium / 🔴 high) |
   | Needs | Who must deliver / review / approve? | Text (e.g. "Boss: review") or "—" if solo |
   | Risk | How high is breakage risk? | 🔴 high \| 🟡 medium \| 🟢 low |
   | Rollback | What to do if something fails? | Short text, or "—" if risk-free |

   These columns help the user decide: What can Claude do alone? What needs attention? Where must someone act?
   For milestone rows (◆) the rating columns stay empty.

   **Task numbers:** Each phase has a 3–5-letter prefix (e.g. LIVE, PROUD, GROW, INFRA, SCAN, DRILL, REACH).

   **Phase naming — IMPORTANT:**
   - **Phase headers** carry the **full English/German name first**, then prefix in parentheses.
     ✅ `### Phase 1 — Infrastructure (INFRA)`
     ❌ `### Phase 1 — INFRA (Infrastructure)`
   - **Tasks** carry only the prefix as number-prefix: `INFRA-01`, `INFRA-02`, `SCAN-01`, `DRILL-01`, `REACH-01`
   - The prefix can be **technically descriptive** (INFRA, SCAN, DRILL, REACH) OR **positively motivating** (LIVE, PROUD, GROW, START, GLOW) — whatever fits the project.
   - Avoid prefixes like ORDN, IMPL, PREP if they feel dry. Strategic/operational projects often work better with clear technical prefixes than forced-motivating ones.

   **Page tasks** (📄): When a task involves creating or editing a page/document.
   **Code review** (⚙️): After EVERY phase, plan a complete review as a task.
   **Perspective shift** (👁️): At project end ALWAYS, and for larger projects also at end of each phase, plan a perspective-shift task (see "Perspective shift check" below).

   **Sorting within a phase:** Tasks sorted by status:
   1. ✅ Done (top)
   2. 🔄 In progress / V1
   3. ⬜ Open
   4. ⚙️ Code review / review
   5. ◆ Milestone (always last row)

   **RULES for the log entries:**
   - **REVERSE CHRONOLOGICAL:** Newest log entries on TOP, oldest on BOTTOM
   - **Log numbers:** Format `LOG-XXX` (e.g. LOG-001, LOG-002). Easier to search and reference ("see LOG-005").
   - **Maintain log index:** After EVERY new log entry, also update the log index above
   - **Purpose of the index:** Claude can quickly check the index for which log is relevant, without reading all detail entries

#### c) Decision log (optional, recommended for larger projects)

For larger projects, create a decision log. Documents the **why** behind important decisions — so months later you can still trace why something is the way it is.

**Filename:** `03-Decisions-[NAME].md` (small) or `F - Decisions-[NAME].md` (large, after A/B/C/D/E)

```
# Decisions — [PROJECT-NAME]

> Documentation of all key decisions.
> Newest at top, oldest at bottom.

## Decision index

| No | Date | Decision |
|---|---|---|
| E-001 | [DATE] | [Short description] |

---

## Decisions (newest first)

### E-001 — [DATE] — [Title]

**Decision:** [What was decided?]
**Reason:** [Why?]
**Effect:** [What changes through this?]
```

**When to create?** When the setup phase already involves decisions (tech stack, structure, platform). Suggest to user: "Should I create a decision log? Helps when we look back later for why we chose X over Y."

#### d) CLAUDE.md (in the project folder)

   Content:
   - Project name and one-liner description
   - People involved
   - File overview (what's where)
   - **Rule: At every session start** read project description AND log
   - Brief summary and propose next 2-3 todos
   - After every completed step, immediately update log
   - After context-compact: re-read project description and log
   - **Files NEVER deleted**, move to `xold/` instead
   - **Keep file references current:** When a file gets a new version (e.g. V01 → V02), CLAUDE.md updates immediately so all paths/references point to the current version. Old version → `xold/`.
   - Relevant access credentials (if any)
   - **Project review rule:** Run a project review after every 10 completed tasks (see "Project review" below)

#### e) `xold/` — Trash folder (always create)

#### e2) `[NN]-Workbench/` — temporary work area (always create for large projects)

As the **last numbered folder** (next free number after the thematic folders) create a **workbench** — including a `README.md` with the 4 rules (nothing permanent · put-back duty: whoever puts something down clears it away · never reference it · a full workbench gets emptied at the `/project-review`). It is the ONLY allowed place for temporary things (test screenshots, dumps, throwaway scripts) — this keeps the top project level permanently clean. Workbench ≠ `xold/` (workbench = active session storage, emptied immediately; `xold/` = trash antechamber). For small (flat) projects it's optional.

#### Additional files as needed:

More files numbered consecutively (small: `03-...`, `04-...` / large: `C -`, `D -` etc.).
E.g. sitemap, style guide, methodology guide, participant list, marketing copy, schedule...

---

### Structuring: Small vs. Large vs. Program

#### Small project (flat structure)

All files directly in the project folder. No subfolders except `xold/`. Numeric numbering.

```
[Projectfolder]/
├── CLAUDE.md
├── 01-Project-Description-[NAME]-V01.md
├── 02-Log-[NAME].md
├── 03-[Other-File]-V01.md
├── 04-[Other-File].md
├── ...
└── xold/
```

**When small?** Workshop, single campaign, manageable scope. When fewer than ~15 files expected.

**Rule:** Expand only when needed. New topics = new numbered file. Only when an area has >5 files, consider a subfolder.

#### Large project (letters + subfolders)

Root documents with **letter prefix** (A, B, C...), subfolders with **numbers** (01-, 02-...). Tasks and log are **separated** (B = tasks/planning, C = log/history).

```
[Projectfolder]/
├── CLAUDE.md
├── A - Project-Description-[NAME]-V01.md
├── B - Tasks-[NAME].md                  ← Phases, tasks, milestones, specs
├── C - Log-[NAME].md                    ← Log index + logs
├── D - [e.g. sitemap / concept].md
├── E - [e.g. style guide].md
├── F - Decisions-[NAME].md
├── 01-[thematic-folder]/
├── 02-[thematic-folder]/
├── ...
└── xold/
```

**When large?** Book (manuscript, approvals, cover, marketing), congress (positioning, experts, images, tech), software (requirements, design, docs).

**Why letters?** Numbered root files (01-, 02-) collide visually with numbered subfolders (01-positioning/, 02-competition/). Letters make it instantly clear: "These are the main documents I always read."

**Typical subfolders by project type:**

| Project type | Subfolders |
|--------------|-----------|
| Online congress | 01-Positioning, 02-Images, 03-Experts, 04-Tech, 05-Marketing |
| Book | 01-Manuscript, 02-Approvals, 03-Cover, 04-Marketing |
| Online course | 01-Curriculum, 02-Videos, 03-Materials, 04-Tech |
| Marketing campaign | 01-Strategy, 02-Content, 03-Ads, 04-Analytics |
| Software / Website | 01-Requirements, 02-Design, 03-Documentation |

Suggest subfolders to the user and confirm. Don't over-engineer!

#### Program (umbrella level + subprojects)

Several related projects under one umbrella. The program level carries the **overarching** concept (its own CLAUDE.md + A/B/C/F, `A` = program description); each **subproject** is internally a complete large project. Full structure + rules → see Phase 4, "**Program: Umbrella Level + Complete Subprojects**".

```
[Program folder]/
├── CLAUDE.md  +  A/B/C/F (+ G)        ← program level (overarching)
├── [NN-Subproject-1]/  → own large project (CLAUDE.md + A/B/C/F + subfolders)
├── [NN-Subproject-2]/  → own large project
└── xold/
```

**When a program?** A series of similar projects (case-study series, book series, several client projects under one roof, a product area with sub-products) — when a shared concept/naming/output must be maintained across multiple projects.

**When NOT?** A single project — even a large one — stays small/large. Program only when a real plurality of related projects exists or is clearly foreseeable. Pull up an existing large project later if needed (umbrella on top, no rebuild).

---

### ⚠️ Leanness / Anti-clutter (mandatory — all project sizes)

Structure should be **flat and lean**. Deep folder trees cost exactly the findability the whole system exists for (layperson test: can you find the file in ≤ 2 clicks?). Especially important when **different AI assistants** work in one project — some like to create temporary intermediate files, dump folders, and deep folder chains ("clutter tails") that junk up the project root. That's precisely what the **workbench** is for (see above): temporary stuff belongs there, not in the root. Binding rules:

1. **A folder only pays off from ~5 files onward.** Below that → **keep it flat + a descriptive name prefix** (date/topic), no folder.
2. **Never one folder per single item.** Similar bulk files (transcripts, receipts, exports, daily videos) live **flat in ONE folder, date-/ID-prefixed, with a `000-INDEX` file** — **not** a subfolder per piece, and certainly no subfolder-in-subfolder.
3. **No empty or single-file wrapper folders** (`transcripts/` around one file, an empty `suggestions/`). A single file sits directly in the parent folder.
4. **Prefer broad over deep.** Every extra folder level must justify itself — when in doubt, one level fewer.
5. **For bulk imports (e.g. video transcripts):** file flat first + index; only introduce structure when a group really has > 5 files **and** its own project nature.

> This is the build-side counterpart of the review principle "No over-engineering" (`/project-review`).

---

### Optional patterns (when applicable)

Four recurring patterns that not every project needs — but appear often enough to be documented here. If one fits: include it. If not: skip.

#### Pattern A: Reference Project (when project builds on existing one)

Often a new project builds on an already running one — e.g. an operational migration project that derives from a technical engineering project. Or a marketing project referencing a predecessor congress.

**How to integrate:**

1. **In CLAUDE.md** add a section "Reference Data" or "Reference Project":
   ```
   ## Reference Data
   - **[Reference project name]:** `/path/to/reference-project/` — contains [what] and [what].
   - **Relevant files:** `[subpath]/xyz.md`
   ```

2. **In A - Project Description** add a section "Sources / Access Data" listing reference files from the other project.

3. **Question to ask the user:** "This project builds on `[other project]`. Should I copy important files directly into your new project (so they stay stable when the source project changes), or just reference them?"

4. **Mark copied files with date in name** (`2026-02-20-Domains-PHP7-list.txt`), so later it's clear which snapshot they're from.

**When not needed:** When the project is fully standalone, or the user explicitly says "fresh start".

#### Pattern B: Session template (for recurring work sessions)

Some projects consist of many similarly structured work sessions: migration days, recording days, interview sessions, production dates, campaign waves. Instead of starting from scratch each time, create a **session template**.

**How to integrate:**

1. In the thematically fitting subfolder (e.g. `04-Migration-Logs/`, `03-Recordings/`, `02-Production-Days/`) create a file `Template-[Session-Type].md`.

2. **Content of the template** (typical layout):
   ```
   # [Session-Type] — [DATE]

   **Created:** [DATE]
   **Owner:** [Person(s)]
   **Max capacity:** [number] (if relevant)

   ## Preparation (day before)
   - [ ] Checkpoint 1
   - [ ] Checkpoint 2

   ## Run
   | No | Customer/Item | ... | Status |
   |---|---|---|---|

   ## [Check] checklist (per item)
   - [ ] Point 1
   - [ ] Point 2

   ## After
   - [ ] Migration list updated
   - [ ] Log entry in C written

   ## Learnings / incidents
   [Leave empty, fill during session]
   ```

3. **In B - Tasks** add a task referencing the template: "Per session: copy template and run through."

4. **In CLAUDE.md** briefly mention this template is used for recurring sessions.

**When to include:** When 3+ similarly structured sessions are expected.
**When to skip:** One-off actions, or sessions too different to justify a template.

#### Pattern C: Meta-Procedure Document (for generalizable projects)

Sometimes a project isn't just a result — it's also a **blueprint for future, similar projects**. Typical cases:
- A freebie that should later be swapped to other topics (one freebie out of 5, then 10, then 20)
- A funnel system that can be applied to any topic (→ see Quiz-Funnel Factory)
- A production workflow the team will run multiple times
- A positioning procedure used for several products

In these cases, a **Meta-Procedure Document (Letter G)** pays off — it describes the generalizable framework in enough detail that the next project can be set up with a single command.

**How to integrate:**

1. **As an additional letter document after F:** create `G - Meta-Procedure-[NAME]-V01.md`.

2. **Content structure** (initial draft):
   - Why this document exists (which repetition is being avoided)
   - The framework at a glance (ASCII diagram or flow)
   - Per stage: input, steps, output, template (prompt), inspiration sources
   - "Application Examples" section — every new product following the framework gets added as an example

3. **In B - Tasks** add a dedicated phase **META** that runs in parallel to the other phases:
   ```
   ### Phase META — Document the meta procedure (continuous, parallel)
   | META-01 | Skeleton G - Meta-Procedure-V01 | ... |
   | META-02 | After Phase 1: generalize the steps | ... |
   | META-03 | After Phase 2: ... | ... |
   ◆ Milestone: G document is reusable
   ```

4. **Retrospective application:** If an existing project turns out to be a usable pattern in hindsight (e.g. Quiz-Funnel Factory), suggest a separate ticket to add a G document there.

**When to include:** When the user uses phrases like "we could do this more often," "it's a blueprint," "would be reusable," "as a template for other products," "generalizable."
**When to skip:** One-off projects with no replication intent.

#### Pattern D: Multi-Channel Project (4-6 distribution channels)

Many projects are **multi-channel products**: one core asset distributed across 4-6 different channels — e.g. a freebie as PDF, skill, ebook, video, funnel AND website. Typical cases:
- Freebies with multiple distribution paths
- Launches (PR, ads, newsletter, affiliate, social, event)
- Content series (blog, video, podcast, newsletter, social clips)
- Product releases with multiple sales channels

**How to integrate:**

1. **In the project folder, create a subfolder `03-Channels/`** (or project-fitting `03-Distribution/`).

2. **Per channel, a numbered sub-subfolder** in the user's preferred priority order:
   ```
   03-Channels/
   ├── 01-PDF-Freebie/          ← Priority 1
   ├── 02-Claude-Skill/          ← Priority 2
   ├── 03-Ebook-Book/            ← Priority 3
   ├── 04-Video-Miniseries/      ← Priority 4
   ├── 05-Funnel-Lead-Gen/       ← Priority 5
   └── 06-Website/               ← Priority 6
   ```

3. **In B - Tasks** add one phase per channel (phase shortcuts: PDF, SKILL, BOOK, VID, FUN, WEB, …). Each phase ends with a milestone (M3, M4, M5, …).

4. **In A - Project Description** add a "Format & Scope" section with **one block per channel** (cover, scope, price, distribution).

5. **Ask during setup:**
   - "Which channels do we want to play out?" (less than 3 usually doesn't justify multi-channel)
   - "What priority order?" (channel 1 gets produced first)
   - "Are there channels that can come later?" (don't do all at once)

6. **Terminology:** "Distribution channel" and "channel" are synonyms here. Use whichever word the user prefers internally to the project.

**When to include:** When the user names multiple output formats (e.g. "PDF and as a skill and maybe as a book").
**When to skip:** Single-channel projects (a book = just the book).

---

### Phase 5: Verification (three-question technique)

10. **Show the user the result:**
    - Briefly summarize what was created
    - List file structure

11. **Ask three questions:**
    > "So I'm sure I understood everything correctly, here are three questions:"
    >
    > [Three project-specific questions that show the project is correctly understood]

12. **Make improvement suggestions:**
    > "Is there anything else you should think about? Here are my suggestions: [...]"

13. **Closing:**
    > "The project is set up! You can come back to this folder anytime and continue working. I automatically read the CLAUDE.md and instantly know where we are."

---

## Perspective Shift Check (Post-Publishing / Goal Verification)

**Core idea:** Step out of the creator role. Take a completely different view. No longer "great what we made", but: **Would the target audience want this immediately?**

**When to plan?**
- **At project end:** ALWAYS. Mandatory task, not optional.
- **At end of each phase** (for larger projects): recommended, especially when the phase has externally visible results (page live, product launched, campaign started).

**How to name?** The name adapts to the project:
- Book → "Post-Publishing"
- Website → "Post-Launch"
- Course → "Post-Release"
- Campaign → "Post-Campaign"
- General → "Goal Verification" or "Quality Check"

**What's checked — the 5 perspective-shift questions:**

1. **Wow effect:** Is there a moment where the target audience thinks "This is genius! Who's behind this?" — If not, the special is missing. Good enough is not good enough.

2. **Want-to-have:** Is there an instant "I want this! I must have this!" Or rather "Interesting, I'll do it sometime"? The difference is everything.

3. **Emotions:** Does it touch? Excite? Spark curiosity? Or is it just correct and complete? Correct and complete anyone can do — emotional resonance not.

4. **Goal achievement:** Is the goal of this phase / project (as defined in the project description) actually achieved? Not "almost", not "in principle" — really achieved?

5. **Customer perspective:** Walk through the entire customer journey from the target audience's view. From first contact to desired action. Where do they stumble? Where do they lose interest? Where is info missing?

**How to add to the task list:**

```
| [PRE]-XX | 👁️ Perspective shift: [Project-specific name] | ✅ | 🔴 | 💰🟢 ⏰🟡 💚🟡 | Boss: review | 🟢 | — | ⬜ Open |
```

For larger projects as own mini-phase (example):

```
### Phase 1b — POST (Post-Publishing Quality Control)

> Methodology: Step out of the creator role. View from the outside like a customer.

| No | Task | Claude | Impact | Effort | Needs | Risk | Rollback | Status |
|---|---|---|---|---|---|---|---|---|
| POST-01 | 👁️ Walk through customer journey (view: [target audience]) | ✅ | 🔴 | 💰🟢 ⏰🟡 💚🟡 | Boss: review | 🟢 | — | ⬜ Open |
| POST-02 | 👁️ Wow-effect check: Is there an element that excites? | ✅ | 🔴 | 💰🟢 ⏰🟢 💚🟢 | Boss: review | 🟢 | — | ⬜ Open |
| POST-03 | 👁️ Check all links/CTAs | ✅ | 🟡 | 💰🟢 ⏰🟢 💚🟢 | — | 🟢 | — | ⬜ Open |
| POST-04 | 👁️ "Who is that?" check: sender clear? funnel logical? | ✅ | 🟡 | 💰🟢 ⏰🟢 💚🟢 | Boss: review | 🟢 | — | ⬜ Open |
| POST-05 | 🔧 Fix all findings | ✅ | 🔴 | 💰🟢 ⏰🟡 💚🟡 | — | 🟡 | Revert | ⬜ Open |
| ◆ | **Milestone: Goal verification passed — no customer stumbles** | | | | | | | ⬜ Open |
```

**Result:** Concrete findings + fixes. Not a report for the report's sake — actually make it better.

---

## Project Review (for larger projects)

**When?** After every **10 completed tasks**, run a full project review. The CLAUDE.md should contain this rule.

**What's checked:**

1. **Log up to date?** Are all status entries correct? Are all logs filed?
2. **Duplications?** Is information maintained in multiple places that could drift apart?
3. **Structure still fits?** Has the project evolved so that folders/files no longer fit? Need to move, merge, or split files?
4. **Documentation complete?** Is it clear where to find what? Are all decisions documented?
5. **Tidy?** Are there outdated files belonging in `xold/`? Stale locks, temp files?
6. **CLAUDE.md current?** Are paths, file overview, rules still correct?

**Result:** Log entry with finding + cleanup work as needed.

---

## Self-Improvement

**IMPORTANT:** After the skill has run and the project is set up, actively check:

> "Before we get going — I noticed a few things during setup that could improve the `/project-kickoff` skill:
> - [Concrete observations: What worked well? What was clunky? What was missing?]
> - [Suggestions for improvements or individualizations]
>
> Should I integrate these improvements into the skill?"

**Things to watch:**
- New project types the skill doesn't yet know (e.g. new subfolder suggestions)
- Steps that were superfluous or missing
- Questions the skill should have asked but didn't
- Structures that turned out impractical mid-project
- Patterns that were project-specific but are actually generally useful

**Also during project flow:** When in later chats it becomes clear that the project structure has weaknesses or the skill could've done something better → suggest updating the skill.

---

## Important rules

- **Start small:** When in doubt, flat structure. Add subfolders when needed.
- **Three levels:** Small (flat, numbers) → Large (letters + subfolders) → Program (umbrella level + complete subprojects). When in doubt pick the smaller level; pull up later without rebuilding what exists.
- **Versioning:** New version = new number (V01, V02, ...), never overwrite
- **Versioned files:** When a new version (e.g. V02) appears, the older version (V01) immediately moves to `xold/`. Only the current version stays in the main folder. Keeps it clean.
- **xold folder:** Move old here instead of deleting
- **Language:** German (default) or English (when project requires it — e.g. international team or customer-facing English content). Specify in CLAUDE.md per project.
- **Files for external delivery:** Always PDF, never DOCX
- **Voice-input typos:** User often uses voice input — domains, email addresses, technical terms always cross-check
- **Don't over-engineer:** Only create what's needed. Better start lean and expand as needed. → **Leanness / Anti-clutter** (own section): no folder under ~5 files, never one folder per single item, no empty wrappers, bulk files flat + `000-INDEX`, prefer broad over deep.
- **Workbench, not clutter:** For large projects, temporary files (test outputs, dumps, throwaway scripts) go ONLY into the `[NN]-Workbench/` folder — never into the project root. Empty it once done (put-back duty).
- **Register, don't island:** Enter every new project at the level above (structure table + changelog log) and check for number collisions BEFORE assigning — reserving placeholder notes count too.
