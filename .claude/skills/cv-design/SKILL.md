---
name: cv-design
description: Visual design standard for the CV (layout, typography, spacing, hierarchy, color) that stays 100% ATS-parsable. Use when choosing or adjusting how the CV looks, before formatting, or when the user asks for a nicer-looking CV.
---

# CV Design

Good CV design is **invisible structure**: easy for a recruiter to scan in 6 to 10 seconds and trivial for an ATS to parse. When style and parsing conflict, parsing wins.

## Design principles
1. **Hierarchy:** name > section titles > entry titles (role/project) > body text > dates/meta. Differences come from size, weight and spacing, never from decoration.
2. **Scan path:** the top third of the page must show who the candidate is, the target title, and the strongest proof (summary + first entry).
3. **White space:** margins 1.5 to 2 cm, 8 to 10 pt above section titles, consistent gaps. Dense but not cramped.
4. **Consistency:** the same pattern for every entry (title, company, location, dates, bullets).
5. **One accent colour** at most (dark navy `#1F3A5F` or charcoal `#333333`) for the name and section rules; body text black.

## Approved templates
| Template | Use for | Notes |
|----------|---------|-------|
| **Classic single column** (default) | Almost every job, ATS portals | Name top-left or centered, contact line, summary, sections with thin rules |
| **Modern minimal** | Startups, product and design-minded companies | Larger name, accent colour on section titles, generous spacing |
| **Compact technical** | Engineering roles with many projects | 10 pt body, projects emphasized, skills block compact, still one column |

Default for Yassine's applications: **Classic single column** (student/early-career profile with projects and an end-of-study project).

## Specification (Classic)
- **Page:** A4 (or Letter for US), one page.
- **Fonts:** Calibri or Arial. Name 20 pt bold; headline 11 pt; section titles 11 pt bold uppercase letter-spaced, thin bottom rule; entry titles 10.5 pt bold; body 10.5 pt; dates 10 pt, right-aligned via tab stop.
- **Bullets:** round, 0.4 cm indent, 2 to 3 pt spacing.
- **Header:** name, then headline line, then a single contact line separated by `|`.
- **Links:** plain readable URLs (for example `github.com/Yassinekh17`).
- **Photo:** none by default; include only if the user asks or the posting requires it.

## What to avoid
- Two-column layouts, sidebars, tables, text boxes, charts, skill bars, star ratings, percentage proficiency, icons used as labels, graphics, watermarks, coloured backgrounds, decorative fonts, small fonts under 10 pt.
- Over-bold text: bold only names, titles, and at most one key metric per bullet.

## When the user wants "a more designed CV"
Offer a **second, separate PDF** for human readers (networking, email, portfolio), never for ATS uploads. Keep an ATS version as the one submitted to portals.

## Output
A short design brief for `resume-formatter`:
```markdown
Template: Classic single column
Page: A4, margins 1.6 cm
Fonts: Calibri 10.5 / name 20 / sections 11
Accent colour: #1F3A5F
Section order: <from tailoring plan>
Photo: no
Notes: <region, language, special portal rules>
```
