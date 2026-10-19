---
name: master-profile
description: Mohamed Yassine Khiari's single source of truth (the master profile) containing every verified fact, project, skill and metric. Read this before writing any CV, cover letter, LinkedIn text or eligibility verdict. Never invent anything that is not here.
---

# Master Profile: Mohamed Yassine Khiari

This file is the **only** source of facts about the candidate. Every CV, cover letter, LinkedIn text and eligibility verdict must be built from it.

## Absolute rules
1. **Never fabricate.** No invented employers, titles, dates, degrees, skills, metrics, certifications or tools.
2. **Fields marked `TODO` are unknown.** Do not fill them with guesses. If a job needs a TODO fact, ask the user, or leave it out and flag it.
3. **Metrics marked `[ESTIMATE]` or `[CONFIRM]`** must be confirmed by the user before appearing in a final document.
4. Add new verified facts through the `master-profile-builder` skill, never by editing silently during another task.
5. Tailoring means **selecting and re-ordering** facts from this file, never adding to it.
6. Do not copy unproven adjectives from old CVs (for example "scalable", "production-grade") into new documents unless section 5 backs them with facts.

## 1. Identity and contact
- **Name:** Mohamed Yassine Khiari
- **Location:** Hammam-Lif, Tunisia
- **Email:** khiarimohamedyassine@gmail.com
- **Phone:** +216 53 717 713
- **LinkedIn:** https://www.linkedin.com/in/yassine-khiarii/
- **GitHub:** github.com/Yassinekh17
- **Portfolio:** https://yassinekh-two.vercel.app/
- **Work authorization / relocation / remote:** Remote from Tunisia. TODO (relocation and visas held not yet stated; confirm before a job requires it)
- **Languages spoken:** Arabic (native), French (fluent), English (fluent)
- **Availability / notice period:** Immediately available (no notice period)
- **Current CV headline (old CV):** Software Engineer | Full Stack & AI

## 2. Headline and summary seeds
- **Core identity:** Software engineer (full stack and AI) who builds web and mobile platforms with AI features, from database to deployed app. Engineering degree at ESPRIT completing Oct 2026.
- **Primary stack:** Flutter / Dart (web and mobile), Node.js, Express, MongoDB Atlas, REST APIs, JWT auth, Vercel deployments.
- **Secondary:** TypeScript, React, Next.js, Angular, Spring Boot, Python, SQL (MySQL), Docker, WordPress.
- **AI/LLM work:** RAG chatbot, CV analyzer agent, tool-calling agent with user confirmation (LLaMA via Groq), NL2Query exploration.
- **Strongest proof points** (all verified, see sections 4 and 5):
  - Talent Manager + Talent Companion at Telnet (Flutter Web app for HR, Flutter mobile app for engineers, shared Node.js/MongoDB backend, three AI agents)
  - Defendr: Next.js/React/TypeScript e-sports tournament dashboard
  - CodeBridge: public VS Code extension (TypeScript, React, ACP)

### Positioning options (pick ONE per job, never mix claims)
| Positioning | Headline example | Target titles / search keywords | Lead with |
|---|---|---|---|
| Full-stack engineer | Full-Stack Engineer \| Node.js, React, Flutter, MongoDB | Full-Stack Developer, Software Engineer, Backend Developer (Node.js), Web Developer | Talent Manager backend and dashboards, Defendr (Next.js), REST design |
| AI-enabled full-stack engineer | Full-Stack Engineer \| Node.js, RAG, LLM Agents | AI Engineer, LLM Application Developer, GenAI Developer, Full-Stack AI Engineer | RAG assistant, CV analyzer, tool-calling agent with user confirmation |
| Mobile / cross-platform engineer | Mobile Developer \| Flutter, Dart, REST APIs | Flutter Developer, Mobile Developer, Cross-Platform Developer | Talent Companion, geolocation attendance, Windows build for CTO demo |
| Frontend / TypeScript engineer | Software Engineer \| TypeScript, React, Next.js | Frontend Engineer, React Developer, TypeScript Developer, Developer Tools Engineer | Defendr, CodeBridge, Talent Manager UI |
| Java / enterprise (use only if the job asks) | Software Engineer \| Spring Boot, Angular | Java Developer, Spring Boot Developer | Academic projects only (section 5); flag as lighter evidence |

### Summary seed (rewrite per job, 45 words max, verified facts only)
- Full-stack: "Full-stack engineer who built Talent Manager at Telnet: a Flutter web app for HR and a mobile app for engineers on a shared Node.js/MongoDB backend, with Slack, GitHub and Cloudinary integrations. Also built a React/TypeScript e-sports dashboard. Seeking to bring end-to-end ownership to <Company>."
- AI-enabled: "Full-stack engineer who integrated three LLaMA/Groq agents into an HR platform at Telnet: a RAG assistant, a CV analyzer and a tool-calling agent that acts on business data with user confirmation. Strong in Node.js and Flutter. Seeking to build practical LLM features at <Company>."
- Mobile: "Flutter developer who built Talent Companion, a mobile app with geolocation attendance, HR requests, a Slack/GitHub-synced team feed, points and badges, and AI-generated daily quizzes, backed by a Node.js API. Seeking to build cross-platform apps at <Company>."

### Honesty notes for the agent
- Talent Manager and Talent Companion were built at Telnet; do not claim real user counts, "production at scale" or revenue unless confirmed in section 5.
- React Native and Expo are **not** evidenced. Do not use them in any positioning or skills line unless the user confirms a project.
- Do not use a positioning whose stack the job needs but section 6 marks as not evidenced.

## 3. Education
- **Engineering Degree in Computer Science, ESPRIT** (École Supérieure Privée d'Ingénierie et de Technologies), Tunisia. Sep 2023 to **Oct 2026**.
  - Specialization: Software Engineering (stated earlier by the user; the old CV says only "Computer Science", so use "Computer Science" on CVs unless the user confirms)
  - End-of-study project: Talent Manager at Telnet (see section 4.1), with a written end-of-study report in progress.
- **Bachelor's Degree in Information Systems Development, ISET Rades**, Tunisia. Sep 2020 to Jul 2023.
- Earlier education (high school / baccalaureate): TODO (include only if a job requires it)

## 4. Experience
Cumulative history is about 2 years of short engagements plus the current Telnet role (roughly 25 months of non-overlapping time). Employment type for every role (full-time, internship, freelance, end-of-study project) is **TODO**: the old CV lists all of them as "Developer". Do not write "internship" or "full-time" until the user confirms. Never claim 5+ years of professional experience.

### 4.1 Full Stack Developer, Telnet (Feb 2026 to Oct 2026)
- **Location:** Tunisia
- **Type:** TODO (also the end-of-study project at ESPRIT)
- **Verified facts:**
  - Designed and developed Talent Manager, a centralized HR platform: a Flutter Web application for HR teams and Talent Companion, a mobile app for engineers, sharing a Node.js/Express and MongoDB backend.
  - Built HR modules: recruitment and candidate tracking, skill management, 9-Box performance evaluation, objectives, employee reviews, HR statistics, interactive dashboards.
  - Built mobile features: geolocation-based attendance, HR requests, team feed synchronized with Slack and GitHub, points and badges, AI-generated daily quizzes.
  - Integrated three AI agents powered by LLaMA via Groq: an HR conversational assistant using RAG, an automated CV analyzer, and an agent that executes business actions through tool calling with user confirmation.
  - Integrated Slack API, GitHub, Cloudinary and Nodemailer, with JWT authentication and role-based access control.
  - Deployed the backend on Vercel; RESTful APIs connect the web and mobile apps.
- See Project 1 and 2 for more detail.

### 4.2 Full Stack Developer, Defendr (Jul 2025 to Sep 2025)
- **Type:** TODO (likely a summer engagement; confirm internship / freelance / contract)
- **Stack:** Next.js, React, TypeScript, REST APIs
- **Verified facts:**
  - Developed a Next.js dashboard for managing e-sports tournaments (tournament organization and administrative workflows).
  - Built responsive, reusable UI components with React and TypeScript.
  - Integrated REST APIs and implemented real-time updates to keep tournament information synchronized.
  - Applied React Hooks and frontend optimization techniques for performance and responsiveness.
  - Collaborated on frontend-to-backend integration to keep data flows reliable.
  - Metrics: TODO (number of tournaments, users, screens, performance gains)

### 4.3 Blockchain / Full Stack Developer, Slide (Jan 2023 to Jun 2023)
- **Type:** TODO
- **Stack:** MERN (MongoDB, Express, React, Node.js), Git, Docker
- **Verified facts:**
  - Designed and developed a Bitcoin cryptocurrency wallet (frontend, backend, database).
  - Implemented an automated Dollar-Cost Averaging (DCA) strategy for recurring Bitcoin purchases.
  - Built authentication and secure transaction workflows to protect accounts and financial operations.
  - Designed RESTful backend services integrated with the wallet interface.
  - Used Git and Docker for environments, version control and deployment; followed Agile practices.
  - Metrics: TODO

### 4.4 Full Stack Developer, Tetra (Jan 2022 to Jul 2022)
- **Type:** TODO
- **Stack:** React, Laravel, Git, CI/CD
- **Verified facts:**
  - Developed and maintained web applications with React and Laravel.
  - Improved frontend and backend performance and reliability.
  - Worked with Git and CI/CD pipelines in team workflows.
  - Metrics: TODO

### 4.5 Full Stack Developer, Swiftsaler (Feb 2022 to Mar 2022)
- **Type:** TODO (overlaps with Tetra; short engagement)
- **Stack:** Symfony, HTML, CSS, JavaScript
- **Verified facts:** Developed an e-commerce platform; optimized website performance and SEO.

### 4.6 WordPress Developer, ConceptMedia (Feb 2021 to Mar 2021)
- **Type:** TODO
- **Verified facts:** Developed and customized client e-commerce websites in WordPress; managed content, themes and plugins.
- Use only for WordPress or web-basics roles; omit from most CVs.

### 4.7 Webmaster / Developer, Forum Tunisien pour l'Éducation (FTE / FCIERI)
- **Not on the old CV.** Include only if the user confirms it should be added.
- **Type:** TODO (freelance / part-time / volunteer)
- **Dates:** TODO
- **Verified facts:**
  - Built WordPress HTML/CSS pages for FCIERI events: registration-fee tables with interactive cards, a sponsorship dossier page, pre-forum and workshop (atelier) event pages with speaker modal popups.
  - Diagnosed and fixed WPBakery `onclick` blocking issues using `data-key` attributes and `DOMContentLoaded` event binding.
  - Long-running WordPress work: HTML tables, CSS styling, plugin customization.
  - Metrics: TODO (pages shipped, visitors, registrations)

## 5. Projects

### Project 1: Talent Manager (HR talent management platform, Telnet)
- **One line:** Centralized HR talent management platform (Flutter Web) covering recruitment, performance reviews, skills and AI assistance, paired with the Talent Companion mobile app.
- **Stack:** Flutter Web, Node.js, Express, MongoDB Atlas, Vercel, Cloudinary, Nodemailer (Gmail), JWT with role-based access control, Multer, Slack API, GitHub, Groq (LLaMA).
- **Verified achievements (use as bullet material):**
  - Designed the data model: Engineer, User, Review (goals and satisfaction), Besoin, Candidat, Team, Event, News, plus chain Client → Project → Job → JobLevel → Engineer.
  - Built a goals module with a dedicated endpoint chain (JWT → Engineer → Review).
  - Built an HR statistics endpoint with year filter returning hires, departures, turnover rate, gender split, age pyramid and department breakdown; plus satisfaction stats by month, age and gender.
  - Built a skills comparison system matching required skills against actual skills with a compound unique index and sync function.
  - Built open-positions, unassigned-engineers and team-member management endpoints, and a candidate-to-engineer conversion endpoint.
  - Built an account-creation system that generates a random password and sends a styled HTML welcome email.
  - Built a recruitment dashboard (KPI cards, fl_chart visualizations, interactive modals) and a 9-Box Talent Grid with bubble chart.
  - Integrated three AI agents (LLaMA via Groq): RAG HR assistant, CV analyzer with PDF parsing, and a tool-calling agent that performs real MongoDB write operations after user confirmation.
  - Packaged the Flutter app as a Windows .exe for a CTO demo, resolving Visual Studio toolchain issues.
- **Metrics:** TODO (users, number of endpoints, response times, hours saved). Do not invent. Verified count: 3 AI agents.

### Project 2: Talent Companion (mobile app for engineers, part of the same Telnet project)
- **Status:** Finished.
- **Stack:** Flutter, shared Node.js/Express/MongoDB backend.
- **Verified features:** profile management, geolocation-based attendance, HR requests, team feed synchronized with Slack and GitHub, points and badges, AI-generated daily quizzes, AI chatbot, review goals, peer recognition.
- **Skills evaluation dashboard:** converts an Excel skills matrix (27 skills, 7 categories, scored 0 to 4) into radar charts, stacked bars and a 9-Box grid with engineer avatars.

### Project 3: CodeBridge (VS Code extension)
- **One line:** VS Code extension that gives OpenCode a native chat sidebar, so developers can use it without the terminal.
- **Stack:** TypeScript (esbuild), React + Vite webview, communicates with OpenCode over ACP (stdio).
- **Link:** github.com/Yassinekh17/ExtensionVscodeOpencode (public)
- **Good for:** code samples, tooling/DX roles, TypeScript roles. Not on the old CV; add it to new ones when relevant.

### Academic projects (ESPRIT / ISET; from the old CV)
- **Intelligent Medical Application** (Spring Boot, Angular, JWT, AI): secure authentication, AI-assisted symptom analysis, appointment management.
- **Khotwa, E-Learning Platform** (Angular, Spring Boot): course, user and e-learning activity management.
- **Petty, Pet Adoption Mobile Application** (React.js, Express.js): swipe-based ("Tinder-like") app for discovering and interacting with adoptable pets. Confirm whether it is a React Native / mobile web app before calling it a "mobile application" in technical terms.
- **Tuniimmo, Tunisian Real Estate Platform** (Angular, Express.js): search, browse and publish listings; role-based features for standard and premium users; premium listings prioritized in search results; 360-degree viewing for premium listings.
- Links and dates: TODO

### Other
- Python algorithm exercises (arrays, matrix multiplication, traversal problems).
- Exploration of AI agent architecture (n8n workflows, level-3 agentic RAG, specialized agents for goal generation, review writing, skill-gap analysis).

## 6. Skills inventory (with honest level)
Levels in bold are from project evidence. Skills marked "CV-listed" appear on the old CV but have little or no project evidence in this file; use them only in the skills block, never as a lead claim, and ask the user for a project before relying on them.

| Skill | Level | Evidence |
|-------|-------|----------|
| Flutter / Dart | Advanced | Talent Manager web + Talent Companion mobile |
| Node.js / Express | Advanced | Talent Manager backend, Slide, academic projects |
| MongoDB (Atlas, aggregation, indexes) | Advanced | HR stats, skills compound index, Slide (MERN) |
| REST API design, JWT auth, role-based access | Advanced | Talent Manager, Slide |
| LLM apps (RAG, tool-calling, agents) | Intermediate to advanced | Three Groq/LLaMA agents at Telnet |
| React / TypeScript / Next.js | Intermediate to advanced | Defendr, Tetra, Slide, CodeBridge |
| Vite | Intermediate | CodeBridge webview |
| Angular | Intermediate | Medical app, Khotwa, Tuniimmo (academic) |
| Spring Boot / Java | Intermediate (academic) | Medical app, Khotwa |
| Git / GitHub | Intermediate | Slide, Tetra, CodeBridge |
| Docker | Intermediate | Slide; user confirmed able to defend (2026-10-19) |
| CI/CD | Basic | Tetra (level TODO) |
| SQL / MySQL | Intermediate | User confirmed (2026-10-19); old CV skills + databases |
| Python | Intermediate | Algorithms, TODO other uses |
| Vercel deployment | Intermediate | Talent Manager |
| Cloudinary, Nodemailer, Multer, Slack API | Intermediate | Talent Manager |
| Laravel, Symfony | Basic | Tetra, Swiftsaler (2022); user confirmed (2026-10-19) |
| WordPress (HTML/CSS/JS, WPBakery) | Intermediate | FTE/FCIERI, ConceptMedia |
| .NET, C# | Intermediate | User confirmed able to defend (2026-10-19); skills-listed, no project named |
| Machine Learning | CV-listed | No project evidence (TODO) |
| Power BI, Talend (Data & ETL) | Intermediate | User confirmed able to defend (2026-10-19); skills-listed, no project named |
| Blockchain / Bitcoin wallet, DCA | Basic to intermediate | Slide |
| React Native, Expo | **Not evidenced.** Do not claim. | |
| Go, GraphQL, GCP | **Not evidenced.** Do not claim. | |

> Keep "Not evidenced" honest. If a job requires one of these, the eligibility assessor must treat it as a gap. For "CV-listed" skills, treat as PARTIAL, never MET, until the user supplies a project.

## 7. Certifications, awards, publications
- None stated. User confirmed the old CV is accurate as written and lists no certifications (2026-10-19).

## 8. Preferences for applications
- Target roles: full-stack, AI/LLM engineer, mobile
- Target regions: remote worldwide / Tunisia / EU / Gulf
- Salary expectations: TODO
- Do not apply to: TODO (industries, company types)

## 9. Pending items the user must fill
Updated 2026-10-19 after importing the old CV (user confirmed all jobs are real and the CV is accurate as written). Resolved: all six jobs imported; CV-listed skills Docker, SQL/MySQL, .NET/C#, Laravel/Symfony, Power BI/Talend confirmed as defensible; certifications = none.
Still open (highest impact first):
1. Employment type for each role (full-time, internship, freelance, end-of-study project); decides how years of experience are counted.
2. Work authorization: relocation openness and visas held.
3. One metric per role or project (users, screens, endpoints, performance, hours saved).
4. Evidence for remaining CV-listed skills: Machine Learning; Docker and CI/CD levels.
5. Whether FTE/FCIERI webmaster work and CodeBridge should be added to the CV, with FTE dates.
6. Salary expectations, high-school education (optional).
The orchestrator must warn the user when a chosen job depends on a TODO field.
