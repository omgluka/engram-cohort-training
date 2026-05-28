# Engram Cohort Training

Workshops to prepare the Engram team for Anthropic's Partner Network certification.

Five workshops mirroring the Claude Partner Network learning path on Anthropic Skilljar, plus a full CCAF practical-exam simulation. Each workshop is a self-contained interactive quiz.

## Workshops

| # | Workshop | Status | Questions |
|---|---|---|---|
| Guide | [Exam guide](topics/exam-guide/) | Live | reference (5 domains + weightings) |
| 01 | [Skills](topics/skills/) | Live | 31 verified |
| 02 | [Claude API](topics/claude-api/) | Live | 28 verified |
| 03 | [Model Context Protocol](topics/mcp/) | Live | 33 verified |
| 04 | [Claude Code in Action](topics/claude-code/) | Live | 42 verified |
| Final | [CCAF simulation](topics/ccaf-simulation/) | Live | 120 verified (60 from paullarionov + 60 from cyberskill, practice + timed exam) |

Every question carries a source-trust badge: `anthropic` (answer confirmed by docs.claude.com), `cyberskill` and `paul` (verbatim from the respective community sources). Each is also tagged with its CCAF domain (1 to 5). The exam guide maps the five weighted domains; its structure is credited to [@hooeem's public study guide](https://x.com/hooeem/status/2033198345045336559).

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
