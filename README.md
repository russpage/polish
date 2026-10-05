# Polish

**Edit AI drafts in your own voice, learned from what you wrote before AI.**

Polish reads writing you did yourself, such as old LinkedIn posts, sent email, or a blog. It skips pieces that show AI habits and builds a voice profile you can correct. Then it marks each AI habit in your draft with a short code, rewrites the draft in your voice, and checks that every name, number, and quote is still there.

In one test on a 270-word LinkedIn post, Polish found 7 AI habits and cut the post's score from 5.6 to 0.8 points per 100 words (Polish's own rubric, not an AI detector), with no facts lost. For fiction, it uses findings from [StoryScope](https://arxiv.org/abs/2604.03136) (Russell et al., COLM 2026), a study of about 61,000 human and AI stories, and gives you story notes instead of rewriting your plot.

To start, [install it](#install) with two commands, then type `/polish` and paste a draft.

## What it does

Polish is a skill for Claude and other AI agents. It does three jobs:

1. **Removes AI tells** from any prose: straw contrasts ("It isn't X, it's Y"), recap endings, announced points, reflex triplets, dash habits, inflated importance, brochure words, label lists, and chat leftovers.
2. **Fixes AI fiction**: explained themes, emotion told only through physical sensation, scenes crowded with smells, weather that copies the mood, vague allusions, and tidy one-thread plots. Story-level problems come back as notes for the writer, not rewrites.
3. **Matches your voice** by learning from writing you did yourself.

## Teach it your voice

Polish keeps two kinds of voice, saved separately:

- **Personal voice** (`voice.md`) for your own emails, posts, and bios. Sources: your LinkedIn posts, your Gmail Sent folder, your blog or newsletter, or a Drive, Dropbox, or local folder of your writing.
- **Company voice** (`brand-voice.md`) for website copy, ads, newsletters, and help docs. Sources: brand guidelines, the company website, and past copy the team wrote.

A voice source only helps if a person wrote it. If you used AI to write email (for example Gmail's "Help me write") or LinkedIn posts, Polish would learn the AI's habits instead of yours. Polish warns you about this, checks each piece for AI tells, skips pieces that look machine-written, and prefers work from before late 2022.

It then builds a short profile (sentence length, favorite words, punctuation, how you open and close, how you joke and hedge), shows it to you for corrections, and saves it so it does not have to reread everything next time.

Example:

```
/polish

My voice: my LinkedIn posts and my Gmail sent mail from before 2023.

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
