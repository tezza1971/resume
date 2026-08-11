---
name: quiz-me
description: >-
  Quizzes the user in Plan mode to build a tech resume from scratch, then writes
  ATS-friendly resume.md and structured resume.json. Use when the user says
  quiz-me, quiz me, build resume from scratch, or resume questionnaire.
disable-model-invocation: true
---

# Quiz me — build resume from scratch

Interactive questionnaire that gathers real career facts, then produces hybrid ATS markdown + JSON Resume–shaped source of truth.

## Hard rules

- **Immediately switch to Plan mode** (`SwitchMode`, `target_mode_id: plan`) before asking questions. Explain briefly: quiz first; no resume files until a plan is approved.
- Ask **1–2 questions per turn** using [question-bank.md](question-bank.md). Do not dump the whole bank.
- **Never invent metrics**, employers, titles, or dates. Ask follow-ups; use `~` or qualitative outcomes when numbers are unknown.
- Follow project rule **resume-architect** for bullet voice and bans.
- Stay in Plan mode through the quiz. When enough data exists, call **CreatePlan** with the resume outline and file targets. Write files only after the user confirms / execution is allowed.
- Read [reference-ats-2026.md](reference-ats-2026.md) before drafting final markdown structure.

## Workflow

1. Switch to Plan mode.
2. Quiz in section order from [question-bank.md](question-bank.md); track gaps mentally (target role → contact → arc → roles → skills → education → projects → summary).
3. For each experience outcome lacking a metric, use the metric follow-ups before accepting the bullet.
4. When the completion gate is met, CreatePlan covering:
   - Target role framing
   - Section outline (hybrid: Summary, Skills, Experience, …)
   - Exact files: `resume.md`, `resume.json` at repo root
   - Note: apply ATS checklist + resume-architect on write
5. After approval, write both files. Re-check [reference-ats-2026.md](reference-ats-2026.md).

## Output: `resume.md`

Single-column hybrid markdown. Contact in the body. Standard headings only.

```markdown
# Full Name
City, Region | phone | email | LinkedIn | GitHub

## Summary
[2–3 lines: target role, years/domain, one quantified achievement if real]

## Skills
**Languages:** …
**Frameworks:** …
**Cloud / Infra:** …
**Tools:** …
**Certifications:** …  (omit empty groups)

## Experience

### Job Title
Company | City or Remote | Month YYYY – Month YYYY or Present
- [Outcome/metric] by [action/system] using [tech]
- …

## Projects
### Project Name
- …

## Education
Degree, Field — School | Month YYYY or Year

## Certifications
Name — Issuer | Year
```

## Output: `resume.json`

JSON Resume–shaped object (subset is fine). Map quiz answers into fields like:

```json
{
  "basics": {
    "name": "",
    "label": "",
    "email": "",
    "phone": "",
    "url": "",
    "summary": "",
    "location": { "city": "", "region": "", "countryCode": "" },
    "profiles": [{ "network": "LinkedIn", "url": "" }]
  },
  "work": [{
    "name": "",
    "position": "",
    "location": "",
    "startDate": "YYYY-MM",
    "endDate": "YYYY-MM",
    "summary": "",
    "highlights": []
  }],
  "education": [],
  "skills": [{ "name": "Languages", "keywords": [] }],
  "projects": [],
  "certificates": []
}
```

- Use ISO-ish `YYYY-MM` in JSON; omit `endDate` or use a clear present convention only if documented in the file (prefer omitting `endDate` for current roles and note `"Present"` in markdown).
- Put remote/visa/open-to-work in JSON only if the user agreed those may be public (e.g. under `basics` meta or a small `meta` object). Default: omit.

## Done criteria

- [ ] Plan mode used for the quiz
- [ ] CreatePlan approved before writes
- [ ] `resume.md` passes ATS checklist (headings, dates, body contact, no layout chrome)
- [ ] `resume.json` mirrors the same facts
- [ ] No invented metrics; resume-architect voice throughout
