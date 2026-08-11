# resume

Public source of truth for **Terence Kearns** — Solutions Architect / Co-Founder, NDX Pty Ltd.

ATS-friendly markdown plus a structured JSON twin. Live site: [resume.terencekearns.com](https://resume.terencekearns.com) (Astro on Cloudflare Workers). Company stand-in link: [ndx.video](https://ndx.video).

## Source files

| File | Role |
|------|------|
| [`resume.md`](resume.md) | Human / ATS resume (hybrid layout) |
| [`resume.json`](resume.json) | JSON Resume–shaped mirror + public work prefs |

Edit both when facts change. Prefer real metrics; never invent numbers.

## Layout conventions

- Single-column hybrid: **Summary → Skills → Experience → Projects → Education → Certifications**
- Contact in the document body (no phone on the public resume)
- Dates as `Month YYYY – Present` when known; honest year ranges when months are unknown
- Bullets: outcome + action + tech ([resume-architect](.cursor/rules/resume-architect.mdc) rule)

## Cursor tooling

| Path | Purpose |
|------|---------|
| [`.cursor/rules/resume-architect.mdc`](.cursor/rules/resume-architect.mdc) | Metric-driven bullets; ban AI buzzwords |
| [`.cursor/skills/quiz-me/`](.cursor/skills/quiz-me/) | Plan-mode questionnaire to rebuild/extend the resume from scratch |

Invoke the skill with **quiz-me** / “build resume from scratch”.

## Website

Rendered at [resume.terencekearns.com](https://resume.terencekearns.com) by the sibling repo [`tezza1971/resume-website`](https://github.com/tezza1971/resume-website) (Astro on Cloudflare Workers). That Worker fetches this repo’s public raw [`resume.md`](https://raw.githubusercontent.com/tezza1971/resume/main/resume.md) and links back here as the edit source.

## Contact

- Email: terence@ndx.au
- Region: Northern Rivers, NSW, Australia
- Remote · Australian citizen · open to work (see `meta.workPreferences` in `resume.json`)
