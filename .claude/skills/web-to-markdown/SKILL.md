---
name: web-to-markdown
description: Fetch a job posting URL (or any web page) and convert it into clean, structured Markdown with the requirements extracted. Use first whenever the user gives a job link, before assessing fit or writing anything.
---

# Web to Markdown

Turns a job-posting link into a clean, structured Markdown file that every other skill reads. Nothing downstream should ever work from a raw URL.

## When to use
- The user gives a job URL (LinkedIn, Indeed, Welcome to the Jungle, company career page, ATS page such as Greenhouse, Lever, Workable, Ashby).
- The user pastes a job description as raw text (skip the fetch step, run steps 3 to 6).

## Procedure

1. **Fetch** the URL with WebFetch. Ask for the full page text, not a summary.
2. **If the fetch fails or returns a login wall / empty shell:**
   - Try once with a WebSearch for the exact job title + company to find a public copy (company careers page, ATS-hosted page).
   - If still blocked, stop and ask the user to paste the job description text. Never guess the content of a posting.
3. **Strip noise:** navigation, cookie banners, "similar jobs", footer, legal boilerplate, application form fields.
4. **Keep the original wording** of requirements and responsibilities. Do not paraphrase them; later skills match keywords exactly as written.
5. **Structure** the result using the template below.
6. **Extract the requirement lists** (section "Parsed requirements") by classifying every requirement as hard or soft using the rules below.
7. **Save** to `jobs/<company>-<role>-<YYYY-MM-DD>/job.md` and return the path.

## Output template

```markdown
# <Job title> at <Company>

- **Source URL:** <url>
- **Fetched:** <date>
- **Location:** <city / country / remote policy, incl. timezone or country restrictions>
- **Employment type:** <full-time / contract / internship / ...>
- **Seniority:** <junior / mid / senior / lead, as stated or inferred (mark "inferred")>
- **Salary:** <as stated, or "not stated">
- **Language of posting:** <en / fr / ...>

## About the company
<2-4 sentences, original wording trimmed>

## Responsibilities
- ...

## Requirements (verbatim)
- ...

## Nice to have (verbatim)
- ...

## Benefits / process
- ...

## Application instructions
<what the application asks for: CV, cover letter, code sample, portfolio, questions, deadline>

## Parsed requirements
### Hard requirements (must have)
| # | Requirement | Type | Evidence in posting |
|---|-------------|------|---------------------|
| 1 | ... | degree / years / skill / language / work-auth / location / certification | "quoted words" |

### Soft requirements (preferred)
| # | Requirement | Type |

### ATS keywords (exact strings)
Hard skills: ...
Tools / stack: ...
Methods / concepts: ...
Soft skills: ...
Job-title variants: ...

### Red flags / ambiguities
- <contradictions, vague seniority, unpaid test tasks, location restrictions, etc.>
```

## Hard vs soft classification
- **Hard:** "required", "must", "minimum", "you have", a stated number of years, a degree, a legal or location constraint, a mandatory language.
- **Soft:** "nice to have", "a plus", "bonus", "ideally", "familiarity with".
- A skill listed only in the tech-stack paragraph and not under requirements is **soft**, unless repeated in the responsibilities.
- If unsure, mark as hard and note "ambiguous".

## Rules
- Never invent requirements that are not on the page.
- Record work-authorization, country, timezone and language constraints explicitly; the eligibility assessor depends on them.
- Keep the posting's language; do not translate.
- Report to the user in one line: title, company, location, and the number of hard requirements found.
