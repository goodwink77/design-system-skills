---
name: design-system-skills
description: A personal learning and testing space for Agent Skills that teach AI agents to build UI with a design system.
metadata:
  author: Kyle Goodwin
  status: experimental
  category: design-systems
---

# Design System Skills

> [!NOTE]
> **This is a learning and testing space.** The skills here are experiments, drafts, and works in progress. Expect them to change, break, and get rewritten as I learn. Nothing here is production-ready, and this is a personal project, not affiliated with or endorsed by my employer.

This repo is where I practice writing [Agent Skills](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview) for design systems, and where I practice Git and GitHub in public while I do it. Each skill teaches an AI agent one design-system discipline, such as color or typography, so it builds UI the way a design systems team would.

## What Is a Skill

A skill is a folder with a `SKILL.md` file that gives an agent instructions for a specific kind of task. It can also hold reference files and scripts the agent uses when it needs them.

Skills load in layers, so they don't fill up the agent's context:

1. **Frontmatter:** the `name` and `description`, always loaded. The description tells the agent *when* to use the skill.
2. **SKILL.md body:** loaded only when the skill is relevant.
3. **Bundled files:** references and scripts, read only when a step needs them.

## Skills in This Repo

| Skill | What it does | Status |
| --- | --- | --- |
| [meta-skill-template](skills/meta-skill-template/) | A starting template for authoring new design system skills with a consistent structure | 🧪 Testing |
| [visual-color](skills/visual-color/) | Applies color token guidance to components and flows, including states and contrast | 🧪 Testing |
| [visual-typography](skills/visual-typography/) | Applies type scale, weight, line height, and text color tokens, with redline-style annotation tables | 🧪 Testing |

**Status key:** 📝 Draft (being written) · 🧪 Testing (being tried on real prompts) · ✅ Stable (works reliably in my tests)

## Repo Layout

```
design-system-skills/
├── README.md
├── CONVENTIONS.md          # how skills in this repo are structured (coming soon)
├── skills/
│   ├── meta-skill-template/
│   │   └── SKILL.md
│   ├── visual-color/
│   │   └── SKILL.md
│   └── visual-typography/
│       └── SKILL.md
└── notes/                  # learning notes and test results
```

## How I'm Testing

I test each skill before calling it stable:

1. **Trigger test:** Does the agent pick the skill up from a natural request, without my naming it?
2. **Output test:** Does the result follow the skill's rules, using the right tokens, structure, and accessibility checks?
3. **With and without:** I run the same prompt with the skill turned on and off, then compare the two outputs.
4. **Write it down:** Results and surprises go in `notes/`, and changes go through pull requests.

## Using a Skill

These are experiments, so try them at your own risk.

- **Claude.ai:** Zip a skill's folder, then upload it under **Settings → Capabilities → Skills** and turn it on.
- **Claude Code:** Copy a skill's folder into `~/.claude/skills/` (for all your projects) or `.claude/skills/` (for one project).

## What I'm Learning

This repo is part of my path from designer to design engineer. Along the way I'm:

- Learning Git and GitHub hands-on, working toward the GitHub Foundations certification
- Writing conventions for how a design system's skills should be structured
- Sketching how skills fit with tokens, components, and an MCP server into one system an agent can build UI from

Issues and Discussions are open. If you're working on something similar, I'd like to hear about it.

## Credits

- **[Ken Collins (@metaskills)](https://github.com/metaskills)**: the README format and approach to explaining skills here are modeled on his [skill-design-guide](https://github.com/metaskills/skill-design-guide). Thank you, Ken.
- **[Anthropic](https://github.com/anthropics/skills)**: the Agent Skills format, documentation, and example skills this work builds on.

## License

[MIT](LICENSE) © Kyle Goodwin
