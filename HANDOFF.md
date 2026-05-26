# Agent Handoff · Engram Cohort Training

> **Summary.** Engram's internal training site for Anthropic Partner Network cert prep. Workshop 01 (Skills) is live with 31 questions. **Workshop 02 (Claude API) is due TONIGHT, Tue May 26 2026, 18:00 CET.** Authoring it is the next move.
>
> **Today:** 2026-05-26. **Workshop date:** 2026-05-26 18:00 CET. **You have ~6 hours.**

---

## Load these first

| File | Why |
| - | - |
| `README.md` | Repo overview, status table, authoring instructions |
| `topics/skills/index.html` | **Canonical template.** 52 KB, 31 questions, full Engram brand. Copy this for new topics |
| `index.html` | Topic-picker landing page. Each new workshop needs its card flipped from `upcoming` to live |
| `vercel.json` | Static deploy config. No build step |
| `~/.claude/projects/C--Claude/memory/MEMORY.md` | Luka's context (founder of Engram, on Partner Network architect track, hiring 2 architects, deadline end of May) |

---

## Mission

Engram is in the Anthropic Partner Network architect cert cohort. Five workshops on Skilljar plus a CCAF practical exam. This repo is the **internal prep tool** the Engram team uses to retrieve-practice every workshop's content.

- Five workshops mirror the official Anthropic learning path
- Quiz format because retrieval practice has the highest ROI for multiple-choice certs
- Questions sourced verbatim from `paullarionov/claude-certified-architect` GitHub repo. Nothing AI-generated. The repo's credibility rests on this rule

You are taking over from Luka. He authored Workshop 01 yesterday and shipped it. You're authoring the rest.

---

## State

| Asset | Where | Status |
| - | - | - |
| Workshop 01 · Skills | `topics/skills/index.html` | Live · 31 verified questions · ship template |
| Workshop 02 · Claude API | `topics/claude-api/index.html` | **Skeleton stub, ~5 KB. Due tonight 18:00 CET** |
| Workshop 03 · MCP | `topics/mcp/index.html` | Skeleton stub. Due Wed May 27 18:00 CET |
| Workshop 04 · Claude Code | `topics/claude-code/index.html` | Skeleton stub. Due Thu May 28 18:00 CET |
| CCAF practical sim | `topics/ccaf-simulation/index.html` | Skeleton stub. 60 questions planned. No fixed deadline |
| Root index / picker | `index.html` | Live. Cards toggle `class="topic"` vs `class="topic upcoming"`, `status live` vs `status coming` |
| Deploy | Vercel via git push | Auto-deploys on push to main |
| Local dev | `npx serve .` (per `package.json`) | Or just open `index.html` in a browser |

Confirm live URL by checking `.vercel/project.json` or asking Luka. Likely something like `engram-cohort-training.vercel.app` or a custom domain off `engram.media`.

---

## Immediate next action · Workshop 02 quiz

**Deadline: today, Tue May 26 2026, 18:00 CET.**

### Steps

1. **Read the Skills template end-to-end.** Open `topics/skills/index.html`. Understand the question-card structure, picker, hover/answered states, brand tokens inlined at the top. The pattern is your template
2. **Pull questions** from `paullarionov/claude-certified-architect` GitHub repo, the Claude API section. Use `gh repo clone` or browse via `gh api repos/paullarionov/claude-certified-architect/contents/...`. Cite the exact source file in a comment at the top of your new `topics/claude-api/index.html`
3. **Author `topics/claude-api/index.html`** by duplicating the Skills file, swapping the question array, updating the title and topic metadata. Do not redesign the UX
4. **Verify** by opening `localhost:3000/topics/claude-api/` after `npx serve .`. Spot-check 3 questions render correctly. Confirm the brand is identical (paper bg, ink text, single orange accent, kiss-stack headline if used)
5. **Update root `index.html`:** find the Claude API card, change `class="topic upcoming"` to `class="topic"` and `<span class="status">coming</span>` to `<span class="status">live</span>`
6. **Update `README.md`** status table: flip Claude API to `Live` and write the question count
7. **Ship:** `git add . && git commit -m "claude-api workshop · NN questions" && git push`
8. **Verify the deploy:** visit the live URL, click into Claude API, take 3 questions, confirm the new card on the landing page

### Success criteria

- Workshop 02 quiz live on Vercel before 18:00 CET today
- Question count > 25 (Skills has 31; aim for comparable)
- Every question cites its source file in an HTML comment
- Brand is pixel-consistent with Workshop 01
- README + landing page reflect the new live status

---

## Backlog (after Workshop 02 ships)

| Priority | Task | Deadline |
| - | - | - |
| P1 | Workshop 03 · MCP quiz | Wed May 27 18:00 CET |
| P2 | Workshop 04 · Claude Code quiz | Thu May 28 18:00 CET |
| P3 | CCAF practical-exam simulation · 60 questions | No fixed deadline · ship after Workshop 04 |

Same authoring pattern for each: duplicate Skills template, swap questions, flip the landing card, update README, push.

---

## Traps · do not

1. **Do not generate questions with AI.** Every question must come from a verified public source. This is the repo's load-bearing credibility rule
2. **Do not introduce a build step.** Static HTML is the architecture. No npm install, no bundler, no React. The whole point is portability and zero-ops deploy
3. **Do not add a second accent color.** Orange `#E8623C` is the only accent. The temptation will be green for "correct" and red for "incorrect" answers. Resist. Use icons, font-weight changes, layout shifts instead. Read `engram-brand` skill if you need to understand why
4. **Do not centralize CSS into a shared file.** Each topic inlines its tokens. The Skills file is the canon; copy-paste is the deliberate pattern. The `shared/` folder is for shared assets only, not styles
5. **Do not edit `C:\Claude\engram-skills-quiz\`.** That's the superseded prototype. Reference only for visual audit screenshots, then ignore
6. **Do not redesign the quiz UX per workshop.** Question card, picker, hover, answered, navigation — these are fixed. New workshop, same UX, different questions
7. **Do not use em-dashes (—) or en-dashes (–) in copy.** Global writing rule. Use period, comma, or split sentence

---

## Operational notes

- **Relevant Engram skills** (auto-load):
  - `engram-brand` — token canon (paper #F6F4EF, ink #0A0A0A, orange #E8623C, 1.5px hairlines, kiss-stack typography)
  - `impeccable` or `taste-skill` — UI critique if you need an audit
- **Verify after every push:** visit the live URL, click into the new topic, answer 3 questions, confirm the card on the landing page
- **Branch for risky edits.** Main auto-deploys
- **Ask Luka** (luka@engram.media) if you hit an architectural decision the README + this handoff don't cover

---

## Sibling workstream

There's a parallel Engram project at `C:\Users\Luka\Documents\engram-creative-mba-workshop\`. It's the Aleksandra Vuković Creative MBA workshop (Sat Jun 6, 2026). Different audience, different deliverable. **Do not touch it unless Luka asks.** Its handoff is at `C:\Users\Luka\Documents\engram-creative-mba-workshop\HANDOFF-AGENT.md` if you need to understand context.

---

## Open questions to confirm with Luka

1. Vercel project name / live URL (check `.vercel/project.json`)
2. Should the CCAF sim use a different UX (timed, mock-exam mode, randomized order, score at end)?
3. Who else consumes this repo? Just Engram cohort, or also the 2 architect-cohort hires Luka is recruiting?

---

Engram · agentic media. · 2026
