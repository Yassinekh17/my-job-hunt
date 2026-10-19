---
name: master-profile-builder
description: Interview the user and update the master profile with verified facts, quantified achievements and resolved TODOs. Use when the profile has gaps, when new projects or jobs are added, or when a CV needs facts that are missing.
---

# Master Profile Builder

Keeps `master-profile` complete, accurate and quantified. The master profile is only as good as what this skill collects.

## When to use
- First-time setup, to resolve every `TODO` in the master profile.
- A new job, project, degree, certification or skill appears.
- Another skill reports a missing fact (for example, a job needs "years of Git" and the profile has none).
- The user pastes an old CV, LinkedIn export or portfolio text to import.

## Inputs it can ingest
Old CV (PDF/DOCX; use the pdf or docx skill to read it), LinkedIn export, GitHub README files, project reports (for example the end-of-study report), pasted notes.

## Procedure

1. **Read the current master profile.** List every TODO, every `[ESTIMATE]`, and every role/project with no metric.
2. **Import first, ask second.** If the user gave documents, extract facts from them before asking questions. Never make the user retype what they already wrote.
3. **Interview in short rounds** (max 5 questions per round, grouped by topic). Use AskUserQuestion for multiple-choice items, plain text for open ones. Order:
   1. Identity and contact, work authorization, languages, availability
   2. Education details (specialization, dates, grades if strong)
   3. Each experience: exact title, employer, dates, team size, what they owned
   4. Each project: users, scale, outcome, links
   5. Skills with honest level and last-used date
   6. Certifications, awards, publications, talks
   7. Target roles, regions, salary
4. **For every responsibility, extract a metric** using the STAR-M prompt:
   - What was the situation or problem?
   - What exactly did you do (verb, tool, scope)?
   - What changed? (time saved, users, records, speed, cost, error rate, adoption, size)
   - If the user does not know the number: ask for a **defensible range** or a proxy (count of endpoints, tables, screens, users, requests). Mark estimates `[ESTIMATE]` and ask the user to confirm them.
5. **Write the update** into the master profile using Edit. Rules:
   - Only facts the user stated or documents show. Tag unverifiable numbers `[ESTIMATE]`.
   - Keep the existing structure; add new roles/projects in reverse-chronological order.
   - Use past-tense, verb-led, factual wording. No marketing language in the master profile.
   - Never delete existing facts without the user's explicit instruction.
6. **Show a diff-style summary** (added / changed / still TODO) in under 10 lines.
7. **Ask the next most valuable question** only if TODOs remain that block applications.

## Quality bar for each profile entry
- Employer, role, dates (month/year), location
- 3 to 6 achievement facts per role, each with action + object + result
- At least one metric per role or project, or an explicit "no metric available"
- Tools listed exactly as they would appear in a job ad (for example "Node.js", not "node")
- Links (GitHub, live demo) where public

## Hard stops
- Do not store government IDs, passport numbers, national ID, date of birth, or full home address. City and country are enough.
- Do not guess dates, titles or numbers. Ask.
- If the user says a fact is confidential (client names, internal numbers), store a generalized version and mark it `[CONFIDENTIAL: generalize]`.
