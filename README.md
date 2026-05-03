# ClaudeSkills

A growing collection of [Claude Code](https://claude.com/claude-code) skills, distributed as a plugin marketplace.

## What's a skill?

A skill is a folder with a `SKILL.md` file that teaches Claude how to handle a specific task — design, scaffolding, debugging, code review, anything procedural. The model auto-invokes it when its `description` matches what you're trying to do, or you can call it manually with `/skill-name`.

## Available plugins

| Plugin | What it does |
|---|---|
| [`app-icon-expert`](plugins/app-icon-expert/skills/app-icon-expert/SKILL.md) | Design app icons / favicons / logo marks the right way. Covers SVG construction, dark-mode handling, the modern multi-format favicon set, PWA manifest, iOS/Android rules, and a verification checklist. |

More to come.

## Install (one-line)

Inside Claude Code:

```
/plugin marketplace add PianoNic/ClaudeSkills
/plugin install app-icon-expert@ClaudeSkills
```

Then `/reload-plugins` (or restart Claude Code) and the skill is live.

## Manual install (without the marketplace)

If you don't want to add the marketplace, copy a single skill folder into your skill directory:

| Scope | Path | Effect |
|---|---|---|
| Personal | `~/.claude/skills/<name>/` | available everywhere on your machine |
| Project | `.claude/skills/<name>/` | committed with the project |

```bash
git clone https://github.com/PianoNic/ClaudeSkills.git
cp -r ClaudeSkills/plugins/app-icon-expert/skills/app-icon-expert ~/.claude/skills/
```

## Verify it loaded

Inside Claude Code, type `/` and look for the skill name in the autocomplete list, or ask Claude "list available skills".

## Contributing

PRs welcome. Each plugin lives under `plugins/<kebab-case-name>/` with this layout:

```
plugins/<plugin-name>/
├── .claude-plugin/
│   └── plugin.json
└── skills/
    └── <skill-name>/
        └── SKILL.md
```

Then add an entry to `.claude-plugin/marketplace.json` so the plugin shows up in the catalog.

`SKILL.md` frontmatter must include at least:

```yaml
---
name: skill-name
description: Concrete description of when this skill should be used.
---
```

Keep `SKILL.md` under ~500 lines. Bundle longer reference material as separate files in the skill folder and reference them from `SKILL.md`.

## License

[MIT](LICENSE) — use it, fork it, ship it.
