---
name: kudos
description: Use when writing an Engineering Kudos nomination or any monthly peer/team recognition — recognising a person or team for a recent achievement and needing a short, specific, outcome-led paragraph grounded in verifiable evidence rather than vague praise.
---

# Kudos

## Overview

A kudos nomination recognises a person or team who **exceeded expectations last
month**. A weak one names the *activity* ("the team worked hard on the project")
— abstract, unverifiable, forgettable. A strong one leads with the **outcome**,
backs every claim with a **sourced specific**, and gives each person their
**name next to what they actually did**.

**Core principle:** recognise the outcome, prove it with evidence, and never
invent a fact to make it sound better. A number you can't source weakens the
nomination — it doesn't strengthen it.

**REQUIRED SUB-SKILL:** Use `making-messages-stick` for the prose itself — it
provides the Simple / Concrete / Credible levers and the "outcome over activity"
move this skill depends on.

## When to Use

- Writing an Engineering Kudos (or similar monthly recognition) nomination.
- Recognising a team or individual for a shipped milestone, launch, or rescue.
- You have a rough sense of "they did something great" but need the specifics,
  the names, and the outcome stated so it lands with a reviewer who wasn't there.

Not for: performance reviews, promo cases, or anything that weighs trade-offs —
kudos is pure recognition of a single recent win.

## The guidelines (hard constraints)

These come from the Engineering Kudos brief. Treat them as non-negotiable:

- **One paragraph.** Short is the goal. A larger team justifies a few more
  sentences, but never more than a paragraph.
- **Specific examples + outcomes.** Say what shipped and what changed because of
  it — not just that effort happened.
- **Use names, not "you" / "your".** Write in the third person about the people.
- **Capitalise team and product names** (e.g. Asset Hierarchy, the Assets team).
- **Recognise those who exceeded expectations** — the bar is "beyond the normal
  job", not "did their job".

## Workflow

Run in order. Steps 2–5 are evidence-gathering; do not start writing until they
are done, or you will pad with abstractions.

1. **Pin the window and the reader.** "Last month" relative to today. The reader
   is a review panel who does **not** know the internals — grade every sentence
   against them.
2. **Resolve the nominees.** Get the exact list of people from the requester or a
   team roster (e.g. a team channel's membership). Confirm it explicitly.
   Exclude people who left or did not contribute; add anyone named who sits
   outside the obvious list. A wrong or missing name undermines the whole thing.
3. **Pull the achievement from an authoritative source** — not memory. In order
   of preference: the delivery tracker (e.g. a Jira epic + its child issues),
   a launch / readiness doc (Confluence), and the launch announcement (Slack).
   Capture: what shipped, the **exact milestone** (Early Access vs Beta vs GA —
   do not blur these), dates, scope, why it was hard, and any real outcome
   metrics.
4. **Attribute one concrete contribution per person**, sourced (Jira assignee,
   PR author, the launch post). One vivid specific each beats a generic list.
5. **Verify — never invent.** Numbers, quotes, and examples go in only if you can
   source them. No metric? Say so and let scope carry the nomination. Don't claim
   GA if it's Early Access. Mark gaps for the requester instead of filling them.
6. **Guard privacy.** Keep customer names, account data, and any sensitive detail
   out of the nomination. If the destination is public or widely shared, strip
   internal specifics (ticket numbers, codenames) too.
7. **Write it.** Apply `making-messages-stick`: open with the outcome (what is now
   possible / faster / safer), make the scope concrete, keep claims testable, and
   put each name beside its contribution. Produce the one-paragraph nomination.
   For a large team, offer two cuts: a **full-team** version (everyone named) and
   a tighter **lead-contributors** version.

## Output format

A single paragraph. Structure that reliably works:

1. **Lead with the outcome + milestone** — what shipped, to whom, and why it
   mattered (one sentence a reviewer grasps instantly).
2. **The "exceeded expectations" hook** — the hard part: scope, a long-deferred
   ask, a tight timeline, a rescue, cross-team or cross-platform reach.
3. **Named contributions** — each person + one concrete, sourced thing they did.
4. **Close on the bar** — one line naming why this is beyond-the-job.

## Common mistakes

| Mistake | Fix |
|---|---|
| Names the activity ("worked on X") | Lead with the outcome X made possible |
| Invents a metric to sound impressive | Source it or drop it; scope can carry it |
| Claims "GA" when it was Early Access / Beta | State the exact milestone |
| "Great job to the team" with no names | Name each person + what they did |
| One generic list of everyone | One vivid specific per person |
| Lowercase product/team names | Capitalise them |
| Leaks a customer name or sensitive detail | Strip it; "named Enterprise customers" |
| Three ideas competing for the lede | Force one core idea to the front |

## Worked example (fictional — illustrates structure only)

> Last month, the Billing team shipped Usage-Based Billing to Early Access for
> Enterprise customers — a capability deferred for two planning cycles as too
> risky to touch — and delivered it in under four months across the web app and
> the public API. Customers can now meter, cap, and invoice on real usage instead
> of flat seats. Sam Rivera owned the metering pipeline and the backfill that
> re-priced every existing account without a billing gap; Jordan Lee built the
> invoice-preview and overage UI; Priya Nair rebuilt the rating engine to stay
> correct under concurrent usage spikes; and Marco Bianchi wired up the alerting
> that let the rollout be watched live. Replacing the core of how the company
> charges, with zero disrupted invoices, is exactly what exceeding expectations
> looks like.

The names, team, and product here are invented — swap in your own sourced facts.
Never copy a real nomination containing colleagues' names into a shared or public
location (see step 6).
