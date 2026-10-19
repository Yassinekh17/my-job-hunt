---
name: linkedin-profile-optimizer
description: Rewrite LinkedIn headline, About, Experience, Projects and Skills so recruiters find and trust the profile, aligned with the master profile and target roles. Use when the user asks to improve LinkedIn or before a wave of applications.
---

# LinkedIn Profile Optimizer

Recruiters search LinkedIn by keyword before they read. This skill makes the profile findable and consistent with the CV.

## Inputs
`master-profile`, target roles (from the master profile preferences or the job posting), the user's current LinkedIn text if provided (paste or export; the built-in LinkedIn page is behind a login, so do not try to scrape it).

## Procedure

1. **Define the target:** 1 to 2 role titles and 10 to 15 search keywords drawn from 5 to 10 representative postings (use `web-to-markdown` on real postings if the user supplies links).
2. **Rewrite each section:**

### Headline (max 220 characters)
Formula: `Target role | key stack | proof or niche | optional open-to line`
Example: `Full-Stack Engineer | Node.js, Flutter, MongoDB | Built AI-powered HR platform (RAG, agents) | Open to remote roles`
- Lead with searchable titles and tools, not "Student at ...". Mention graduation only in Education.

### About (first 3 lines matter most, max about 2,000 characters)
Structure:
1. Hook (2 lines): who you are + what you build + for whom
2. What you do best (3 to 4 short lines or bullets): stack, domains, strengths with verified evidence
3. Proof (2 to 3 achievements with numbers from the master profile)
4. What you are looking for + how to contact
- First person, plain language, keywords woven in naturally; end with a call to action.

### Experience
Same facts as the CV, 3 to 5 bullets per role, plus a "Skills" tag line per role. Dates and titles must match the CV exactly.

### Projects / Featured
Add Talent Manager, Talent Companion and CodeBridge with link, 2-line description, stack, and visuals (screenshots, demo video). Pin the best 2 to 3 in Featured.

### Skills
List 30 to 50 relevant skills; pin the top 3 matching the target role. Order by search relevance; request endorsements for the top 5.

### Other
- Education with the end-of-study project
- Custom URL (`linkedin.com/in/firstname-lastname`)
- Professional photo, banner with stack or personal tagline
- Location set correctly; "Open to work" with only target titles and remote preference (recruiter-only visibility if the user prefers)
- Language, certifications, recommendations (ask 2 to 3 supervisors or teammates)

3. **Consistency check:** headline, titles, dates and numbers must match the CV and master profile. Flag mismatches.
4. **Weekly routine suggestions:** connect with recruiters and engineers at target companies, comment on posts, share one project update every 2 weeks.

## Output
A Markdown file `linkedin-optimized.md` with copy-ready text for each section, a keyword list, and a short checklist of manual actions the user must do in LinkedIn.

## Rules
- No unverified claims; same honesty rules as the CV.
- Do not promise ranking or visibility results.
- Never request or store the user's LinkedIn password; the user pastes content or applies the edits.
