# Job application system

For any request involving a job link, CV, cover letter, LinkedIn or my profile,
use the skills in .claude/skills/. Read a skill's SKILL.md before using it.
My facts live ONLY in the master-profile skill. Never invent anything.

Start here for any job: job-application-orchestrator (it runs the others).

Skills:
- web-to-markdown: turns a job link into structured job.md
- job-eligibility-assessor: scores me vs the job; says "not qualified" when true
- master-profile: my verified facts (only source of truth)
- master-profile-builder: interviews me, imports my old CV, fills missing facts
- resume-tailor: picks what to emphasize for this job + keyword map
- resume-section-builder: writes each CV section
- resume-quantifier: adds real numbers, never fake ones
- resume-build-writer: assembles the full CV text
- resume-ats-optimizer: ATS audit, must reach 85+
- cv-design / resume-formatter: layout rules, produces DOCX + PDF
- cover-letter-generator: tailored letter + application answers
- linkedin-profile-optimizer: only when I ask

Rules: honesty over ATS score. If I'm not qualified, say so and stop unless I say "override".
Save everything in jobs/<company-role-date>/. Old CV and exports are in inputs/.