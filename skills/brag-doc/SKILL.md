---
name: brag-doc
description: Compile a weekly brag doc / impact log from a "completed items" Slack feed into a private Confluence page. Use on Fridays, or on-demand before a 1:1 / review / perf check-in. Reads the completed-items feed, reframes each item as an outcome/impact statement grouped by goal, sanitizes confidential people matters, updates the Confluence page, and DMs you the link.
---

# Brag Doc — Weekly Impact Log Generator

Turn a week of completed tasks into a dry, factual impact log on Confluence, grouped by goal.
The source of truth for *what was done* is your own `Conclusion` text on each completed item —
reframe it as an outcome; never invent impact that isn't there.

> **How it works.** Slack Lists aren't directly readable by Claude, so this skill assumes a
> Slack Workflow that posts one message per completed item into a DM/channel (the "feed"), plus
> a private Confluence page to publish into. Fill in the `Configure` block with your own values.

## Configure (fill these in)

- `FEED_CHANNEL` — Slack DM/channel id that receives one message per completed item (from your
  "item marked Done" Slack Workflow).
- `FEED_BOT_NAME` — the workflow/bot name that posts to the feed.
- `CONFLUENCE_PAGE_ID` — the private Confluence page to publish the log to.
- `CONFLUENCE_SPACE` — its space key.
- `CLOUD_ID` — your Atlassian site (e.g. `your-site.atlassian.net`).
- `YOUR_SLACK_USER_ID` — where to DM the summary (your own id).
- `GOAL_MAP` — a file (or files) listing your goals and which projects map to each. This skill
  uses a G1–G4 goal taxonomy as an example; replace with your own.

## Conventions

- **Feed** = `FEED_CHANNEL`, posted by `FEED_BOT_NAME`. Every message is one completed item.
  This is the ONLY input — the Slack List itself is not readable by Claude.
- **Goals key (example — replace with yours):** G1 · G2 · G3 · G4.
- **Register:** factual, dry, descriptive. No editorial adjectives ("great", "huge", "crucial"),
  no motivational framing. Outcome over activity.

## Message format in the feed

Each workflow message looks like this — parse the bullet fields:

```
✅ New Task Completion Details:
• Name: <task name>
• Project: <project name>
• Slack source: <permalink to where the work happened>   (may be absent)
• Conclusion: <your own one-line summary of what was done>
🔷 Slack List Item Details:
• Item ID: <RecXXXX>
• Item URL: <https://<workspace>.slack.com/lists/.../?record_id=RecXXXX>
```

`Conclusion` is the gold field. `Item URL` is the stable unique key for dedup.

## Steps

### Step 1 — Resolve the window
- Default (Friday run): the current week, **Monday 00:00 → now**, your timezone. Compute the
  Monday-00:00 Unix timestamp in Bash.
- On-demand run (before a 1:1 / review): window = since the date of the most recent
  `### Week of …` heading already on the Confluence page. If the page has no week yet, default
  to the last 7 days.

### Step 2 — Read the feed
- Read Slack channel `FEED_CHANNEL` with `oldest=<window start ts>`, `limit` 100.
- Keep only messages containing `New Task Completion Details`. Parse each into
  `{ name, project, slackSource, conclusion, itemId, itemUrl }`.
- If the feed is empty for the window: do not touch Confluence. DM yourself one line —
  "No completed items logged this week." — and stop.

### Step 3 — Dedup against the page
- Get Confluence page `CONFLUENCE_PAGE_ID` (contentFormat `markdown`).
- Collect every `Item URL` / `record_id=Rec…` already present. Drop any feed item whose
  `Item URL` is already logged. (Reruns on the same week must not duplicate.)

### Step 4 — Map each item to a goal
- For each item's `Project`, find the matching entry in `GOAL_MAP` and read its goal. Match on
  the project's short name/number. A project may map to more than one goal — use the first.
- No match, or a pure operational one-off → tag `[Admin]`.
- If a project maps but the goal is ambiguous, pick the single best fit and move on — do not
  stall on edge cases.

### Step 4.5 — Sanitize confidential people matters (MANDATORY)
Do this BEFORE reframing. **Treat the Impact Log as if it could leak** — even though the page
is private, no confidential people information may ever appear on it.

**Classify.** An item is a *confidential people matter* if its `Name` or `Conclusion` touches
any of:
- resignation, exit, offboarding, termination, someone leaving
- performance, underperformance, PIP, ratings, individual feedback
- compensation, salary, equity, pay, a promotion case
- health, medical, wellbeing, personal / family circumstances
- conduct, disciplinary, grievance, complaint, investigation
- the private contents of a 1:1

When unsure, treat it as confidential.

**Transform each confidential item:**
1. **Abstract the topic** to a neutral phrase — "people matters", "a management matter",
   "a people-leadership conversation". NEVER write the sensitive word (resignation, PIP,
   comp, …) or any specific drawn from `Conclusion`.
2. **Keep the first name** of the person involved — this preserves the signal that you led or
   partnered on it. First name only; never a surname or other identifier.
3. **Preserve the collaboration signal.** Catching up / partnering with your manager or
   supporting a report is legitimate brag value — keep *that* you did it, drop *what* it was
   about.
4. **Drop the source link AND Item URL** for confidential items — never link the sensitive
   thread. The line stands with no source.

Worked examples (generic — use real first names, never the sensitive topic):
- `Handling {name}'s resignation email` → "Addressing people matters with {name}" *(no link)*
- A private 1:1 with your manager about a report → "Partnered with {manager} on a people matter" *(no link)*
- `Performance review notes for {name}` → "Worked through a people-leadership matter with {name}" *(no link)*

Non-confidential items pass through unchanged (keep names, keep source links).

### Step 5 — Reframe each item as an outcome
Write ONE line per item. Lead with the result/change, not the activity. Draw on `Conclusion` +
`Name`; never fabricate impact beyond what `Conclusion` states. Append the source as a link —
`Slack source` if present, else `Item URL`. **Exception:** for confidential items sanitized in
Step 4.5, omit the `— [source]` suffix entirely.

- ✗ "Sent out message to the reading group."  (activity)
- ✓ "Ran the reading-group nudge and sharpened the message — [source]."  (outcome, dry)

### Step 6 — Compose the week section (markdown)
```
### Week of {Mon DD}–{Fri DD} {Mon} {YYYY}

**G1 — <goal name>**
- {outcome line} — [source]
- {outcome line} — [source]

**G4 — <goal name>**
- {outcome line} — [source]

**[Admin]**
- {outcome line} — [source]
```
Omit any goal group with no items. Order groups G1→G2→G3→G4→[Admin].

### Step 7 — Update Confluence
- **Weekly log:** prepend the new week section directly under the `## Weekly log` heading
  (newest week on top). Remove the `_(empty — …)_` placeholder on first real entry.
- **Highlights — quarter to date:** refresh the top block to the 5–8 biggest outcomes of the
  current quarter drawn from the whole log. "Biggest" = cross-business reach, named
  stakeholders, shipped customer impact, or team-level outcomes over routine admin. Replace the
  placeholder on first run.
- Update the page (markdown). Preserve the intro + Goals key + the `---` dividers.

### Step 8 — DM yourself the result
- Send a Slack DM to `YOUR_SLACK_USER_ID` (your own DM): the page link plus a 3-line summary —
  count of items logged this week, a per-goal tally, and anything that couldn't be mapped.
- This is the intended delivery; send it without asking.

## Guardrails
- **Confidentiality is mandatory (Step 4.5).** Treat the page as leakable. Never post the
  substance of resignations, performance, compensation, health, conduct, or private 1:1s.
  Abstract the topic, keep the first name + the collaboration signal, drop the source link.
  When unsure whether something is confidential, abstract it.
- **Read-only on Slack except the final self-DM.** Never post to channels or other people.
- **Confluence page stays private.** Never change its restrictions.
- **Never invent impact.** If an item's Conclusion is thin, log a thin line — do not inflate.
- **Dedup is mandatory** (Step 3) — the same Item URL must never appear twice.
- If a step errors (feed unreachable, goal map missing), note it in the DM and finish with what
  you have rather than aborting silently.
