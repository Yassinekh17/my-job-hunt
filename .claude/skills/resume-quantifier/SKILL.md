---
name: resume-quantifier
description: Turn vague resume bullets into measurable, truthful achievement statements using only verified numbers from the master profile or numbers the user confirms. Use after drafting bullets and before ATS optimization.
---

# Resume Quantifier

Strengthens bullets with numbers **without fabricating anything**. A fake metric is worse than none.

## The honesty rule
A number may appear in a CV only if:
1. It is in the master profile as a verified fact, or
2. It is directly countable from the project itself (endpoints, collections, screens, features, tables, skills evaluated), or
3. The user confirmed it in this conversation.

Anything else is tagged `[ESTIMATE]` and shown to the user for approval; never auto-include it.

## Procedure

1. **Scan each bullet** for missing scale, speed, quality, cost or adoption. Typical weak patterns: "responsible for", "worked on", "developed a feature", "improved performance".
2. **Find the numbers in the profile first.** Examples already verifiable for Yassine's work:
   - Skills matrix: 27 skills across 7 categories scored 0 to 4
   - Data entities: 8+ core collections plus the Client → Project → Job → JobLevel → Engineer chain
   - Mobile app: 9 listed feature areas (profile, points, AI chatbot, clocking in, review goals, HR requests, team feed, peer recognition, daily quiz)
   - Stats outputs: hires, departures, turnover, gender, age pyramid, departments (6 dimensions)
   - Deliverables: web app + mobile app + Windows build for CTO demo
3. **Pick the right metric type** for the bullet:
   | Type | Examples |
   |------|----------|
   | Scale | users, records, endpoints, screens, services, requests/day |
   | Speed | load time, response time, build time, time-to-hire, manual hours removed |
   | Quality | error rate, test coverage, bugs closed, uptime |
   | Money/efficiency | cost saved, hours saved per week, licences replaced |
   | Reach | audiences, events, registrations, visitors |
   | Scope | team size, stakeholders, countries, modules |
4. **Ask when missing.** Produce a short question list for the user, grouped by bullet, with answer options such as ranges ("under 50 / 50-200 / 200+ users"). Offer proxies if exact numbers are unknown.
5. **Rewrite** each bullet in the form: `Action verb + object + how (tool) + result (number + unit + baseline if known)`.
   - Weak: "Worked on HR statistics for the dashboard."
   - Strong (numbers confirmed): "Built a year-filtered HR statistics API (hires, departures, turnover, gender, age pyramid, department split) in Node.js/MongoDB, feeding a KPI dashboard used by HR."
   - If no real number exists, strengthen with **scope and specificity** instead of a fake number (list the real dimensions).
6. **Use ranges and wording honestly:** "~", "over", "more than" only when the user confirmed the floor. Never round up.
7. **Label baselines:** "reduced from X to Y" only when both are known.

## Output
A table of before/after per bullet:
| Original | Quantified | Source of number | Needs user confirmation |
and a list of questions for the user. Bullets with unconfirmed numbers stay out of the final CV.

## Do not
- Invent percentages ("improved performance by 40%") without evidence.
- Claim team leadership, user counts or revenue that are not in the profile.
- Turn a student project into "production at scale" language.
