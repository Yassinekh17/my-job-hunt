---
name: resume-tailor
description: Select and re-order verified master-profile facts to match one specific job posting, producing a tailoring plan (headline, summary angle, section order, bullet selection, keyword map). Use after eligibility is confirmed and before writing resume text.
---

# Resume Tailor

Decides **what goes in the CV for this job** and in what order. It selects and re-orders; it never invents.

## Inputs
- `jobs/<slug>/job.md` (parsed requirements and ATS keywords)
- Eligibility report (strongest angles and gaps)
- `master-profile`

## Procedure

1. **Read the posting like a recruiter.** Identify the top 5 things the employer will screen for, in priority order. Usually these are the first 3 to 5 requirements and anything repeated 2+ times.
2. **Build the keyword map.** For each ATS keyword in the job file, find the master-profile evidence. Output a table:
   | Keyword (exact) | In profile? | Where it will appear | Section |
   Rules: use the posting's exact spelling (for example "Node.js", "REST APIs", "CI/CD"). Add a keyword only when the profile truly supports it. Missing keywords are listed as gaps, never inserted.
3. **Choose the positioning.** Pick one headline that mirrors the job title and the candidate's true identity, for example "Full-Stack Engineer | Node.js, Flutter, MongoDB". Do not claim a seniority the profile does not support.
4. **Select projects and experience.**
   - Rank every project and role by relevance to the posting (stack overlap + responsibility overlap).
   - Keep the top 2 to 3 projects and all relevant roles. Drop or compress the rest to a single line.
   - Choose 3 to 5 bullets per item: the ones that prove the top requirements. Order bullets by relevance, not chronology.
5. **Choose the skills block.** Group into 3 to 4 labelled lines. Put the posting's required skills first in each line. Remove skills the job will not value if they dilute (a long list of unrelated tools looks weak).
6. **Choose the section order.**
   - Student or recent graduate (default for Yassine until real full-time experience exists): Header, Summary, Education (if recent), Projects, Experience, Skills, Certifications.
   - Experienced hire for the role: Header, Summary, Experience, Projects, Skills, Education.
   - Decide per job and justify in one line.
7. **Plan the summary.** 3 lines max: identity + strongest proof + stack match + what they want to do for this employer. Mirror 2 to 3 of the posting's keywords naturally.
8. **Plan the gaps.** For each gap, decide: omit silently (not required), address in cover letter (significant), or note "learning X" only if the profile contains real evidence of learning. Never fake coverage.
9. **Choose language and region conventions.** Match the posting language. Country rules:
   - US/Canada: no photo, no date of birth, no marital status
   - France/Tunisia/Gulf: photo optional, follow the posting; still omit sensitive data unless required
   - Always one page for under 10 years of experience unless the posting asks for more

## Output: tailoring plan (save as `jobs/<slug>/tailoring-plan.md`)
```markdown
# Tailoring plan: <Job> at <Company>
Headline: ...
Summary angle: ...
Top 5 screening criteria: 1... 2... 
Section order: ...
Keyword map: (table)
Experience/project selection: (ranked list with bullet IDs from master profile)
Skills block: (grouped lines)
Gaps and handling: (table)
Language / region conventions: ...
Open questions for the user: ...
```

## Rules
- Every bullet chosen must trace back to a master-profile fact.
- Keyword stuffing is forbidden: each keyword appears where it is true, at most 2 to 3 times in the whole document.
- If the plan needs a fact marked TODO in the master profile, add it to "Open questions".
