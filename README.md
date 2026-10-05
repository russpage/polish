# Writing

Writing skills for Claude and other AI agents, by Russ Page.

| Skill | What it does |
|---|---|
| [Polish](skills/polish/) | Edits AI drafts in your own voice, learned from what you wrote before AI. It finds AI habits, rewrites those lines, and keeps every fact. |

## Install

### Claude Code

Add the collection once, then install the skills you want:

```text
/plugin marketplace add russpage/writing
/plugin install polish@writing
```

### Claude apps

Download the skill's folder (for example `skills/polish`) as a ZIP and add it as a new skill in Claude's Settings.

### Other agents

```bash
npx skills add russpage/writing --skill polish
```

Or copy a skill's `SKILL.md` into your agent's skills folder.

## License

MIT. See [LICENSE](LICENSE).
