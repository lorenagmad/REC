# REC guide

REC has two parts:

- **The studio floor** (`index.html`): the website students open. It lists the contests, asks for the password and presents the questions as a live TV show, hosted by Cam, the camera.
- **The teacher studio** (`studio.html`): where teachers prepare questions, create contests, publish them and analyse the results.

Everything runs in the browser. Questions travel encrypted and can only be opened with each contest’s password.

## 1. Set up your site (once)

1. Create a [GitHub](https://github.com) account if you do not have one.
2. Create a new repository, e.g. `rec`. It can be public or private (publishing from a private one requires GitHub Pro, free for teachers through GitHub Education).
3. Upload all the files in this folder: **Add file → Upload files**, drag `index.html`, `studio.html`, `README.md`, `.nojekyll` and the `contests` and `docs` folders, and press **Commit changes**.
4. Go to **Settings → Pages**, choose the `main` branch and the `/ (root)` folder, and press **Save**.
5. In a minute or two your site will be live at `https://your-username.github.io/rec/`. That is the link for students. The studio is at `https://your-username.github.io/rec/studio.html`.

Check that it works by opening the demo contest with the password `rec demo`.

## 2. The studio

Open `studio.html` on your site (or on your computer, by double-clicking it). It has five tabs: Course, Question bank, Contests, Publish and Results. You can switch the studio language (ES/EN) at the top right.

- Everything you do is **saved automatically** in that browser.
- Use **Save project** to keep a copy on your computer (`.rec.json` file) and **Open project** to restore it or move it to another computer.
- ⚠️ The project file contains the questions, answers and passwords unencrypted. **Never upload it to GitHub.**

For a complete example, open `docs/proyecto-demo.rec.json` with **Open project**.

## 3. Question bank

### Importing from Moodle

In Moodle, go to **Question bank → Export**, choose the **Moodle XML** format, select the category and download the file. In the studio, press **Import Moodle XML** (you can select several files at once).

Supported types: multiple choice (one or several correct answers), true/false, matching, short answer and ordering (*Ordering*). Embedded images and videos are imported too, as well as feedback (general and per answer), which students will see as an explanation.

Warnings you may get:

- **Images linked from another website:** the question shows an image hosted outside Moodle (e.g. on Kahoot). It may stop working: edit the question, remove that image and add the file.
- **Very large videos:** each student will download them in full. Consider trimming them or uploading them to YouTube and adding the link.
- **Skipped questions:** unsupported types or duplicates.

### Topics

Give each question a topic (filter, select several and press **Set topic**). Topics are announced before each question, feed topic analysis and retention, and spread automatic global tests.

### Creating and editing questions

Press **New question** and choose the type. All types accept an image (compressed automatically), a video file or a YouTube/Vimeo link, an explanation after answering and, optionally, their own time limit.

- **Short answer:** ignores capitals and accents (unless you tick “Case sensitive”). Use `*` as a wildcard and give partial credit with a percentage.
- **Point on image:** add the image and drag on it to draw the correct areas (rectangles, or circles if you tick “Circle”). This type does not exist in Moodle.

## 4. Contests

A contest is a set of questions from the bank with its own password. For each one:

- **Internal title:** shown on tickets. Do not change it once used.
- **Section:** e.g. “Unit 1”. Contests in a section are added up in the ranking.
- **Password:** press **Generate** for one that is easy to dictate. Capitals and accents do not matter.
- **Visible on the home page**, **answer analysis** (students download a file with their answers) and **practice mode** (no points, no clock, with solutions; same password).
- **Time and scoring:** seconds per question type and points for an instant correct answer and for one in the last second (1000 and 500 by default).
- **Presentation:** Cam’s welcome message and, if you like, your own lines after a correct answer, a wrong one, or when time runs out.

### Automatic global tests

In **Contest questions → Generate a global test**, choose the source contests, how many questions to take from each and, optionally, a maximum per topic. The studio picks them at random and marks the contest as a global test (needed to calculate retention). You can then adjust them by hand.

## 5. Publishing

In the **Publish** tab the studio checks that everything is ready and flags possible problems. Press **Generate the package (.zip)**:

1. Unzip the file: it contains a `contests` folder.
2. In your repository, open `contests` → **Add file → Upload files**.
3. Drag the whole content of the `contests` folder from the .zip (replacing existing files) and press **Commit changes**.

Whenever you change something (a question, a password, visibility), generate the package again and upload it. **Download the password list** gives you a text file to keep them at hand (do not upload it).

## 6. In class

Share your site’s link (e.g. on your learning platform) and say the password right before starting. Students:

- type their name and ID; there is one attempt per contest in each browser;
- can switch language (ES/EN), mute the sound and open **Accessibility** (text size, high contrast, reduced motion);
- at the end, copy their ticket or download the file (if the contest has analysis) and send it the way you indicate.

**Extra time:** in **Results → Extra time** you generate a personal code linked to the student’s ID (+25 %, +50 %, +75 % or double). It works for every contest in the project and the score is calculated on the extended time.

## 7. Results

### Ranking

Choose the section, paste the tickets or load the files and press **Prepare the awards show**. The studio checks every code, discards tampered tickets, flags duplicates and adds up each student’s points.

The **bonus** (e.g. free questions in the exam) can be:

- **By percentage of the maximum** (recommended): students know from the start what they need. Note that getting everything right at half time gives 75 % of the maximum.
- **Relative to the top scorer:** the top scorer gets the maximum and the rest in proportion.

You can rename the bonus and change the number of levels and the thresholds; the ranking is recalculated instantly. Download the version to publish (with the ID partly hidden) and the full CSV sheet for yourself. **Publish the ranking only in a closed space, such as your learning platform.**

### Analysis

Load the `.json` files from contests with analysis (e.g. all submissions from a Moodle assignment). There are two views:

- **One contest:** summary, ideas for the next class, speed and accuracy map (masters it, knows but hesitates, rushes, needs review), question-by-question analysis (difficulty, most common mistake, whether the question discriminates) and student by student.
- **Everything loaded:** mastery by topic and retention between a section’s contests and its global test.

**Class review** projects the most missed questions full screen with the answer distribution; the solution appears when you press (arrow keys and space bar). **Anonymise** replaces name and ID with a generic code, the same across contests for each student, also in CSV exports.

## 8. Security and privacy

- Without the password, contest files are unreadable. With it, a technically skilled student could inspect the answers in their browser: it is a deterrent suitable for class contests, not for high-stakes exams.
- Use two-word passwords with a number and do not reveal them until it is time to start.
- Ticket and extra-time codes prevent scores from being edited by hand, but “one attempt per contest” relies on the browser.
- Student data never go through any server: tickets reach you through the channel you choose and are processed on your computer.
- Third-party images and videos must be usable for teaching. Check with your institution before publishing them on an open website.

## 9. FAQ

**A student says they already took the contest but did not finish it.** The attempt is recorded at the end. If they closed it before, they can enter again.

**I changed a question and cannot see it.** Generate the package again, upload it and reload the page.

**I want to hide a contest.** Untick “Visible on the home page”, generate the package and upload it. To see it anyway, add `?all` to the address.

**Can I use REC with several groups?** Yes: create one repository per group or use different sections.
