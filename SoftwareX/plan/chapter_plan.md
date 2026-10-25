# REC — SoftwareX Chapter Plan + INSIGHT Collection (in progress)

ARS `plan` mode, started 23 October 2026. All claims below are in the author's words or were explicitly confirmed by the author.

## Configuration

| Item | Decision |
|---|---|
| Journal | SoftwareX, Original Software Publication (5 template sections) |
| Licence | AGPL-3.0-or-later (CC BY-NC rejected: not on SoftwareX's approved list) |
| Release | v1.0.0, DOI 10.5281/zenodo.23594648 (all versions: 10.5281/zenodo.23594647) |
| Submission | After June 2027, with all second-semester results |

## Thesis (confirmed)

"REC es una herramienta que permite gamificar cuestionarios adaptándolos a las necesidades del profesor, asignatura y estudiantes; no solo ayuda a analizar la evolución de los estudiantes, sino que también publica cifrados los cuestionarios, sin cuentas ni servidores."

- Main difference (author's words): "El análisis de los datos y que está en manos del profesor, no proveedor", with REC's analysis tool (speed × accuracy map, ideas for the next class).
- Point-on-image questions and extra time are features, **not** exclusive.
  - For extra time, what is distinctive is *how* it is granted: personal codes, no accounts.

## Section 1 — Motivation and significance ✅ confirmed (~550–650 words; drafted in LaTeX)

- **Hook:** participation is "muy explotada". REC goes "un paso más": real progress from per-question interactions, with the data held by the teacher.
- **Origin:**
  - Kahoot limited players per game in 2019 (~10) [verify].
  - That made it unusable in FTPD (~150 students), so the quizzes moved to Moodle.
  - Moodle has no speed-based ranking, so the scores were computed in a manual spreadsheet.
  - Cost: ~15–30 min per quiz, 13 quizzes per semester in Animación (~3–6.5 h).
- **Courses:**
  - *Herramientas Multimedia y Animación* = *Animación y Nuevas Tecnologías en Publicidad*, same content and assessment. Origin of the 2018 paper.
  - J. C. Collado Machuca only helped create the Excel tool and had no role in the course. He is not mentioned in REC.
- **Two uses:**
  - Graded continuous assessment (Animación, 20–30 students).
  - Ungraded diagnosis + attendance (FTPD, ~150 students; 3 quizzes; +0.1 for participation).
- **What REC records:**
  - One xAPI statement per question: response, correctness, time, time limit, topic, position.
  - Plus attempted/completed statements.
- **Privacy, precise wording:**
  - Questions are published only encrypted (AES-GCM 256).
  - Unencrypted questions, passwords and results never pass through a REC server.
  - No student accounts or database.
  - Not encrypted: the teacher's project/IndexedDB and the students' results file.
  - Google Fonts (and YouTube/Vimeo when videos are used) are third-party requests.
- **REC → Aspa workflow:** goes in Impact, citing Aspa, which is published first.

## Positioning decisions (23 Oct 2026, after the verified search — see comparison_table.md)

- **Kahoot! limit:** corrected to 50 players for higher education (Nov 2019) and 10 (Feb 2021). Cited from archived help pages.
- **No accounts, practice mode, point-on-image, extra time:** described as REC features in Section 2, not as differentiators.
- **REC's position:**
  - The combination: static, serverless, open source.
  - Moodle XML import outside Moodle.
  - A per-student xAPI file.
  - Built-in speed × accuracy and retention analysis (Heckler & Scaife 2015; Liang 2024).
- **Ticket (author's wording):**
  - Contests are accessed with a password, and a verification code lets the studio detect modified tickets.
  - Section 2 states the limit: recomputing the code in the browser is not detected.
- **How REC is used in class (author's words):**
  - Everyone plays at the same time after the lecture, on any device; the password is shown or said; nothing is projected.
  - The teacher supervises and answers questions.
  - Students upload the ticket file (code, interactions, result) to the virtual campus.
  - The teacher builds and publishes the ranking after the session.
  - It is not a synchronous multiplayer game.
- **Related work and Table 2:** drafted in LaTeX (Section 1).

## Section 2 — Software description ✅ drafted in LaTeX (24 Oct 2026)

- **No libraries:** "para que no se tenga que saber programar y no haya que instalar nada".
- **Moodle XML import:** so that teachers with existing quizzes can use REC easily. Future work: import formats from other tools.
- **Scoring:**
  - Linear from max to min (default 1000 → 500), × fraction correct for partly correct answers.
  - The 500 floor rewards slow correct answers, given time pressure (Wang & Tahir 2020).
  - Streaks are motivation only; they add no points.
- **Extra time:** personal code; time limit × (1 + pct/100).
- **Analysis:**
  - Each answer is compared with the question's median time, giving 4 categories.
  - A question is flagged as a possible misconception when ≥30% answered fast and wrong (Heckler & Scaife 2015).
  - Flags are presented as hypotheses (Hull et al. 2022).
  - Ideas for the next class come from fixed rules, not AI.
- **Bonus = questions counted as correct in the final exam:**
  - The author used "relative" (top scorer gets the max) in Excel; with REC she will use "by % of the maximum score".
  - This is the link to Aspa → Impact.
- **Ticket limit stated:** recomputing the code in developer tools is not detected; the same applies to extra-time codes.
- **AI assistance:** one sentence in Section 2 + the mandatory declaration. If the paper runs long, keep only the declaration.
- **Figures:**
  - Flow diagram (from the registration document) — placeholder.
  - Studio floor, studio and speed × accuracy map: demo data now (author can request the images), or anonymised real data after June.

**Figures in the LaTeX (24 Oct 2026), 4 of max. 6:**
- Fig. 1: flow diagram (TikZ).
- Fig. 2: contest settings (`23c`).
- Fig. 3: studio floor — (a) point on image `10`, (b) phone `16`, (c) ticket `11`.
- Fig. 4: speed × accuracy map `28` (fictitious; real anonymised data after June is optional).
- Candidates for Impact: awards show `26`, high contrast `12`.

**Accessibility** (text size, high contrast, reduced motion) is stated in "Playing".

## Section 3 — Illustrative examples ✅ structure drafted (25 Oct 2026); data in June 2027

- **Two scenarios**, both real (2026/27, second semester):
  1. **Animación** (graded continuous assessment):
     - At least one quiz created from scratch in REC by importing Moodle XML. Measure the time to the published package.
     - June: time to build the ranking from real tickets (vs 15–30 min with the spreadsheet).
     - Bonus by % levels.
     - A real question flagged as a possible misconception, chosen with June data, and what was done next class.
  2. **FTPD** (~150 students): 3 ungraded diagnostic contests + attendance (+0.1 participation).
- **"En el aire":** the author will keep it and align its engine/evaluation with REC.
  - Claude's suggestion: migrate it into a REC site (title "¡En el aire!"), so that all 13 quizzes count as REC data and retention (sessions + global test) can be shown. Author to decide.
  - With only one quiz in REC, there is no retention example.
- **June data:** students, tickets, modified/duplicate tickets (none expected: students of Advertising, Marketing and Tourism; report honestly without claiming security), flagged questions, retention.
- **Devices are not recorded** in the file; the author will note them in class if wanted.
- **University consent:** to be requested (for Aspa and REC).
- **Screencast:** the author will record it.

## Section 4 — Impact ✅ drafted (25 Oct 2026)

- **Daily practice = adaptation** (author's words):
  - large groups;
  - feedback after or before a lecture;
  - attendance;
  - motivation and attention through the exam bonus;
  - time saved vs the spreadsheet.
- **REC → Aspa:** today REC gives the number and the teacher chooses the questions. Future work: direct export in Aspa's class-list format.
- **Research questions:**
  - Does the bonus increase participation and attendance? (Needs earlier years' data to compare; otherwise present it as a question REC makes it possible to study.)
  - Group-level misconceptions (≥30%) persisting in global tests.
  - Response time vs accuracy across subjects (Liang 2024).
  - xAPI reference: Serrano-Laguna et al. 2017.
- **"En el aire" = the prototype from which REC grew** (author's decision, 25 Oct 2026); not an instance.
- **Attendance data:** the author has enrolment and quiz-based attendance for earlier years (Moodle quizzes). A descriptive comparison with 2026/27 is planned. Both periods had quizzes, so it compares REC with Moodle, not quizzes with no quizzes; a year before the 2016/17 pilot would be the baseline for the latter.
- **Publications:** Aspa submitted in Feb 2027, hopefully published by June/July, when REC is submitted → cite the Aspa paper instead of the Zenodo DOI.
- **Spread:**
  - GitHub: 0 stars/forks; Zenodo: 0 downloads (as of 25 Oct 2026).
  - REC-FTPD is an instance; "En el aire" is the prototype unless migrated to REC.
  - UCA teaching-innovation call for 2027/28.
  - AGPL, no commercial use.
- **Reviewer's "prospective impact":** answered with June data from two courses with different uses.

## Section 5 — Conclusions ✅ drafted (25 Oct 2026)

- **Contribution** (author's words): "REC permite trabajar con un gran volumen de alumnos sin almacenar ningún dato en Internet, tras las sesiones se puede tener un análisis en profundidad de las respuestas permitiendo actuar en la siguiente sesión."
  - Precise wording used: no external provider stores the answers; no own server or accounts.
- **Closing line** (author's words): "REC es una herramienta para la gamificación de cuestionarios que se adapta a cualquier asignatura permitiendo una evaluación de las respuestas de manera offline." The analysis in the studio works offline.
- **Limits, framed as the price of the serverless design** (author's argument): fixing them would require a server. These are the forgeable ticket code and no real-time synchronisation.
- **Future work:** other import formats; direct export of the bonus to Aspa's class list. Typefaces/Google Fonts dropped (author's decision).
- **Attendance comparison:** optional single aggregate rate per year; no class lists. Otherwise it stays a research question.

## Pending

- [ ] **Version for the paper:** after v1.0.0 the code changed:
  - English demo (cf9792e).
  - Softened analysis wording, "may indicate" (06d68bc, 9a6069b).
  - The figures already show the new wording. Before submission, publish a new release (e.g. v1.1.0) and update C1, the DOI in the paper and CITATION.cff.

- [ ] Verified related-tool search: Kahoot!, Quizizz/Wayground, Socrative, Moodle quiz, others. Cover per-question reports, point-on-image, extra time, accounts, data storage, player limits.
- [ ] Kahoot 2019 player limit: citable source.
- [ ] Sections 2–5: negotiation.
- [ ] Future work: bundle the typefaces instead of loading them from Google Fonts.
- [ ] REC-FTPD README is a copy of REC's (broken links to docs/ and descargas/).
- [ ] AI-assistance disclosure (registration document: developed with Claude).
