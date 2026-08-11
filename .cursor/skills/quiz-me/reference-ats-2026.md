# ATS / AI resume checklist (2026)

Screening layers: **parser → keyword/semantic score → human skim**. Optimize all three.

## Format (parser reliability)

- Single-column hybrid: short **Summary** + grouped **Skills**, then reverse-chronological **Experience**
- Standard headings only: `Summary`, `Skills`, `Experience`, `Projects`, `Education`, `Certifications`
- Contact in the **document body** (first lines), not headers/footers
- Dates: `Month YYYY – Month YYYY` or `Month YYYY – Present` (never year-only; prefer `Present` over `Current`)
- No tables, multi-column layouts, text boxes, icons, photos, charts, or skill bars
- Plain selectable text; system-safe fonts if exporting later (Arial, Calibri, Georgia, Times)
- Applications: text-selectable PDF; DOCX only when a portal requires it
- Sanity check: paste into a plain-text editor — reading order and fields must survive

## Scoring (AI / semantic ATS)

- Put must-have keywords in **context** (summary + bullets), not only a skills wall
- Do not keyword-stuff or use hidden text — modern systems penalize manipulation
- Quantified outcomes score higher than vague responsibilities
- Group skills (~12–20 specific items): Languages / Frameworks / Cloud / Tools / Certifications
- Keep title progression and dates consistent with LinkedIn when applicable
- Semantic synonyms help when honest; fluff leadership language does not

## Source of truth

- Prefer structured data (`resume.json`) plus human ATS markdown (`resume.md`)
- Render PDFs from structured/markdown sources later; do not reverse-engineer layout-heavy PDFs as the master copy

## Writing (align with resume-architect)

- Formula: **[Outcome/metric] by [action/system] using [tech]** when metrics exist
- Never invent metrics; use `~` ranges or qualitative results when exact numbers are unknown
- Ban AI buzzwords (spearheaded, leveraged, cutting-edge, seamlessly, etc.)
- One outcome per bullet; past tense for past roles; present for current
