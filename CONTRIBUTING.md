# Adding to this repository

## Adding a skill to an existing plugin

Create `plugins/<plugin>/skills/<skill-name>/SKILL.md`. The directory name is
the skill name and must be kebab-case.

```markdown
---
name: skill-name
description: One sentence saying WHEN to use this, not what it is. This is the
  only thing a model sees when deciding whether to load the skill, so write it
  as a trigger.
---

# Skill Name

Body.
```

`description` decides whether the skill is ever used. "Deploying the gitserver
server or runner to edge-01" is a trigger. "Deployment documentation" is not.

## Adding a new plugin family

1. `mkdir -p plugins/<family>/skills`
2. Write `plugins/<family>/.claude-plugin/plugin.json` and
   `plugins/<family>/.ulx-plugin/plugin.json` with `name`, `description` and
   `version` (the ulx one also has `"skills": "./skills"`).
3. Add an entry to `plugins` in both `.claude-plugin/marketplace.json` and
   `.ulx-plugin/marketplace.json` with `name`, `source: "./plugins/<family>"`
   and `description`. Keep the two files in step.
4. Add a row to the table in `README.md`.

Group by domain, not by author or by date. Someone installing `gitserver`
should not also receive writing skills.

## What makes a good skill here

**Write down the failure, not just the procedure.** A correct sequence of
commands is worth less than the sentence explaining why the obvious-looking
alternative silently does nothing. If you spent an hour on something, the hour
was the content.

**Say what success looks like.** "Six renamed tables and nothing new" is
checkable. "Verify the deploy worked" is not.

**Prefer a command that produces evidence over a claim.** Where a skill says
something is true, give the command that shows it.

**Keep it current.** A skill describing last quarter's layout is worse than no
skill, because it is believed. When you change the platform, change the skill in
the same commit.
