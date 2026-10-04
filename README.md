# Polish

Polish is a skill for Claude and other AI agents. It edits writing that sounds machine-made until it sounds like the person who wrote it. It changes how things are said, never what is said.

It does three jobs:

1. **Removes AI tells** from any prose: straw contrasts ("It isn't X, it's Y"), recap endings, announced points, reflex triplets, dash habits, inflated importance, brochure words, label lists, and chat leftovers.
2. **Fixes AI fiction**: explained themes, emotion told only through physical sensation, scenes crowded with smells, weather that copies the mood, vague allusions, and tidy one-thread plots. Story-level problems come back as notes for the writer, not rewrites.
3. **Matches your voice** by learning from writing you did yourself.

## Teach it your voice

Point Polish at your own human-written work:

- a folder on Google Drive, Dropbox, OneDrive, or your computer;
- your blog or newsletter (give the URL);
- past documents, emails, or posts you wrote.

Polish checks each piece for AI tells and skips any that look machine-written. Work from before late 2022 is the safest source. It then builds a short voice profile (sentence length, favorite words, punctuation, how you open and close, how you joke and hedge), shows it to you for corrections, and can save it as `voice.md` so it does not have to reread everything next time.

Example:

```
/polish

My voice: the "Writing" folder in my Google Drive, and my blog at example.com/blog.

Text to polish:
[paste text]
```

## Install

### Claude Code

```text
/plugin marketplace add russpage/polish
/plugin install polish@polish
```

### Claude apps

On GitHub, click **Code**, then **Download ZIP**. In Claude, open Settings and add the ZIP as a new skill.

### Other agents

Copy `SKILL.md` into your agent's skills folder, or run:

```bash
npx skills add russpage/polish
```

## Use

```
/polish
[paste text]
```

Or in plain words: "Polish this post," or "Polish the prose in docs/launch.md." For a file, Polish changes only the prose and leaves code, data, and links alone.

## How it decides

A language model picks the most probable next word, so its default choices are average ones. People write for one reader about one thing, so their choices are more specific. Polish finds the average choices and replaces them with the writer's own, or with the plain choice when it does not know the writer's.

The tells are grouped by level and coded so a report is easy to scan:

| Code | Level | Examples |
|------|-------|----------|
| S1 to S11 | Sentences | straw contrast, recap ending, announced point, threes by reflex, dash habit, commentary tag |
| W1 to W4 | Words | model favorites, importance inflation, brochure words, vague sourcing |
| P1 to P4 | The page | bold label lists, dressed-up headings, recap sections, format leaks |
| C1 to C3 | Chat leftovers | assistant voice, knowledge-limit filler, text about the text |
| R1 | The reader | rebuilding context the reader already has |
| F1 to F6 | Fiction | explained meaning, body-only emotion, mood weather, vague allusion, intro by looks, tidy story |

Polish never adds facts. Every name, number, date, quote, and source in the original stays, and nothing new is invented.

## Sources

- Wikipedia, [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), maintained by WikiProject AI Cleanup.
- Russell, Rajendhran, Pham, Iyyer, and Wieting, [StoryScope: Investigating idiosyncrasies in AI fiction](https://arxiv.org/abs/2604.03136), COLM 2026.

## License

MIT. See [LICENSE](LICENSE).
