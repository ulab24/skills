# ulab24 skills

Skills for working inside ulab24. This repository is a plugin marketplace
for both Claude Code (`.claude-plugin/`) and ulx (`.ulx-plugin/`), and every skill is also a plain markdown file, so a harness that
does not understand plugins can read `plugins/*/skills/*/SKILL.md` directly.

The repository is public on GitHub.

## Install

In ulx:

```
/plugin marketplace add https://github.com/ulab24/skills.git
```

In Claude Code:

```
/plugin marketplace add https://github.com/ulab24/skills.git
```

Pin to a tag if you want a fixed version:

```
/plugin marketplace add https://github.com/ulab24/skills.git@v0.1.0
```

## What is here

No plugins are configured yet. Skills will be added to `plugins/<family>/skills/`
over time. See [CONTRIBUTING.md](CONTRIBUTING.md).

## Why these exist

Most of what is written down here is a failure that cost someone an afternoon.
The platform has a recurring shape: **things fail silently**. An unknown
environment variable is ignored rather than rejected. A fixture whose filename
no longer matches a table loads nothing and breaks a test somewhere else. A
lint target pointed at a deleted path passes because it ends in `|| true`. A
read-only registry account logs in successfully and is refused four steps later.

A skill here earns its place by naming the signal that distinguishes one of
those from the thing it looks like.
