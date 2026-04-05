# viz-pack

Four Claude skills that turn any content into visuals. Paste a URL, attach a doc, or reference something in conversation — then type the command.

## Skills

| Command | What it does | Output |
|---------|-------------|--------|
| `diagram it` | Picks the best diagram type (flowchart, tree, timeline, concept map) and renders it | Excalidraw diagram inline in chat |
| `nano this` | Sends content to Gemini image generation with a Swiss Pulse design prompt | Polished infographic PNG |
| `vis it` | Picks the best visual format (chart, timeline, explainer, pipeline, comparison) | Interactive widget inline in chat |
| `ver it` | Builds a Swiss Pulse interactive HTML (hero metric, stats, Chart.js graph, dark mode) | Published shareable link |

## Install

1. Open [Claude.ai](https://claude.ai) → Settings → Claude's Memory → Skills
2. Create a new skill for each `.md` file
3. Copy the file contents into the skill
4. Save

That's it. The skills trigger automatically when you type the command.

## Usage

```
diagram it https://some-article-url.com
```

```
nano this
[attach a PDF or doc]
```

```
vis it https://medium.com/some-interesting-post
```

```
ver it
[paste text, attach a file, or reference something in the conversation]
```

You can also use them with content already in your conversation:

```
that strategy we just discussed — diagram it
```

## How they work

Each skill follows the same pattern:

1. **Acquire** — fetch the URL, read the uploaded file, or pull from conversation context
2. **Analyze** — extract the structure: metrics, sequences, relationships, takeaways
3. **Render** — produce the visual in the skill's output format

The skills are designed to stay out of each other's way:

- Need a diagram? → `diagram it` (Excalidraw)
- Need a static infographic image? → `nano this` (Gemini image gen)
- Need an inline interactive visual? → `vis it` (Visualizer widget)
- Need a shareable link? → `ver it` (HeyGenverse publish)

## Design system

Three of the four skills (`nano this`, `vis it`, `ver it`) use **Swiss Pulse** — a design system inspired by Josef Müller-Brockmann's Swiss International Typographic Style:

- **Palette:** Black, white, and one accent color — electric blue `#0066FF`
- **Typography:** Helvetica / system grotesque, two weights only (400, 600)
- **Layout:** Grid-locked, generous whitespace, no decoration
- **Data-first:** Lead with the hero metric, support with charts and stats
- **Dark mode:** Always supported

## Notes

- `nano this` requires a Gemini API key. Add yours to the skill file before use.
- `ver it` publishes to [HeyGenverse](https://www.heygenverse.com) — you'll need access to use this skill as-is. Fork and modify the publish step for your own platform.
- `vis it` and `diagram it` work out of the box with no external dependencies.

## License

MIT