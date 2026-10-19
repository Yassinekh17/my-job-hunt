---
name: resume-ats-optimizer
description: Audit a CV against a job posting for ATS compatibility and keyword coverage, score it, and fix parsing risks and keyword gaps without adding unverified claims. Use after the CV text is assembled and again after formatting.
---

# Resume ATS Optimizer

Makes sure applicant tracking systems parse the CV correctly and rank it well for the posting.

## Inputs
`jobs/<slug>/cv.md` (or final .docx/.pdf), `jobs/<slug>/job.md`, `master-profile`.

## Part A: Parse safety (pass/fail)
Check and fix:
1. **Layout:** single column, no tables for content, no text boxes, no headers/footers holding key info, no images or icons carrying text.
2. **Section titles:** standard names only: Summary, Experience (or Work Experience), Projects, Education, Skills, Certifications, Languages.
3. **Contact info:** in the body (not in the Word header), as plain text. Include a professional email and a working LinkedIn URL.
4. **Dates:** consistent `Mon YYYY - Mon YYYY` format on every entry.
5. **Fonts:** a standard font (Calibri, Arial, Helvetica, Georgia, Times New Roman); body 10 to 12 pt; no decorative fonts.
6. **Bullets:** standard round bullets only.
7. **File:** `.docx` or text-based `.pdf` (never a scanned image); file name `Firstname_Lastname_CompanyOrRole_CV.pdf`.
8. **Special characters:** avoid emoji, arrows, fancy dashes inside words, ligature-breaking fonts.
9. **Links:** show the readable URL text, not only a hyperlink on a word.
10. **Length:** 1 page for under 10 years of experience.

## Part B: Keyword coverage
1. Take the ATS keywords from `job.md` (hard skills, tools, methods, titles, soft skills).
2. For each keyword, check presence in the CV: exact match, accepted variant (for example "REST API" vs "RESTful APIs"), or missing.
3. **Coverage score** = matched hard-skill keywords / total hard-skill keywords the candidate truly has. Soft-skill keywords count half.
4. For missing keywords:
   - If the profile supports it: add it where it is true (a bullet, the skills line, the summary).
   - If the profile does not: list it as a **gap** and do **not** add it.
5. Place keywords where ATS weights them: job title line, summary, skills block, and in context inside bullets.
6. Include both the acronym and the full term once when the posting uses both.
7. **Density:** no keyword more than 3 times in the whole CV.

## Part C: Content quality
- Banned buzzwords: team player, hard-working, results-driven, passionate, dynamic, go-getter, synergy, think outside the box, detail-oriented (unless shown by evidence).
- Banned bullet starters: "Responsible for", "Worked on", "Helped", "Assisted with", "Involved in".
- Each bullet starts with a strong verb, includes a tool or method, and carries a result where one is verified.
- Job-title alignment: the headline should match or mirror the posting title if it is true for the candidate.

## Scoring (report to the user)
| Area | Weight |
|------|-------:|
| Parse safety | 30 |
| Hard-skill keyword coverage | 35 |
| Title/summary alignment | 10 |
| Bullet quality and metrics | 15 |
| Length and format | 10 |

Pass mark for sending: **85+**. Below 85, fix and rescore (max 2 iterations).

## Output
```markdown
## ATS report: <Job>
Score: <n>/100   (Parse <a>/30, Keywords <b>/35, Alignment <c>/10, Bullets <d>/15, Format <e>/10)
Matched keywords: ...
Missing but true (added): ...
Missing and NOT true (gaps, not added): ...
Fixes applied: ...
Remaining risks: ...
```
Return the improved `cv.md` along with the report.

## Hard rule
Optimization never overrides honesty. If hitting 85 would require a false claim, report the real score and the gap.
