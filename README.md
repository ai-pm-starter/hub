# Hub — how we work

## Roadmap
| Days | Dates | Project | PM |
|---|---|---|---|
| 1 | Nov 2 | Setup | both |
| 2–4 | Nov 3–5 | P1 Conversion Teardown | Kapil |
| 5–6 | Nov 6–7 | P2 JobPilot v0 | Prashant |
| 7–10 | Nov 8–11 | P3 Funnel Leak Finder | Kapil |
| 11–15 | Nov 12–16 | P4 Visual Product Tagger | Prashant |
| 16–19 | Nov 17–20 | P5 Purchase Propensity | Kapil |
| 20–24 | Nov 21–25 | P6 Adaptive Homepage | Prashant |
| 25–30 | Nov 26–Dec 1 | P7 Recommender + Visual Search | Kapil |
| 31–36 | Dec 2–7 | P8 AI Shopping Concierge | Prashant |
| 37–42 | Dec 8–13 | P9 Shop-to-ERP Integration Agent | Kapil |
| 43–48 | Dec 14–19 | P10 Fraud Detection | Prashant |
| 49–55 | Dec 20–26 | P11 Churn & Win-back Agent | Kapil |
| 56–62 | Dec 27–Jan 2 | P12 JobPilot v1 | Prashant |
| 63–70 | Jan 3–10 | P13 0→1 Launch Studio | Kapil |

## Rhythm
- **Every morning, 15 min:** standup. Each person comments on the sprint's standup issue: Done / Next / Blocked.
- **Every evening:** review each other's PRs, move cards, add one line to the project's decision log.
- **Monday, 30 min:** sprint planning.
- **Sunday, 45 min:** sprint review (demo) + retro (`docs/sprints/sprint-NN/retro.md`).

## Roles per project
- **PM:** owns problem statement, PRD, scope cuts, success metrics, final call on trade-offs.
- **Builder:** the other person leads implementation; both write code.

## Definition of Done (every project)
- [ ] Live demo link
- [ ] README with demo GIF, eval results, limitations
- [ ] Eval set + results committed
- [ ] At least one ADR
- [ ] Sprint review + retro written
- [ ] LinkedIn post published

## Free models (Google AI Studio)
Checked Nov 1, 2026 on the [pricing page](https://ai.google.dev/gemini-api/docs/pricing). Free tiers change often: re-check before each project.

| Model ID | Free tier | Image input | Use for |
|---|---|---|---|
| `gemini-3.8-flash` | Yes | Check | P1 default (in `.env`) |
| `gemini-3.6-flash` | Yes | Check | Fallback |
| `gemini-3-flash-preview` | Yes | Yes | Fallback (preview) |
| `gemini-3.5-flash-lite` | Yes | Yes | Fast, cheap calls |
| `gemini-3.1-flash-lite` | Yes | Yes | Fast, cheap calls |
| `gemini-2.5-pro` | Yes | Yes | Hardest reasoning, low rate limits |
| `gemini-2.5-flash` / `gemini-2.5-flash-lite` | Yes | Yes | Stable fallback |

Known issue (Nov 1): `gemini-3.8-flash` is listed for our key but `generateContent` calls time out with no response. Test it before relying on it; fall back to a 2.5 model if it still hangs.

Not free: `gemini-4-argon`, `gemini-3.1-pro-preview`, image-generation models.
Free-tier prompts and outputs may be used by Google to improve its products: never send personal data.
