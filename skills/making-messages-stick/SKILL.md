---
name: making-messages-stick
description: Use when writing or reviewing a title, headline, project name, announcement, update, doc, or any comms — especially leadership-facing or widely-shared — and it reads abstract, buries the point, names the activity instead of the outcome, or the impact isn't clear at a glance.
---

# Making Messages Stick

## Overview

Sharpen any message using the *Made to Stick* framework (Heath & Heath). Sticky ideas are **SUCCESs**: Simple, Unexpected, Concrete, Credible, Emotional, Stories. The enemy underneath all six is the **Curse of Knowledge** — once you know something, you can't imagine not knowing it, so you write in abstractions the reader can't picture.

**Core move:** name the *outcome for the reader*, not the *activity you're doing*. "Architectural uplift" is your work; "faster, lighter, tablet-ready" is their win.

## When to Use

- A title/headline/project name reads abstract ("uplift", "modernize", "optimization workstream", "enhancement").
- A message buries the point — reader must dig to learn why it matters.
- Comms is leadership-facing or widely shared, where it'll be scanned, not read.
- You're the expert writing for non-experts (Curse of Knowledge risk is highest here).
- The message is *about* writing/communication/the very principle in play — apply that principle to the message itself, so the medium becomes the proof.

Don't force it on internal shorthand between people who share full context.

## Workflow

Run these steps **in order** when handed a draft to improve. The scorecard comes *before* any rewrite: diagnose first, let the writer choose what matters, then rewrite only what they picked. Don't jump to a polished version — naming the reader and scoring first are what make the rewrite land on the right idea.

1. **Gather the message.** Collect three things: the draft itself, the *one* reader who will scan it (a named VP, the whole eng org, a customer — ask if unclear; don't settle for "leadership"), and the single idea that reader must walk away with (the core). If you have three candidate takeaways, force the pick — say three things and you say nothing. If the draft truly serves two different readers, that's usually two messages.
2. **Score it — the scorecard.** Grade all six SUCCESs principles against the named reader, using the scorecard format below. Every principle gets a score, a verdict, and a one-line reason. Mark a principle **N/A** when a message of this length or type doesn't owe it — a one-line status update isn't failing by carrying no Story. This is a diagnosis that *drives* the rewrite, not a justification written afterward.
3. **Recommend priorities.** From the scorecard, name the 1–3 principles that would most lift *this* message, each with its lever (see levers below). Simple and Concrete first — they fix most drafts. Say plainly: a short message rarely needs all six, so the goal is to pick what's load-bearing, not to chase a perfect score.
4. **Writer picks.** STOP and let the writer choose which principles to address. Present the recommendation, then wait — don't auto-rewrite everything. The scorecard informs; the writer decides what's worth the effort for this message.
5. **Produce scoped rewrites.** For the principles the writer picked, produce 2–3 rewrites — a real choice, varying the angle between candidates. Each leads with the outcome for the reader, not the activity (see Core pattern), and pulls only the chosen levers. Then re-grade the picked principles, apply the reader test against the named person (if they read only the first line, is the impact clear?), show **before → after**, and flag any placeholder the writer must fill with a real figure.

### The levers

Pull the matching lever for each principle the writer chose to address:

- **Concrete** → a real number or something they can picture. Never invent a number, example, quote, or anecdote. When the message cites a source (a book, talk, doc), use only examples you can verify are in it, and flag any you're unsure of so the author can confirm before sending. The strongest concrete detail comes from the reader's *own* daily reality (their tickets, their meetings, their codebase), not a famous-but-distant example — the closer it sounds to something they said last week, the harder it pulls.
- **Emotional** → WIIFY ("what's in it for *you*"): state the reader's own stake. One person's win beats a percentage (identifiable-victim effect).
- **Credible** → a claim the skeptic can test for themselves.
- **Simple** → an analogy that borrows something the reader already understands.
- **Unexpected** → pose the question the content answers; **do not answer it**. Naming the concept or term collapses the gap and removes the reason to engage. For reminders and teasers, the payoff lives in the room, not the message.

## The scorecard

Grade all six principles against the named reader. Each gets a **score /5**, a **verdict**, and a one-line reason. The question in the middle column is what you're scoring against.

**Scoring:** 5 = Strong, 3–4 = Partial, 0–2 = Missing. Mark **N/A** (no score) when a message of this length or type doesn't owe the principle — a one-line title isn't obliged to carry a Story. Exclude N/A rows from the total, shown as e.g. `13/20`. The total is a read on where the message stands, not a target to maximise — a short message that nails Simple + Concrete and marks the rest N/A is done.

| Principle | The question | Score | Verdict | Why |
|---|---|---|---|---|
| **Simple** | Is there ONE core idea, up front? | _/5 | | |
| **Unexpected** | Is there a hook, or a curiosity gap? | _/5 | | |
| **Concrete** | Can the reader *picture* or *measure* it? | _/5 | | |
| **Credible** | Why should they believe it? | _/5 | | |
| **Emotional** | Why should they *care*? | _/5 | | |
| **Stories** | Is there a concrete example carrying it? | _/5 | | |

Most weak comms fall down on **Simple** and **Concrete** — weight those two first when recommending priorities, they fix most drafts.

## The reader test

Before sending, ask: **if [the specific person who matters] reads only the title/first line, is the impact clear without opening the rest?** Name the actual audience (a VP, a customer, the whole eng org). Grade against *them*, not a generic reader.

## Core pattern: outcome over activity

The single highest-leverage swap. Delete the abstraction naming your process; lead with what gets faster, lighter, safer, or newly possible. Keep the mechanism (the tech, the refactor) in the description.

```
✗ "iOS Assets Architectural Uplift"        (names the refactor — invisible)
✓ "Rebuild iOS Assets: faster, lighter, tablet-ready"  (names the win)

✗ "Backend Latency Optimization Workstream"
✓ "Cut checkout API from 800ms to 200ms"

✗ "Improve onboarding experience"
✓ "Get new users to first inspection in under 5 minutes"
```

## Common mistakes

- **Abstraction as the headline.** "uplift/modernize/optimize/enhance" — none can be pictured. The Curse of Knowledge in one word.
- **Mechanism in the title.** "in SwiftUI", "using Kafka" — that's the how; lead with the what-for.
- **A number that isn't there.** Don't invent one; but if a real metric exists (size, latency, crash rate), it carries the whole line (Concrete + Credible at once).
- **Inventing evidence.** Same rule as numbers, extended to examples, quotes, and anecdotes — especially when citing a source. Use only what you can verify; flag anything unsure so the author confirms before sending.
- **Closing the gap you just opened.** Explaining the answer in the same breath as the hook. A curiosity gap only pulls while it's unresolved — name the payoff and the reason to engage evaporates.
- **Grading against yourself.** It's clear to you because you have the context. Grade against the reader who doesn't.
- **Chasing all six.** Not every message owes every principle — a short status line or a reminder legitimately marks several N/A. Pick what's load-bearing (Simple + Concrete first); don't treat the scorecard total as a number to maximise.
- **Rewriting before scoring.** Jumping straight to a polished version skips naming the reader, the core, and the scorecard — you'll polish the wrong idea, then justify it after. Run the workflow steps in order, and let the writer pick priorities before you rewrite.
