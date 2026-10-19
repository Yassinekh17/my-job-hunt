---
name: job-eligibility-assessor
description: Score the candidate against a parsed job posting and return an honest verdict (Strong fit, Qualified, Stretch, Not qualified) with gaps and a go/no-go decision. Run before writing any CV or cover letter for a job.
---

# Job Eligibility Assessor

The gatekeeper. It decides whether an application is worth sending and tells the user the truth if it is not.

## Inputs
- `jobs/<slug>/job.md` from `web-to-markdown` (hard requirements, soft requirements, keywords)
- The `master-profile` skill (the only source of candidate facts)

## Procedure

### Step 1: Hard-requirement gate
For every hard requirement in the job file, mark one of:
- **MET** (clear evidence in the master profile)
- **PARTIAL** (adjacent or transferable evidence)
- **NOT MET** (no evidence)
- **UNKNOWN** (master profile has a TODO for it; ask the user, do not assume)

Treat these as **knockout** requirements. Any NOT MET here means the verdict is capped at NOT QUALIFIED unless the user confirms the posting is flexible:
- Work authorization or country/timezone restriction the candidate cannot satisfy
- Mandatory language the candidate lacks
- Mandatory degree or license the candidate lacks
- A minimum years-of-experience requirement above the candidate's real experience by more than 50% (for example 5+ years asked, under 2.5 years held)
- A mandatory certification

### Step 2: Weighted score (0 to 100)
| Dimension | Weight | How to score |
|-----------|-------:|--------------|
| Core technical skills (hard-requirement skills) | 40 | MET = full, PARTIAL = half, NOT MET = 0, weighted by emphasis in the posting |
| Experience level and years | 20 | Compare real years and scope to stated seniority |
| Domain / responsibility overlap | 15 | Do past projects resemble the responsibilities? |
| Education and certifications | 10 | Required or preferred ones held |
| Soft requirements and nice-to-haves | 10 | Fraction covered |
| Location, language, logistics | 5 | Fit with the stated constraints |

Use only evidence from the master profile. Count years from real dates, never from skill claims. Student projects and end-of-study projects count as experience, but label them honestly (for example "end-of-study project", not "3 years of production experience").

### Step 3: Verdict
| Score | Knockouts failed? | Verdict | Action |
|-------|-------------------|---------|--------|
| 80 to 100 | none | **STRONG FIT** | Proceed; apply with confidence |
| 65 to 79 | none | **QUALIFIED** | Proceed; address gaps in the cover letter |
| 50 to 64 | none | **STRETCH** | Proceed only if the user insists; write honestly around gaps; warn about low odds |
| below 50 | any | **NOT QUALIFIED** | Do not generate application documents unless the user explicitly overrides |

If any knockout fails, the verdict is **NOT QUALIFIED** regardless of score.

### Step 4: Report (always this format)
```markdown
## Eligibility: <Job title> at <Company>
**Verdict: <STRONG FIT | QUALIFIED | STRETCH | NOT QUALIFIED>**   Score: <n>/100

**Why (3 bullets max)**
- ...

**Requirement check**
| Requirement | Status | Evidence from your profile |
|---|---|---|

**Gaps**
- <gap> - <severity: blocker / significant / minor> - <how to address: learn X, mention project Y, accept>

**Strongest angles to lead with**
- ...

**Recommendation:** <apply / apply with changes / do not apply / ask user first>
```

### Step 5: If NOT QUALIFIED
Say so plainly, kindly and specifically. Example: "You are not qualified enough for this one: it requires 5+ years of Go and PostgreSQL in production, and your profile shows neither." Then give:
1. The 1 to 3 real blockers
2. What would make the user qualified (skills, time, certification)
3. 2 to 3 better-matching role types or search keywords based on the master profile
4. A clear offer: "If you still want to apply, tell me and I will write the most honest version."

## Rules
- Never inflate the score to be nice. Never deflate it to be safe.
- Never treat a keyword as MET without a project or job in the master profile that shows it.
- If more than 30% of hard requirements are UNKNOWN, stop and run `master-profile-builder` first.
- Always list "Go, GraphQL, GCP, Docker, SQL" style gaps explicitly when the posting asks for them and the profile marks them as not evidenced.
- Salary band, company prestige and remote status never raise the score.
