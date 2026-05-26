# Engram Cohort Training

Workshops to prepare the Engram team for Anthropic's Partner Network certification.

Five workshops mirroring the Claude Partner Network learning path on Anthropic Skilljar, plus a full CCAF practical-exam simulation. Each workshop is a self-contained interactive quiz.

## Workshops

| # | Workshop | Status | Questions |
|---|---|---|---|
| 01 | [Skills](topics/skills/) | Live | 31 verified |
| 02 | [Claude API](topics/claude-api/) | Live | 28 verified |
| 03 | [Model Context Protocol](topics/mcp/) | Coming soon | — |
| 04 | [Claude Code](topics/claude-code/) | Coming soon | — |
| Final | [CCAF simulation](topics/ccaf-simulation/) | Live | 120 verified (60 from paullarionov + 60 from cyberskill, practice + timed exam) |

All questions are sourced verbatim from the [`claude-certified-architect`](https://github.com/paullarionov/claude-certified-architect) repo. Nothing is AI-generated.

## Run locally

```bash
npx serve .
```

Or just open `index.html` in a browser.

## Deploy

This is a static site. Deploys to Vercel with zero configuration. Push to GitHub, import in Vercel, done.

```bash
git push origin main
# then in Vercel: New Project → Import Git Repository
```

## Structure

```
engram-cohort-training/
├── index.html                       # topic picker (landing)
├── topics/
│   ├── skills/index.html            # workshop 01 (live)
│   ├── claude-api/index.html        # placeholder
│   ├── mcp/index.html               # placeholder
│   ├── claude-code/index.html       # placeholder
│   └── ccaf-simulation/index.html   # placeholder
├── vercel.json                      # static deploy config
├── package.json                     # dev script
├── README.md
├── LICENSE                          # MIT
└── .gitignore
```

## Adding a new workshop

1. Author the quiz HTML in `topics/<workshop-name>/index.html`. Use the Skills quiz as the template.
2. Source every question from a verified file (e.g., the CCAF repo). Cite the source in a comment.
3. Update the topic card in the root `index.html` — flip `class="topic upcoming"` to `class="topic"` and change `status coming` to `status live`.
4. Update this README's status table.

## Design system

Engram brand tokens (paper, ink, single orange accent, kiss-stack headline, hairline rules) are inlined per-file. The Skills quiz contains the canonical CSS — copy from there when authoring a new workshop. Do not introduce gradients, shadows, or a second accent color.

## License

MIT. See [LICENSE](LICENSE).

---

Engram · agentic media. · 2026
