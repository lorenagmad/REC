# REC guide: create your contest from scratch

REC turns your quizzes into a live TV game show. It has two parts:

- **The studio floor:** the website your students open. It lists your contests, asks for the password and presents the questions as a live show, hosted by Cam, the camera.
- **The studio:** your workspace. This is where you prepare questions, create contests, publish them and analyse the results.

Everything is published for free on GitHub Pages and runs in the browser, with no servers and no student accounts. Questions travel encrypted: each contest only opens with its password.

The original REC is at <https://github.com/lorenagmad/REC>.

---

## Part 1. Set up your site (once)

### Step 1. Download the REC kit

1. Go to <https://github.com/lorenagmad/REC>, open the `descargas` folder and click `rec-kit.zip`.
2. Press the download button (**Download raw file**, the down-arrow icon).
3. Unzip it. Inside you will find this guide and a folder called **`web`**, which is the only thing you will upload to GitHub.

### Step 2. Create your GitHub account

If you do not have one, go to <https://github.com>, press **Sign up** and follow the steps (email, password and username). Your username will be part of your contest’s address, so choose a simple one.

### Step 3. Create a repository for your contest

1. Press the **+** at the top right and choose **New repository**.
2. In **Repository name**, type a short name without spaces or accents, e.g. `history-quiz`. It will appear in the web address.
3. Leave **Public** selected. (A private repository also works, but publishing it requires GitHub Pro, which is free for teachers through GitHub Education.)
4. Do not tick any of the options below (README, .gitignore, licence).
5. Press **Create repository**.

### Step 4. Upload the REC files

1. On the page of your new repository, click the **uploading an existing file** link.
2. On your computer, open the kit’s `web` folder, select **everything inside it** (`index.html`, `studio.html`, `README.md` and the `contests` folder) and drag it onto the GitHub page. Drag the content, not the `web` folder itself.
3. Wait for the files to finish uploading and press **Commit changes**.

### Step 5. Publish your site

1. In the repository, open **Settings** (the gear in the top bar) and, in the left menu, **Pages**.
2. Under **Source**, keep **Deploy from a branch**. Under **Branch**, choose `main` and the `/ (root)` folder, and press **Save**.
3. Wait a minute or two and reload the page. **Your site is live at…** will appear at the top with your address, which looks like this:

   `https://your-username.github.io/history-quiz/`

That is the address for your students. Open it: you will see the REC home page, with no contests yet.

Your studio is at the same address ending in `studio.html`:

`https://your-username.github.io/history-quiz/studio.html`

Bookmark it: that is where you will work from now on.

---

## Part 2. Prepare your contest in the studio

Open your studio. It has five tabs: **Course**, **Question bank**, **Contests**, **Publish** and **Results**. At the top right you can switch the language (ES/EN) and open this guide with **Help**.

- Everything you do is **saved automatically** in that browser.
- Use **Save project** every now and then to keep a copy on your computer (`.rec.json` file), and **Open project** to restore it or continue on another computer.
- ⚠️ The project file contains the questions, answers and passwords unencrypted. **Keep it on your computer only and never upload it to GitHub.**

### 1. Course

Type the name of your course or subject (it appears on the home page), an optional subtitle and the default contest language.

### 2. Question bank

**Importing from Moodle.** In Moodle, open your course’s question bank, choose **Export**, the **Moodle XML** format and the category, and download the file. In the studio, press **Import Moodle XML** (you can select several files at once).

Multiple choice (one or several correct answers), true/false, matching, short answer and ordering (*Ordering*) questions are imported, with their images, videos and feedback, which students will see as an explanation. The studio will warn you about:

- **images linked from another website:** they may stop working. Edit the question, remove that image and add the file;
- **very large videos:** each student will download them in full. Consider trimming them or uploading them to YouTube and adding the link;
- **skipped questions:** unsupported types or duplicates.

**Creating questions.** Press **New question** and choose the type. All types accept an image (compressed automatically), a video file or a YouTube/Vimeo link, an explanation after answering and, optionally, their own time limit.

- **Short answer:** ignores capitals and accents (unless you tick it). Use `*` as a wildcard and give partial credit with a percentage.
- **Point on image:** add the image and drag on it to draw the correct areas (rectangles, or circles if you tick “Circle”).

**Topics.** Give each question a topic: filter, select several and press **Set topic**. Topics are announced before each question, feed topic analysis and spread automatic global tests.

### 3. Contests

A contest is a set of questions from the bank with its own password. Press **New contest** and fill in:

- **Internal title:** shown on student tickets. Do not change it once the contest has been used.
- **Section:** e.g. “Unit 1”. Contests in the same section are added up in the ranking.
- **Visible name and description:** what students see on the home page.
- **Password:** press **Generate** for one that is easy to dictate. Capitals and accents do not matter.
- **Visible on the home page**, **answer analysis** (students download an xAPI file with their answers) and **practice mode** (no points, no clock, with solutions; same password).
- **Time and scoring:** seconds per question type and points for an instant correct answer and for one in the last second (1000 and 500 by default).
- **Presentation:** Cam’s welcome message and, if you like, your own lines after a correct answer, a wrong one or when time runs out.

Then choose the questions from the bank. For a **global test**, use **Generate a global test**: choose the source contests, how many questions to take from each and, optionally, a maximum per topic. The studio picks them at random and you can adjust them by hand.

### 4. Publish

In the **Publish** tab the studio checks that everything is ready. Press **Generate the package (.zip)** and unzip it: it contains a `contests` folder. To upload it:

1. In your GitHub repository, open the `contests` folder.
2. Press **Add file → Upload files**.
3. Drag **the whole content** of the package’s `contests` folder (the `index.json` file and the `.bin` files). They will replace the existing ones.
4. Press **Commit changes**. In a minute or two your contests will appear on the home page.

Whenever you change something (a question, a password, a contest’s visibility), generate the package again and upload it. **Download the password list** gives you a text file to keep them at hand; do not upload it.

---

## Part 3. In class

Share your site’s address (e.g. on your learning platform) and say the password right before starting. Students:

- type their name and ID. There is one attempt per contest in each browser;
- can switch language (ES/EN), mute the sound and open **Accessibility** (text size, high contrast and reduced motion);
- at the end, copy their ticket or download the file (if the contest has analysis) and send it the way you indicate, e.g. a Moodle assignment.

**Extra time.** In **Results → Extra time** you generate a personal code linked to the student’s ID (+25 %, +50 %, +75 % or double). Give it privately; the student types it before starting. Nothing needs to be uploaded to GitHub: the code works for every contest published from your project, and the score is calculated on the extended time. If you start a new project, the codes you handed out stop working.

---

## Part 4. Results

### Ranking

Choose the section, paste the tickets or load the files, and press **Prepare the awards show**. The studio checks every code, discards tampered tickets, flags duplicates and adds up each student’s points.

The **bonus** (e.g. free questions in the exam) can be:

- **By percentage of the maximum** (recommended): students know from the start what they need. Note that getting everything right at half time gives 75 % of the maximum.
- **Relative to the top scorer:** the top scorer gets the maximum and the rest in proportion.

You can rename the bonus and change the number of levels and the thresholds: the ranking is recalculated instantly. Download the version to publish (with the ID partly hidden) and the full CSV sheet for yourself. **Publish the ranking only in a closed space, such as your learning platform.**

### Analysis

Load the `.json` files from contests with analysis (e.g. all submissions from a Moodle assignment). There are two views:

- **One contest:** summary, ideas for the next class, speed and accuracy map (masters it, knows but hesitates, rushes and needs review), question-by-question analysis (difficulty, most common mistake and whether the question discriminates) and student by student.
- **Everything loaded:** mastery by topic and retention between a section’s contests and its global test.

**The xAPI file.** The file students download is in **xAPI** format (Experience API), the standard for recording learning activities: it contains one statement per question (what they answered, whether it was correct and how long it took) and, inside, the verifiable ticket used by the ranking and the analysis. It is a single file per student and contest. The **Download all interactions as xAPI** button merges the statements from all loaded files into one, ready to import into an LRS (your institution’s learning record store, if it has one); with “Anonymise” ticked, names and IDs are removed.

**Class review** projects the most missed questions full screen with the group’s answer distribution; the solution appears when you press (also with the arrow keys and the space bar). **Anonymise** replaces name and ID with a generic code, the same for each student across contests, also in CSV exports.

---

## Part 5. Maintenance

**Updating REC.** When there is a new version, download the kit again and upload only `index.html` and `studio.html` to your repository (**Add file → Upload files**), replacing the old ones. Your contests are not affected.

**Hiding a contest.** Untick “Visible on the home page”, generate the package and upload it. To see it anyway, add `?all` to the end of the address.

**Several groups or subjects.** Create one repository for each by following Part 1, or use different sections in the same project.

---

## Security and privacy

- Without the password, contest files are unreadable. With it, someone with technical skills could inspect the answers in their browser: it is a deterrent suitable for class contests, not for high-stakes exams.
- Use two-word passwords with a number and do not reveal them until it is time to start.
- Ticket and extra-time codes prevent scores from being edited by hand, but “one attempt per contest” relies on the browser.
- Student data never go through any server: tickets reach you through the channel you choose and are processed on your computer.
- Any third-party images and videos you include must be usable for teaching. Check with your institution before publishing them on an open website.

## FAQ

**A student says they already took the contest but did not finish it.** The attempt is recorded at the end. If they closed it before, they can enter again.

**I changed a question and cannot see it.** Generate the package again, upload it to the `contests` folder and reload the page.

**The home page says the list of contests cannot be loaded.** Check that the `contests` folder in your repository contains the `index.json` file.

**I lost my studio project.** If you cleared the browser data, open the copy you saved with **Save project**. That is why it is worth saving it every now and then.
