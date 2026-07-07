---
name: text-impact-filter
description: >
  Analyzes any text for emotional IMPACT — sentence by sentence, with a 5-level color scale.
  Use this skill when the user wants to improve, tighten, or "get a text to the point".
  Also use for: "impact filter", "polish text", "rate the sentences", "what doesn't land here",
  "too long", "boring", "tighten the text", "make it more emotional", "every sentence has to hit",
  "cut the filler", "improve storytelling", "optimize the script", "improve ad copy",
  "shorten the newsletter", "tighten the landing-page copy".
  Works with any text: storytelling scripts, sales pages, newsletters, ads, book chapters,
  blog posts, video scripts, speeches, presentations.
---

# Impact Filter

> Rate every sentence for emotional IMPACT. Cut the weak, polish up the rest.
> Developed in practice — inspired by attachment-energy psychology.

## The core principle

Impact and content are two different things. A sentence can be flawless in content and still have zero impact. Another sentence says almost nothing — but you feel it instantly.

**When in doubt: impact > content.**

This is not proofreading. Not a grammar check. Not "does this sound good?". The impact filter asks a single question: **Does this sentence create a feeling?**

---

## Process

The impact filter runs ALL the way through — no interim questions, no "should I?". Input in → output out.

**What comes out (in this order):**
1. HTML file 1: Color-coded analysis (to view)
2. HTML file 2: Polished version with markup (to view)
3. **THE FINISHED TEXT** — polished, level 4-5 only, copy-paste-ready (this is the main result!)

### Step 1: Analysis

Go through the text **sentence by sentence** (for long sentences: clause by clause) and rate each on the 5-level scale:

| Level | CSS class | Color | Name | What it means |
|-------|-----------|-------|------|-----------------|
| 5 | `w5` | Dark green (#14532d on #dcfce7) | **Hammer** | Creates a feeling instantly. You stop. You feel it. |
| 4 | `w4` | Light green (#365314 on #ecfccb) | **Strong** | Carries the story emotionally. Good tension. |
| 3 | `w3` | Orange (#78350f on #fff7ed) | **Medium** | Okay, but interchangeable. Neither strong nor weak. |
| 2 | `w2` | Red (#9a3412 on #fff1f2) | **Weak** | Flat, generic, explanatory. No emotion. |
| 1 | `w1` | Struck through (#7f1d1d on #fee2e2) | **Cut** | Filler, redundancy, a list with no feeling. |

### What makes a sentence high-impact?

Watch for these **indicators of strong impact** (level 4-5):
- **Specificity**: Time of day, place, weather, sensory detail ("Wednesday night, freeway, rain on the windshield")
- **Rhythm break**: A short, punchy sentence after a long passage
- **Show don't tell**: A concrete scene instead of an explanation
- **Contrast & surprise**: Break the expectation
- **Vulnerability**: Raw honesty that hurts
- **Rule of three**: "Don't correct. Don't control. Don't rework."
- **Rhetorical questions**: "But how are you going to pay for that?"
- **The stopper**: A sentence you HAVE to pause on

And these **indicators of weak impact** (level 1-2):
- Generic, abstract statements with no image
- Explanatory filler sentences ("That's because...")
- Lists with no emotional charge
- Redundancy: making the same point again in other words
- Hedging: "And for generic tasks it works fine too"
- Rational bridges: "Then a door opened. For the first time I understood..."
- Too many abstract nouns in one sentence ("the info, the commitment, the involvement")

### Step 2: Output the HTML analysis

Create an HTML file with the color-coded analysis. Use this template:

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Impact Filter — [TITLE]</title>
<style>
  body { font-family: 'Inter', system-ui, sans-serif; max-width: 800px; margin: 40px auto; padding: 20px; background: #faf8f5; color: #3c3c3b; line-height: 1.8; font-size: 17px; }
  h1 { color: #91133B; font-size: 24px; }
  .subtitle { color: #888; font-size: 14px; margin-bottom: 30px; }
  .legend { display: flex; gap: 20px; margin-bottom: 30px; padding: 15px; background: white; border-radius: 12px; flex-wrap: wrap; border: 1px solid #eee; }
  .legend-item { display: flex; align-items: center; gap: 6px; font-size: 13px; }
  .dot { width: 14px; height: 14px; border-radius: 50%; flex-shrink: 0; }
  .w5 { color: #14532d; background: #dcfce7; padding: 1px 3px; border-radius: 3px; font-weight: 600; }
  .w4 { color: #365314; background: #ecfccb; padding: 1px 3px; border-radius: 3px; }
  .w3 { color: #78350f; background: #fff7ed; padding: 1px 3px; border-radius: 3px; }
  .w2 { color: #9a3412; background: #fff1f2; padding: 1px 3px; border-radius: 3px; }
  .w1 { color: #7f1d1d; background: #fee2e2; padding: 1px 3px; border-radius: 3px; text-decoration: line-through; }
  p { margin: 16px 0; }
  .note { font-size: 12px; color: #888; font-style: italic; margin-left: 6px; }
  .stats { background: white; padding: 20px; border-radius: 12px; margin-top: 40px; border: 1px solid #eee; }
  .stats table { width: 100%; border-collapse: collapse; }
  .stats td, .stats th { padding: 8px 12px; text-align: left; border-bottom: 1px solid #f0f0f0; font-size: 14px; }
  .bar { height: 16px; border-radius: 8px; display: inline-block; }
</style>
</head>
<body>
<h1>Impact Filter — [TITLE]</h1>
<div class="subtitle">[SUBTITLE]</div>
<!-- Legend and sentences here -->
<!-- At the end: stats table with distribution -->
</body>
</html>
```

Each sentence/clause is wrapped in a `<span class="wN">`. For weak spots, add a `.note` with a short rationale (why doesn't it land?).

At the end of the HTML: a stats table with the count per level and a bar chart.

### Step 3: Polish (automatic, DON'T ask!)

Right after the analysis — without any follow-up question — create the polished version.

Create a second HTML file with three sections:
1. **Marked-up version**: Black = keep (4-5), Blue = rewritten, Gray struck through = removed
2. **Before/after table**: Words, estimated duration, level-1-2 spots
3. **Plain text**: The polished version without markup

### Polish rules:
- Level 5: **DON'T TOUCH** — that's gold
- Level 4: Keep
- Level 3: Keep only if needed for sense/context. Otherwise: polish up or cut
- Level 2: Cut. If the sense breaks → rewrite completely at level 4-5
- Level 1: Out immediately

When polishing up: don't just reword — rebuild the sentence so it creates a FEELING. Make it more specific, shorter, more surprising, more vulnerable.

### Step 4: Deliver the finished text + close out

This is the MAIN RESULT. Output the finished, polished text as plain text in the chat — no HTML, no markup, just the finished text ready to copy.

Plus a short summary:
- Words before → after (with percentage)
- Spots cut / rewritten
- Highlight the 3 strongest hammer sentences

### Step 5: At the end, just ONE question

After the finished text:

> "All impact-optimized! Want to see, save, or delete the color-coded impact analysis and the polished version?"

Options:
- **See:** Open the HTML files in the browser
- **Save:** Store the HTML files in the project folder (under `04-Assets/` or similar)
- **Delete:** Discard the HTML files — the finished text is already there

---

## Three modes of use

The impact filter is deployed differently depending on WHO wrote the text:

### Mode 1: Standalone (`/impact-filter`)
When the user explicitly invokes `/impact-filter` or hands over an existing text to optimize.
- Run all the way through (steps 1-5)
- End with the ONE question (see/save/delete)

### Mode 2: Automatic (AI-generated texts)
When the AI ITSELF generated a text — newsletter, ad copy, social-media posts, sales-page copy, email sequences, funnel copy — then attach the impact filter AUTOMATICALLY. No asking, no separate invocation needed.
- Run steps 1-4 silently in the background
- Output ONLY the finished, impact-optimized text
- Do NOT create HTML files (saves time)
- Short note: "Impact filter applied: X words → Y words (-Z%)"

Applies to all skills/contexts where the AI produces text:
- Writing newsletters
- Generating ad copy
- Sales-page copy
- Email sequences
- Social-media posts
- Funnel copy (storytelling, quiz, diagnosis)

### Mode 3: Book chapter (a step of its own)
For books and long storytelling texts, the impact filter is a SEPARATE step in the workflow — not automatic.
- First let the text get written completely
- Then explicitly ask: "Should I run the impact filter over it?"
- On "yes": full analysis with HTML files (steps 1-5)
- Gather feedback: "Is this good? Better? What's missing?"
- Iterate until it lands

Why separate for books? Because book chapters are longer, carry more context, and the author wants to review the impact rating themselves before anything gets cut.

---

## Examples of impact

**Level 5 (Hammer) — sentences that STOP you:**
- "The only thing I could rely on was me."
- "Now I was the errand girl for everything."
- "Finally, no more idiots."
- "They won't. Not like this. Not alone."
- "I didn't even know what I was looking for."
- "It felt like I'd been kept busy."

**Level 1 (Cut) — sentences that DO nothing:**
- "I'd already optimized everywhere — time-management courses, prioritization tools."
- "Maybe you could be even more efficient, maybe you could work even more."
- "And for truly generic tasks you can handle cleanly, it works fine too."

---

## Saving files (if wanted)

- Analysis: `[folder]/impact-analysis-[name].html`
- Polished version: `[folder]/impact-analysis-[name]-polished.html`

If no folder is given: in the current project folder under `04-Assets/` or the nearest sensible location.

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
| — | (no entries yet) | — |
