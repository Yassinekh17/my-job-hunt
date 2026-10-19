---
name: job-application-orchestrator
description: Master workflow. When the user gives a job link (or pasted job text), run the full pipeline - fetch, assess eligibility, and if qualified produce a tailored ATS CV and cover letter; if not qualified, say so honestly. Use for any "make a CV/cover letter for this job" request.
---

# Job Application Orchestrator

One entry point for the whole system. The user gives a job link; the result is either a **tailored, ATS-ready CV (and cover letter)** or an **honest "you are not qualified enough, here is why"**.

## Skills it coordinates
1. `web-to-markdown`: job link to structured `job.md`
2. `master-profile` (+ `master-profile-builder` when facts are missing)
3. `job-eligibility-assessor`: go / no-go gate
4. `resume-tailor`: selection and keyword plan
5. `resume-section-builder` and `resume-quantifier`: sections and numbers
6. `resume-build-writer`: assemble `cv.md`
7. `resume-ats-optimizer`: audit and fix (pass mark 85)
8. `cv-design` and `resume-formatter`: DOCX and PDF
9. `cover-letter-generator`: letter and application answers
10. `linkedin-profile-optimizer`: only on request

Read each skill's SKILL.md before using it.

## Workflow

### Step 0: Intake
- Input: URL(s) or pasted text. Optional flags from the user: "CV only", "cover letter only", "assess only", "override" (apply even if not qualified).
- First reply: one sentence saying what is about to happen.
- Create a task list (TaskCreate) for the steps below and update it as you go.
- Check that the master profile has no blocking `TODO` for this job (contact info, name). If it does, ask the user once, in a single message, then continue.

### Step 1: Fetch and parse
Run `web-to-markdown`. If the page cannot be read, ask for pasted text and stop until it arrives.

### Step 2: Eligibility gate
Run `job-eligibility-assessor` and show the user the verdict block.
- **STRONG FIT / QUALIFIED:** continue automatically.
- **STRETCH:** tell the user the odds are low and what is missing; continue only if the user said "apply anyway" or "override"; if the user is not available, continue with an honest version and label it STRETCH in the summary.
- **NOT QUALIFIED:** stop. Do not produce a CV or letter. Give the plain verdict, the 1 to 3 blockers, how to become qualified, and 2 to 3 better-fit searches. Offer: "Say 'override' if you want me to write the most honest version anyway."
- **Missing information:** if the assessor finds more than 30% of hard requirements UNKNOWN, run `master-profile-builder` first.

### Step 3: Tailor
Run `resume-tailor` and save `tailoring-plan.md`.

### Step 4: Write
Run `resume-section-builder`, then `resume-quantifier` (collect any needed confirmations from the user in one batch), then `resume-build-writer` to produce `cv.md`.

### Step 5: Audit
Run `resume-ats-optimizer`. Iterate at most twice until the score is 85 or higher. If it cannot reach 85 without false claims, deliver the honest score and explain.

### Step 6: Format
Apply `cv-design`, then `resume-formatter` to produce DOCX + PDF. Verify the PDF text order and page count.

### Step 7: Cover letter (default yes for QUALIFIED and above, unless the user said "CV only")
Run `cover-letter-generator`. Answer application questions if the posting has them.

### Step 8: Final QA (mandatory)
- Every fact traced to the master profile; zero unconfirmed numbers
- Names, company and role spelled correctly in every file
- Same dates and titles across CV, letter, and LinkedIn
- Files open, one page, text selectable
- Folder `jobs/<slug>/` contains: `job.md`, `eligibility.md`, `tailoring-plan.md`, `cv.md`, CV `.docx` + `.pdf`, cover letter `.docx` + `.pdf`, `ats-report.md`

### Step 9: Deliver
Send the PDFs (and DOCX) with SendUserFile. The final message has, in this order:
1. Verdict and score (one line)
2. What was produced (file names)
3. ATS score and the 1 to 3 honest gaps
4. Anything the user must confirm or add (open TODOs, unconfirmed metrics)
5. Application tips: where to apply, who to contact, one follow-up suggestion

## Non-negotiable rules
1. **Never fabricate** experience, skills, dates, degrees, metrics or links. The master profile is the only source.
2. **Honesty beats optimization.** A lower ATS score with true content is the correct outcome.
3. **No silent overrides** of a NOT QUALIFIED verdict.
4. **One job at a time.** For several links, process each in its own folder and give a comparison table of verdicts at the end (job, score, verdict, recommendation).
5. **Privacy:** never store IDs, passwords, exact home address, or date of birth.
6. If the posting asks for something the system cannot do (video, assessment, portal form filling), say so and give the user clear manual steps.

## Quick commands the user can say
- "Assess only <link>": steps 1 to 2
- "CV for <link>": steps 1 to 6
- "Full pack for <link>": steps 1 to 9
- "Override, apply anyway <link>": skip the gate, label the output STRETCH or UNQUALIFIED in the summary
- "Update my profile": run `master-profile-builder`
- "Optimize my LinkedIn": run `linkedin-profile-optimizer`
