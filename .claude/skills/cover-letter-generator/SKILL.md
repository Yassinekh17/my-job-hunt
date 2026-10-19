---
name: cover-letter-generator
description: Write a tailored, honest, one-page cover letter for a specific job using the master profile, job posting and eligibility report. Use when the user asks for a cover letter, or when the application asks for one or for short answer questions.
---

# Cover Letter Generator

A cover letter proves **fit and motivation** in under 300 words. It complements the CV; it never repeats it.

## Inputs
`jobs/<slug>/job.md`, eligibility report (strengths and gaps), tailoring plan, `master-profile`.

## Procedure

1. **Research the company** quickly with WebSearch (product, mission, recent news, tech stack, values) from official sources; pick 1 specific, true detail to reference. If nothing reliable is found, skip it rather than invent.
2. **Find the addressee.** Use the hiring manager's name only if the posting or LinkedIn gives it; otherwise "Dear <Company> Hiring Team,". Never "To whom it may concern".
3. **Pick the 2 strongest proofs** from the master profile that match the posting's top screening criteria (usually one project and one skill/result).
4. **Handle gaps honestly** (from the eligibility report):
   - Minor gap: do not mention it.
   - Significant gap: one sentence acknowledging it plus real evidence of learning or adjacent work.
   - Never claim experience that is not in the profile.
5. **Write** with this structure (250 to 300 words, 3 to 4 short paragraphs):
   - **Opening (2 to 3 sentences):** role applied for, a specific hook about the company or product, and your single best credential.
   - **Proof paragraph:** one concrete project/achievement with its stack and result, mapped to what the employer needs.
   - **Fit paragraph:** a second proof or skill, plus why this company/role (genuine, specific).
   - **Close (2 sentences):** availability, a clear call to action, thanks.
6. **Tone:** professional, direct, warm; first person; no clichés ("I am writing to apply", "I am a hard-working team player", "perfect fit"); no flattery; no repeating CV bullets.
7. **Language:** same as the posting; US spelling for US companies, British otherwise.
8. **Format:** one page, same header as the CV (name, contact), date, company, greeting, body, closing, name. Build the file with the `docx` skill (and a PDF through the `pdf` skill). Name it `Firstname_Lastname_<Company>_CoverLetter.pdf`.

## Application questions
If the application asks short questions (for example "why are you proud of this code sample?", "how did you hear about us?", "technical writing sample"), answer each in 80 to 150 words, specific, honest, drawn from the master profile (for example CodeBridge for code samples). Provide the answers in the chat as copy-ready text.

## Quality checklist (run before delivering)
- Names the exact role and company correctly
- One specific company detail that is true
- At least one number or concrete outcome (verified)
- No claim outside the master profile
- No sentence that could be pasted into another company's letter unchanged
- 250 to 300 words, one page

## Output
The letter text for review, plus the DOCX and PDF files via SendUserFile, plus a 2-line note on which gaps were handled and how.
