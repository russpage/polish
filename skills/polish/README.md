# Polish

**Edit AI drafts in your own voice, learned from what you wrote before AI.**

Polish reads writing you did yourself, such as old LinkedIn posts, sent email, or a blog. It skips any piece that shows AI habits and builds a voice profile you can correct. Then it finds the AI habits in your draft, rewrites those lines the way you would write them, and checks that every name, number, and quote is still there.

> **Before:** The useful lesson is to make the choice easier for the customer—and give AI a clearer message to work with.
>
> **After:** That shelf makes the choice easy. Do the same for your customers, and AI will have a clearer message to work with.

That line comes from a test on a 270-word LinkedIn post. Polish found 7 AI habits and cut the post's score from 5.6 to 0.8 points per 100 words, with no facts lost. (The score is Polish's own rubric, not an AI detector.)

To start, [install it](#install) with two commands, then type `/polish` and paste a draft.

## What it fixes

| AI habit | Example | What Polish does |
|---|---|---|
| A contrast against something nobody said | "It isn't a tool, it's a partner." | States the real point |
| A last line that repeats the paragraph | "Small change, big results." | Cuts it, or keeps only a new fact |
| Announcing a point instead of making it | "Here's the thing:" | Starts with the point |
| Lists of three by habit | "fast, flexible, and future-ready" | Keeps only the real items |
| Em dashes everywhere | "slipped a week — again — and" | Uses commas, colons, or periods |
| Big words for ordinary facts | "a pivotal moment in our journey" | States what happened |
| Brochure words | "nestled," "vibrant," "world-class" | Says what the thing is and has |
| "Experts say" with no source | "Studies show..." | Names the source, or cuts the claim |
| Bold labels on every bullet | "**Speed:** Pages load faster." | Turns the list into a sentence |
| Chatbot leftovers | "I hope this helps!" | Deletes them |
| A reply that re-explains what the reader knows | Three sentences of recap, then the answer | Puts the answer first |

Polish never adds facts. If a line needs a detail you did not give, it writes a simpler line or asks you.

## Fiction

For stories, Polish uses findings from [StoryScope](https://arxiv.org/abs/2604.03136) (Russell et al., COLM 2026), which compared about 10,000 human stories with 51,000 AI stories.

- It edits sentences that explain the story's meaning, show every feeling only through the body ("her chest tightened"), put a smell in every scene, or make the weather match the mood.
- It does not rewrite your plot. Problems like a single storyline, events told strictly in order, or a neat inner-peace ending come back as up to five notes for you to decide on.

## Teach it your voice

Polish keeps two voices, saved as separate files:

- **Your personal voice** (`voice.md`), for your own emails, posts, and bios. It learns from your LinkedIn posts, your Gmail Sent folder, your blog or newsletter, or a folder of your writing on Google Drive, Dropbox, or your computer.
- **Your company's voice** (`brand-voice.md`), for website copy, ads, newsletters, and help docs. It learns from brand guidelines, the company website, and past copy the team wrote.

A voice source helps only if a person wrote it. If you used AI to write emails (for example Gmail's "Help me write") or LinkedIn posts, Polish would learn the AI's habits instead of yours. So Polish warns you, checks each piece, skips the ones that look machine-written, and prefers writing from before late 2022.

It then shows you the profile (sentence length, favorite words, punctuation, how you open and close, how you joke and hedge) so you can correct it, and saves it for next time.

```
/polish

My voice: my LinkedIn posts and my Gmail sent mail from before 2023.

Text to polish:
[paste text]
```

## Install

### Claude Code

```text
/plugin marketplace add russpage/writing
/plugin install polish@writing
```

### Claude apps

Download the `skills/polish` folder as a ZIP and add it as a new skill in Claude's Settings. (On GitHub, **Code → Download ZIP** gives you the whole repo; upload just the `polish` folder.)

### Other agents

Copy `SKILL.md` into your agent's skills folder, or run:

```bash
npx skills add russpage/writing --skill polish
```

## Use

```
/polish
[paste text]
```

Or in plain words: "Polish this post," or "Polish the prose in docs/launch.md." For a file, Polish changes only the prose and leaves code, data, and links alone.

## Why AI writing sounds the way it does

A language model picks the most likely next word, so its default choices are average ones. People write for one reader about one thing, so their choices are more specific. StoryScope measured this: human stories sat far from the average, and AI stories crowded near it. Polish looks for the average choices and replaces them with yours, or with the plain choice when it does not know yours.

## Sources

- Wikipedia, [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), maintained by WikiProject AI Cleanup.
- Russell, Rajendhran, Pham, Iyyer, and Wieting, [StoryScope: Investigating idiosyncrasies in AI fiction](https://arxiv.org/abs/2604.03136), COLM 2026.

## License

MIT. See [LICENSE](../../LICENSE).
