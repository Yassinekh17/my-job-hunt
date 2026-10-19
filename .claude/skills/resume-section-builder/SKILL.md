---
name: resume-section-builder
description: Write one CV section at a time (header, summary, experience, projects, education, skills, certifications, languages, volunteering) in correct ATS-friendly form from the tailoring plan. Use when building or rebuilding individual sections.
---

# Resume Section Builder

Builds each CV section to a fixed standard. Feed it the tailoring plan and master profile; it returns finished section text.

## Global rules (apply to every section)
- Source facts only from `master-profile`.
- Plain text structure: standard section titles, no tables for core content, no text boxes, no icons as content.
- Dates as `Mon YYYY - Mon YYYY` (or `Present`), consistent everywhere.
- Past tense for finished work, present tense for current roles.
- No first-person pronouns ("I", "my"), no filler ("responsible for", "worked on", "helped with").
- Acronyms: write full form once if the posting uses both (for example "Retrieval-Augmented Generation (RAG)").

## Sections

### 1. Header
Name (largest), headline (matches target title), then one line: City, Country | email | phone | LinkedIn | GitHub | portfolio.
- Email and phone as plain text, not images.
- Add "Open to remote" or relocation only if the profile states it.
- No photo, age, marital status unless the posting's country norm requires it and the user agrees.

### 2. Professional summary (2 to 3 lines, max 45 words)
Formula: `<Title/identity> with <strongest proof/scale> in <top 2 to 3 job-relevant skills>. <One notable achievement with a number>. <Target contribution to this employer>.`
- Student/recent grad: lead with the end-of-study project result, not with "motivated student".
- No adjectives that cannot be proven ("passionate", "hard-working", "results-driven").

### 3. Experience
Per role: `Job Title | Company | City, Country | Mon YYYY - Mon YYYY`, then 3 to 5 bullets (2 to 3 for roles older than 5 years).
Bullet formula: **Action verb + what you did (with tool) + measurable result/scale**.
- Most relevant bullet first.
- One line, max two lines on a page; around 15 to 30 words.
- Vary the opening verbs; never start two consecutive bullets with the same verb.
- Use `resume-quantifier` for numbers.

### 4. Projects (important for students and career-changers)
Per project: `Project name | Role | stack | link | Mon YYYY - Mon YYYY`, then 2 to 4 bullets.
- First bullet: what it is and who it is for, in one line.
- Remaining bullets: engineering decisions and outcomes, in job keywords.
- Include a public link only if it works.

### 5. Education
`Degree, Specialization | Institution | City, Country | Mon YYYY - Mon YYYY (or expected)`
- Add: end-of-study project title, relevant coursework only if it matches the posting, honors.
- Expected graduation uses "Expected Oct 2026" style if not yet awarded.

### 6. Skills
3 to 4 labelled lines, most relevant first:
`Languages: ... | Backend: ... | Frontend/Mobile: ... | Data/AI: ... | Tools/Cloud: ...`
- Exact posting spellings.
- Only skills with evidence in the profile and that the job values.
- No self-rated bars, stars or percentage levels.

### 7. Certifications / Awards / Publications
`Name | Issuer | Year`. Include only relevant ones; skip the section if empty.

### 8. Languages (human)
`Language (level)`, using CEFR or plain levels from the profile. Skip if not asked and not helpful.

### 9. Volunteering / Extracurricular
Only if it shows relevant skills or fills a gap (leadership, teaching, open source).

## Output
Return each section in Markdown with the exact heading names above, ready for `resume-build-writer` to assemble. Flag every fact that came from a `[ESTIMATE]` tag.
