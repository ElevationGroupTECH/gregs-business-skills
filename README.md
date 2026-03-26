🇬🇧 English | [🇩🇪 Deutsch](README.de.md)

<p align="center">
  <img src="assets/claude-business-skills-hero.png" alt="Claude Business Skills" width="700">
</p>

# Claude Business Skills

**Most people use Claude like a fancy autocomplete. These skills turn it into a project manager.**

Ever started a new project and spent 20 minutes explaining context to Claude — only to do it all over again next session? Or opened a project folder after two weeks and had no idea where you left off?

You know the type. 47 files on the desktop. "Final_v3_FINAL_really-final.docx". A project folder that looks like a digital junk drawer.

Here's the thing: **Claude is only as good as the context you give it.** Give it a clean project setup with clear documentation, and it becomes a completely different tool. These skills do that in about 30 seconds.

---

## What's Inside

### `/project-kickoff` — Start Projects Right

Turn a chaotic brain dump into a properly structured project. You talk, Claude organizes:

- **Project description** with all the details that matter (goals, people, timeline, tech stack)
- **Changelog** with phases, milestones, task tracking, and log entries
- **CLAUDE.md** so Claude knows exactly what to read and how to behave in your project
- **Smart sizing** — small projects stay flat, large ones get letter-prefixed docs + numbered subfolders
- **Verification** — three targeted questions to make sure nothing was lost in translation

**How it works:** Run `/project-kickoff`, dump everything you know about your project (voice message style is fine — messy, unstructured, all over the place), and watch Claude turn it into a pristine project structure in under a minute.

> *Built from hundreds of hours of real project work with Claude. Not theory — this is how we actually work every day at [Teile Deine Botschaft](https://www.teiledeinebotschaft.de).*

### `/projekt-review` — Polish Check (Score Your Project)

Your project has been growing for weeks. Files everywhere. The changelog is three updates behind. The CLAUDE.md still mentions Phase 1 when you're deep in Phase 3.

This skill runs a comprehensive review and gives you a **Polish Score out of 10**:

| Category | What It Checks |
|---|---|
| 🏗️ **Structure** | CLAUDE.md, file naming, folder hierarchy |
| 📋 **Completeness** | Project description, tasks, milestones, changelog |
| 🔗 **Consistency** | Cross-references, URLs, phase names, status indicators |
| 🕐 **Currency** | Are statuses up to date? Is the changelog current? |
| 🧹 **Cleanliness** | Temp files, orphaned docs, overgrown files |

**What happens:**
1. Full assessment (reads everything, checks everything)
2. Automatic fixes (sort order, log index, file overview — the obvious stuff)
3. Decision table (things that need your input)
4. Recommended tasks with priority and score impact
5. Score forecast: "If you do all of this → 9.2 / 10"

**The score scale:**
```
0-1: 🤯  |  1-2: 🤬  |  2-3: 😱  |  3-4: 😫  |  4-5: 🥵
5-6: 🧐  |  6-7: 🤔  |  7-8: 😀  |  8-9: 🤩💪  |  9-10: 🏆🏆🏆
```

Hit 9+? You get a celebration. You've earned it.

---

## Better Together

These two skills are a pair — like inhaling and exhaling.

```
   /project-kickoff                    /project-review
   ┌──────────────┐                   ┌──────────────┐
   │  START RIGHT  │ ──→ Work ──→    │  STAY RIGHT   │
   │              │                   │              │
   │  Structure   │                   │  Score       │
   │  Description │                   │  Fix         │
   │  Changelog   │                   │  Polish      │
   │  CLAUDE.md   │                   │  Celebrate   │
   └──────────────┘                   └──────────────┘
          ↑                                  │
          └──────── Keep working ←───────────┘
```

**`/project-kickoff`** sets up a clean foundation. **`/project-review`** keeps it clean as the project grows. Without review, every project turns into a jungle. Without a good kickoff, there's nothing worth reviewing. Together, they form a cycle that keeps Claude effective across weeks and months of work.

Install both. Your future self will thank you.

---

## Installation

```bash
# Add the skill marketplace
/plugin marketplace add ElevationGroupTECH/claude-business-skills

# Install the skills you want
/plugin install project-kickoff     # English
/plugin install projekt-starten     # Deutsch

/plugin install project-review      # English
/plugin install projekt-review      # Deutsch
```

Then just run `/project-kickoff` or `/project-review` in any Claude Code session.

---

## Languages

Every skill is available in **English** and **German**:

| English | Deutsch | Description |
|---|---|---|
| `/project-kickoff` | `/projekt-starten` | Set up a new project with proper structure |
| `/project-review` | `/projekt-review` | Score and polish an existing project |

---

## Who Is This For?

- **Coaches & consultants** managing client projects, course launches, or event planning
- **Marketers** juggling campaigns, content calendars, and website projects
- **Solo entrepreneurs** who need structure but don't have a project manager
- **Anyone using Claude Code** who wants their AI to actually remember what's going on

If you've ever reopened a Claude conversation and spent 10 minutes re-explaining your project — these skills fix that. Permanently.

---

## The Philosophy

> Claude is only as good as the context you give it.

A well-structured project with a proper CLAUDE.md, versioned documents, and a current changelog isn't just "nice to have." It's the difference between Claude being a helpful team member and Claude being a confused intern who asks the same question for the fifth time.

These skills encode hundreds of hours of real-world project management with Claude into repeatable, one-command workflows.

---

## Examples

**Before `/project-kickoff`:**
```
my-project/
├── notes.txt
├── ideas.docx
├── final.docx
├── final_v2.docx
├── final_FINAL.docx
└── stuff/
```

**After `/project-kickoff`:**
```
my-project/
├── CLAUDE.md
├── 01-Project-Description-ClientPortal-V01.md
├── 02-Changelog-ClientPortal.md
└── xold/
```

**Before `/project-review`:** Score 3.2 / 10 😫
**After `/project-review`:** Score 9.1 / 10 🏆🏆🏆

---

## A Word of Honesty

These skills aren't magic. They won't fix a project that has no clear goal, and they won't replace thinking about what you're actually building. What they will do is remove the friction of setting up and maintaining the boring-but-essential project scaffolding — so you can focus on the work that matters.

They're the skills we use daily. Battle-tested, not perfect. And completely free.

---

## Contributing

Found a bug? Have an idea for a new skill? PRs and issues are welcome.

This repo is designed to grow — more business skills will be added over time.

---

## License

Apache 2.0 — use it, modify it, share it.

---

## About

Built by **[Teile Deine Botschaft](https://www.teiledeinebotschaft.de)** (TDB) — we help coaches, consultants, and solo entrepreneurs build their online business without needing to become tech experts.

These skills were born from running dozens of real projects with Claude Code. They're the foundation of how we work every day.

**Want to go deeper?**
- [Visit our website](https://www.teiledeinebotschaft.de) — Online business without tech headaches
- [Meet the team](https://www.teiledeinebotschaft.de/termin) — Book a free intro call
- [Read what our clients say](https://www.teiledeinebotschaft.de/kundenstimmen) — Real voices, real results

---

*Powered by Teile Deine Botschaft • Elevation Group G.N.D LTD*
