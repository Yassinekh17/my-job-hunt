---
name: resume-build-writer
description: Assemble the complete tailored CV text from the tailoring plan, section builder output and quantified bullets into one coherent, truthful, ATS-ready document in Markdown. Use after tailoring and quantifying, before ATS scoring and formatting.
---

# Resume Build Writer

The editor. It assembles the final CV content and makes it read like one voice, within one page where possible.

## Inputs
`tailoring-plan.md`, section drafts (from `resume-section-builder`), quantified bullets (from `resume-quantifier`), `master-profile`, `jobs/<slug>/job.md`.

## Procedure

1. **Assemble** sections in the order set by the tailoring plan.
2. **Enforce length:**
   - Under 10 years of experience: **1 page** (about 450 to 600 words).
   - 10+ years or academic/research roles: 2 pages max.
   - If over: cut in this order: oldest bullets, least relevant project, extra skills, summary length. Never shrink the font below 10 pt to fit.
3. **Voice pass:** consistent tense, consistent punctuation (bullets end without periods, or all with periods), active verbs, no repeated starting verbs, no buzzwords (see `resume-ats-optimizer` banned list).
4. **Relevance pass:** every line must either prove a requirement or add credibility for the role. Remove the rest.
5. **Truth pass (mandatory):** for every bullet, confirm a master-profile source exists. Remove or flag anything that does not. Check every number is verified or user-confirmed.
6. **Consistency pass:** dates, location format, tool spellings, capitalization of technologies (JavaScript, Node.js, MongoDB, Flutter, GitHub), link formats.
7. **Keyword pass:** confirm the top keywords from the tailoring plan appear naturally; do not exceed 2 to 3 mentions each.
8. **Output** `jobs/<slug>/cv.md` in this canonical structure:

```markdown
# FULL NAME
Headline | Target Title
City, Country | email | phone | linkedin | github | portfolio

## Summary
...

## Experience
### Title | Company | City, Country | Mon YYYY - Mon YYYY
- bullet
...

## Projects
### Name | Role | Stack | link | dates
- bullet

## Education
...

## Skills
Category: a, b, c

## Certifications
...
```

9. **Self-review checklist** (return it with the CV):
   - One page? Sections in the plan's order?
   - Zero unverified facts or numbers?
   - Top 5 screening criteria visible in the top third of the page?
   - No first person, no "responsible for", no tables for content?
   - Spelling and grammar clean in the posting's language?

## Rules
- Write the CV in the same language as the job posting.
- If a section would be empty or weak, omit it rather than pad it.
- Never add a "References available on request" line.
