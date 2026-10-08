# reys-skills

A collection of [Claude Code](https://claude.com/claude-code) skills.

## What is a skill?

A skill is a reusable reference guide that teaches an agent a proven technique or
workflow. Each one lives in its own folder under `skills/` as a `SKILL.md` file
with YAML frontmatter. Claude Code reads the `description` to decide when a skill
is relevant, then loads the body on demand — so skills extend what the agent can
do without bloating every conversation.

## Skills

| Skill | Use it when |
|---|---|
| [making-messages-stick](skills/making-messages-stick/) | Writing or reviewing a title, headline, announcement, or doc that reads abstract, buries the point, or names the activity instead of the outcome. Diagnoses drafts against the *Made to Stick* (Heath & Heath) SUCCESs framework. |
| [brag-doc](skills/brag-doc/) | Compiling a weekly brag doc / impact log from a "completed items" Slack feed into a private Confluence page — on Fridays, or before a 1:1, review, or perf check-in. Reframes each completed item as an outcome grouped by goal, and sanitizes confidential people matters. |

## Install

### As a plugin (recommended)

Install the whole collection through the Claude Code plugin marketplace — new
skills arrive automatically when you update:

```
/plugin marketplace add Reybolt/reys-skills
/plugin install reys-skills
```

### Manual copy

Or copy a single skill folder into your personal skills directory:

```bash
cp -R skills/making-messages-stick ~/.claude/skills/
```

Either way the skill becomes available via the `Skill` tool in Claude Code.

## Authoring a new skill

Each skill is a folder under `skills/` containing a `SKILL.md`:

```
skills/
  your-skill-name/
    SKILL.md
```

The `SKILL.md` starts with YAML frontmatter and follows a consistent structure:

```markdown
---
name: your-skill-name
description: Use when <specific triggering conditions and symptoms>.
---

# Your Skill Name

## Overview        — what it is + the core principle in 1–2 sentences
## When to Use     — concrete symptoms and situations; when NOT to use
## <Process>       — the steps, pattern, or checklist the agent follows
## Common mistakes — what goes wrong, and the fix
```

Conventions:

- **`name`** uses lowercase letters, numbers, and hyphens only, and matches the
  folder name.
- **`description`** is written in the third person, starts with "Use when…", and
  describes *only the triggering conditions* — not the skill's workflow. This is
  what the agent matches against, so lead with the symptoms someone would have.
- Keep it reusable and concise. A skill is a reference guide, not a story about
  one time you solved a problem.

## License

[MIT](LICENSE)
