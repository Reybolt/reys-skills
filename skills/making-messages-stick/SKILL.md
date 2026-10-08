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

## Rewrite workflow

Run these steps **in order** when handed a draft to improve. Don't jump to a polished version — naming the reader and diagnosing first are what make the rewrite land on the right idea.

1. **Name the one reader.** Who specifically will scan this — a named VP, the whole eng org, a customer? Ask if it's unclear; don't settle for "leadership." Every later step grades against *them*. (If the draft truly serves two different readers, that's usually two messages.)
2. **Find the core (Simple).** State in one sentence the single idea this reader must walk away with. If you have three, force the pick — say three things and you say nothing. Everything else is supporting detail.
3. **Diagnose the draft.** Grade it against the SUCCESs checklist below and name the 1–3 principles it fails — Simple and Concrete first, they fix most drafts. A few lines, not an essay. This is a diagnosis that *drives* the rewrite, not a justification written afterward.
4. **Produce 2–3 rewrites.** Give the user a real choice: vary the angle between candidates. Each leads with the outcome for the reader, not the activity (see Core pattern). Pull the specific lever for each failed principle:
   - **Concrete** → a real number or something they can picture. Never invent a number, example, quote, or anecdote. When the message cites a source (a book, talk, doc), use only examples you can verify are in it, and flag any you're unsure of so the author can confirm before sending. The strongest concrete detail comes from the reader's *own* daily reality (their tickets, their meetings, their codebase), not a famous-but-distant example — the closer it sounds to something they said last week, the harder it pulls.
   - **Emotional** → WIIFY ("what's in it for *you*"): state the reader's own stake. One person's win beats a percentage (identifiable-victim effect).
   - **Credible** → a claim the skeptic can test for themselves.
   - **Simple** → an analogy that borrows something the reader already understands.
   - **Unexpected** → pose the question the content answers; **do not answer it**. Naming the concept or term collapses the gap and removes the reason to engage. For reminders and teasers, the payoff lives in the room, not the message.
5. **Re-grade and deliver.** Pick the strongest candidate and apply the reader test against the named person: if they read only the first line, is the impact clear? Show **before → after**, name which principles it now passes, and flag any placeholder the user must fill with a real figure.

## The SUCCESs checklist

Grade the draft against each. Most weak comms fail on **Simple** and **Concrete** — fix those two first for the biggest lift.

| Principle | The question | Fix if it fails |
|---|---|---|
| **Simple** | Is there ONE core idea, up front? | Cut to the lede; say it first. |
| **Unexpected** | Is there a hook, or a curiosity gap? | Open with the tension/counterintuitive fact, not the summary. |
| **Concrete** | Can the reader *picture* or *measure* it? | Replace abstractions with sensory detail or a number. |
| **Credible** | Why should they believe it? | Add a stat, a testable claim, or an authority. |
| **Emotional** | Why should they *care*? | Name the stakes; appeal to identity/self-interest. One person, not a percentage. |
| **Stories** | Is there a concrete example carrying it? | Add a short scenario or before/after. |

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
- **Fixing all six at once.** Start with Simple + Concrete; they fix most drafts.
- **Rewriting before diagnosing.** Jumping straight to a polished version skips naming the reader and the core — you'll polish the wrong idea, then justify it after. Run the workflow steps in order.
