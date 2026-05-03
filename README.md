# ClaudeSkills

A growing collection of [Claude Code](https://claude.com/claude-code) skills you can drop into your own setup.

## What's a skill?

A skill is a folder with a `SKILL.md` file that teaches Claude how to handle a specific task — design, scaffolding, debugging, code review, anything procedural. The model auto-invokes it when its `description` matches what you're trying to do, or you can call it manually with `/skill-name`.

## Available skills

| Skill | What it does |
|---|---|
| [`app-icon-expert`](skills/app-icon-expert/SKILL.md) | Design app icons / favicons / logo marks the right way. Covers SVG construction, dark-mode handling, the modern multi-format favicon set, PWA manifest, iOS/Android rules, and a verification checklist. |

More to come.

## Install

Pick the scope you want and copy the skill folder into the matching path:

| Scope | Path | Effect |
|---|---|---|
| Personal (all your projects) | `~/.claude/skills/<name>/` | available everywhere on your machine |
| Project only | `.claude/skills/<name>/` | committed with the project, available to anyone who clones it |

Example:

```bash
git clone https://github.com/PianoNic/ClaudeSkills.git
cp -r ClaudeSkills/skills/app-icon-expert ~/.claude/skills/
```

Or for a project-scoped install:

```bash
mkdir -p .claude/skills
cp -r /path/to/ClaudeSkills/skills/app-icon-expert .claude/skills/
git add .claude/skills/app-icon-expert
```

After copying, restart Claude Code (or run `/reload-plugins` if you have it) so the skill is picked up.

## Verify it loaded

Inside Claude Code, type `/` and look for the skill name in the autocomplete list. You can also ask Claude "list available skills" — the loaded skill should appear.

## Contributing

PRs welcome. Each skill lives in its own folder under `skills/<kebab-case-name>/` with a `SKILL.md` as the entrypoint. Frontmatter must include at least:

```yaml
---
name: skill-name
description: Concrete description of when this skill should be used.
---
```

Keep `SKILL.md` under ~500 lines. Bundle longer reference material as separate files in the skill folder and reference them from `SKILL.md`.

## License

[MIT](LICENSE) — use it, fork it, ship it.
