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

## Pending

- [ ] Verified related-tool search: Kahoot!, Quizizz/Wayground, Socrative, Moodle quiz, others. Cover per-question reports, point-on-image, extra time, accounts, data storage, player limits.
- [ ] Kahoot 2019 player limit: citable source.
- [ ] Sections 2–5: negotiation.
- [ ] Future work: bundle the typefaces instead of loading them from Google Fonts.
- [ ] REC-FTPD README is a copy of REC's (broken links to docs/ and descargas/).
- [ ] AI-assistance disclosure (registration document: developed with Claude).
