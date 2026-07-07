---
name: text-subvocalization
description: >
  Optimizes all non-body-text elements for fast visual scanning: buttons, headlines,
  bullet points, labels, menu items, tabs, CTAs, subject lines, captions.
  Use this skill when the user writes or optimizes UI text, buttons, menus, lists, headlines,
  or any other visually arranged text. Also use for: "subvocalization lock",
  "button text", "shorten the headline", "optimize the label", "too long for a button",
  "unify the bullet list", "UI text", "CTA text", "subject line",
  "the texts look uneven", "doesn't fit on one line".
  Applied AUTOMATICALLY when the AI itself generates UI elements, buttons, lists, or
  headlines — no separate invocation needed.
---

# Subvocalization Lock

> Optimize visual texts (everything but body text) for fast pattern recognition.
> Developed in practice, validated with 26 quiz questions + all quiz-funnel elements.

## Why this matters

The brain processes **graphically arranged text** differently from body text. With body text, a person reads along internally (subvocalization) — slow, but deep. With visual elements like buttons and headlines, fast **pattern recognition** kicks in: the eye scans the first 1-2 words and "recognizes" the content.

Poorly structured text in such elements **breaks pattern recognition** — the brain drops back into slow subvocalization mode. That feels "sluggish" and kills the impact.

## Applies to

Headlines, bullet points, lists, buttons, captions, tabs, menu items, labels, slogans, subject lines, CTAs, infographic text — everything that is NOT body text.

**Does NOT apply to:** body text in paragraphs, chapters, email body (there linear reading is the intended mode).

---

## The 5 rules

### Rule 1: One line is king (70-80% importance)

Keep text in buttons, bullet points, and headlines so short that it fits on **one line**.

| Bad | Good |
|---|---|
| Solo entrepreneur | Solopreneur |
| Small team (2-5 people) | Small team |
| I work a lot, but it runs fine | Runs — a lot, but under control |

### Rule 2: Controlled line break

If one line isn't enough: set a **deliberate** line break, don't leave it to the layout.

- With centered text: both lines roughly equal, bottom one slightly longer (pyramid effect)
- Three lines only in exceptional cases

### Rule 3: Information-first (keyword up front)

The **key word** comes as the FIRST word. Intros are information killers — the eye only scans the first 1-2 words.

| Bad | Good | Why |
|---|---|---|
| How would you describe your workload? | Your workload? | "How would you" = zero info |
| Feels sluggish, even though it's not much | **Sluggish** — even though not much | "Sluggish" visible instantly |

**Bold formatting** on the keyword amplifies the effect. In a group of 4 answers, the eye then scans only: **Runs / Too much / At the limit / Sluggish**.

### Rule 4: Numbers as numbers (not as words)

ALWAYS write numbers as digits, NOT spelled out. The eye recognizes digits in <50 ms; words require subvocalization.

| Bad | Good |
|---|---|
| Three pillars of the time machine | 3 pillars of the time machine |
| Two hours, two topics | 2 hours · 2 topics |
| Rule of thumb — same prompt three times = one skill | Rule of thumb — same process 3x = 1 skill |
| Seven sessions | 7 sessions |

**Exception:** when the number is part of a fixed term that idiomatically must be spelled out (e.g. "one-on-one conversation" as a set phrase). In lists, bullets, headlines, buttons, though, **always** use the digit.

### Rule 5: Visual sameness among siblings

All elements of a group share the **same text structure**:
- Same number of lines
- Same formatting pattern (keyword bold → explanation normal)
- **Horizontal > Vertical**: elements side by side MUST be the same

| Bad (uneven) | Good (even) |
|---|---|
| ✅ Runs | ✅ **Runs** — under control |
| ❌ Lots of work, still can't keep up | ✅ **Too much** — can't keep up |
| ✅ At the limit | ✅ **At the limit** — no more room |
| ❌ Feels sluggish, even though it's not that much | ✅ **Sluggish** — even though not much |

---

## Process

### As standalone (`/subvocalization-lock`):
1. User gives texts (buttons, list, headlines, etc.)
2. Apply all 5 rules
3. Output the optimized version with an explanation per change
4. Show a before/after comparison

### Automatic (when the AI generates it itself):
Whenever the AI generates UI elements, buttons, lists, quiz questions, tab labels, menu items, CTAs, or headlines — apply all 5 rules automatically. No separate invocation, no follow-up question. Just get it right directly.

Applies especially to:
- Quiz questions and answer options
- Button texts and CTAs
- Navigation menus
- Email subject lines
- Bullet lists on sales pages
- Slide headlines
- Dashboard labels

---

## Quality check

- [ ] Does every element fit on one line?
- [ ] Is the keyword at the start?
- [ ] Are all numbers digits (not spelled out)?
- [ ] Are all sibling elements visually the same?
- [ ] No uncontrolled line breaks?

---

## 🔄 Self-improvement — after every run

This skill improves itself. **After every complete run**, pause briefly and reflect honestly:

- **What went well?** What was smooth and fast — what to keep exactly as is?
- **What went badly?** Where did you get stuck, what didn't work, where was there friction, error, or ambiguity?
- **Why?** What was the cause — missing info, an unclear step, a technical issue?
- **How to do it better next time?** What would you have needed to make it faster, cleaner, and error-free?

**Then act:**
- **Small, clear improvements** (typo, missing hint, sharper wording, a new edge case) → enter them into this skill yourself right away and note them in the changelog below.
- **Larger changes** (a different flow, new steps, structural rebuild) → propose them to the user and wait for approval before building them in.

That way the skill gets sharper with every use. Better one small improvement too many than one too few.

### Changelog

| Date | What was improved | Trigger |
|------|-------------------|---------|
| 2026-05-23 | New rule 4: numbers as numbers (not spelled out). Quality check extended. | Slides session 05: "two hours, two topics" → "2 hours · 2 topics". User feedback. |
