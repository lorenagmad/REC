# REC — comparison table and related work (checked 23 October 2026)

Every cell for the other tools comes from the tool's official help centre, website, privacy policy or docs. REC's row was checked against its code.
Legend: ✓ yes · ◐ partial · ✗ no · ? not documented (never write "no" in the paper).

## Columns

| ID | Column | Definition |
|---|---|---|
| C1 | Speed scoring | Points for a correct answer depend on response time |
| C2 | No student accounts | Students join with a code/nickname |
| C3 | Data not on the vendor's servers | Results/answers are not stored in the provider's cloud |
| C4 | Moodle XML import | |
| C5 | Point on image | Hotspot / pin question type |
| C6 | Per-student extra time | Individual, not whole-class |
| C7 | Practice mode | Self-study without affecting scores |
| C8 | Per-question response + time export | Per student |
| C9 | Speed × accuracy analysis | Built in |
| C10 | Retention across sessions | Built in |
| C11 | xAPI export | |
| C12 | Verifiable results ticket | Teacher can check offline |
| C13 | Free for a ~150-student game | Today |

## Table

| Tool | C1 | C2 | C3 | C4 | C5 | C6 | C7 | C8 | C9 | C10 | C11 | C12 | C13 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **REC** | ✓ | ✓ | ✓¹ | ✓ | ✓ | ✓ (personal codes) | ✓ | ✓ | ✓ | ✓ | ✓ | ◐² | ✓ |
| Kahoot! | ✓ | ✓ | ✗ | ✗ | ✓ (paid) | ✗ | ✓ | ✓ (paid) | ✗³ | ◐ (Combine reports) | ? | ? | ✗ (10 for higher ed) |
| Wayground (Quizizz) | ◐ (paid) | ◐ | ✗ (AWS) | ? | ✓ (paid) | ✓ | ✓ | ◐ | ✗ | ? | ? | ? | ✓ (up to 100) / ✗ for 150 |
| Socrative | ✗ | ✓ | ✗ (AWS, US) | ✗ | ✗ | ✗ | ? | ◐ (no times) | ✗⁴ | ? | ? | ? | ✗ (50) |
| Moodle Quiz | ✗ | ✗ | ◐ (institution's server) | ✓ | ◐ (drag markers) | ✓ (overrides) | ◐ | ◐ (time per attempt) | ✗ | ✗ | ✗ (core) | ? | ✓ |
| Blooket | ✓ | ✓ | ✗ | ✗ | ? | ? | ✓ | ◐ (paid, average time) | ✗ | ? | ? | ? | ✗ (60) |
| Gimkit | ✗ | ✓ | ✗ | ✗ | ? | ✗ | ✓ | ◐ (PDF, no times) | ✗ | ✗ (within a game) | ? | ? | ✓ (most modes) |
| Mentimeter | ✓ | ✓ | ✗ (EU cloud) | ? | ◐ (not in quizzes) | ✗ | ✗ | ◐ (paid) | ✗ | ? | ? | ? | ◐ |

Notes:
1. Nothing goes through a REC server. The static host (GitHub Pages) still sees visitors' IP addresses, and the pages load Google Fonts, plus YouTube/Vimeo when contests embed videos.
2. The ticket code is a non-cryptographic hash (cyrb53) over a salt that travels inside the contest every student decrypts (`index.html` lines 456–460). A student with the browser's developer tools could compute a valid code for any score. The extra-time codes (line 635) can be forged the same way. Honest wording: it **detects casual edits**; it is not tamper-proof. No serverless design can fully prevent this, because the key would have to be in the student's browser.
3. Kahoot!'s "Confidence" experience combines *self-reported* confidence with correctness, not response time.
4. Socrative's "AI Insights" lists "common misconceptions", but not from response time.

Open-source alternatives: **all need a server**. ClassQuiz (MPL-2.0: FastAPI + Socket.IO + PostgreSQL + Redis), QuizDock (MIT: PostgreSQL + Redis; time-weighted points), Razzia (MIT, Node server), Darkhold (GPL-3.0, "not ready for production"), and Kahoodle (a Moodle plugin with speed scoring; needs Moodle accounts). H5P emits xAPI but needs a host CMS and has no live mode. No static, serverless, open-source equivalent was found.

## Kahoot! free-plan player limit (verified)

The author's recollection ("10 players in 2019") needs correcting:

| When (article "updated") | Free plan, live games | Source |
|---|---|---|
| Aug 2019 | 1,000 players | Kahoot! help centre, archived |
| 25 Nov 2019 | K-12 1,000; **higher education 50** | [archive, 13 Dec 2019](https://web.archive.org/web/20191213032024/https://support.kahoot.com/hc/en-us/articles/360008246494-Plans-and-billing-options-for-schools) — checked by Claude |
| 27 Feb 2021 | **Higher education 10** | [archive, 2 Mar 2021](https://web.archive.org/web/20210302015423/https://support.kahoot.com/hc/en-us/articles/115003072287-How-many-players-can-join-a-game-) — checked by Claude |
| 22 Oct 2026 (current) | "Kahoot! Go": higher education 10, K-12 40 | support.kahoot.com article 115003072287 |

So, for a 150-student course, the free plan stopped being enough in **late 2019** (50 players) and was cut to **10** in **2021**. No Kahoot! announcement was found; cite the archived help pages.

## What this means for the thesis (author to decide)

- **Not differentiators:**
  - No student accounts: Kahoot!, Socrative, Blooket, Gimkit and Mentimeter don't need them either.
  - Practice mode and point-on-image questions.
  - Per-student extra time: Wayground and Moodle have it.
  - Difficulty/discrimination statistics: Moodle has them.
- **"The teacher holds the data"** is shared with a self-hosted Moodle. Against Moodle, REC's difference is speed scoring + speed × accuracy analysis + no accounts + no server at all.
- **What survives as REC's position:**
  - The **combination**: static, serverless, open-source deployment.
  - Moodle XML import outside Moodle.
  - A per-student xAPI file.
  - Built-in speed × accuracy and retention analysis.
- **"Live":** REC has no real-time shared state (no WebSocket/WebRTC). Each student plays on their own device, and the ranking is built afterwards. "TV-style game show" must not suggest a synchronous multiplayer game.
- **"Cryptographic verification of results"** (wording in the OTRI document) is inaccurate; see note 2.

## Verified references found (DOIs checked in Crossref)

Speed × accuracy rationale:
- Heckler, A. F., Scaife, T. M. (2015). Patterns of response times and response choices to science questions: the influence of relative processing time. *Cognitive Science* 39(3). doi:10.1111/cogs.12166 — misconception-like answers were faster.
- Liang, Z. (2024). More haste, less speed? Relationship between response time and response accuracy in gamified online quizzes in an undergraduate engineering course. *Frontiers in Education* 9, 1412954. doi:10.3389/feduc.2024.1412954 — Kahoot! data; fast errors = guesses, slow errors = weak recall.
- Maris, G., van der Maas, H. (2012). Speed-accuracy response models: scoring rules based on response time and accuracy. *Psychometrika* 77(4), 615–633. doi:10.1007/s11336-012-9288-y — formal basis for speed-weighted scoring.
- Wise, S. L. (2017). Rapid-guessing behavior. *Educational Measurement: Issues and Practice* 36(4), 52–61. doi:10.1111/emip.12165 — checked in Crossref; separates fast guesses from fast errors.

Caveats:
- Wang, A. I., Tahir, R. (2020), *Computers & Education* 149, 103818 — already cited; reports time pressure among the problems.
- Hull, M. M., Jansky, A., Hopf, M. (2022). Does confidence in a wrong answer imply a misconception? *Phys. Rev. Phys. Educ. Res.* 18, 020108. doi:10.1103/PhysRevPhysEducRes.18.020108 — present the flags as hypotheses for the teacher.

Related software papers:
- Alqahtani, R. (2026). McqAnalysis: Classical test theory item analysis for multiple-choice tests in R. *SoftwareX* 35, 102797. doi:10.1016/j.softx.2026.102797.
- Serrano-Laguna, Á. et al. (2017). Applying standards to systematize learning analytics in serious games. *Computer Standards & Interfaces* 50, 116–123. doi:10.1016/j.csi.2016.09.014 — xAPI for games.
- Other SoftwareX precedents (UBUMonitor 2024, Game-Based Assessment labelling tool 2024): DOIs reported by the search, not yet re-checked.
