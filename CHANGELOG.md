# Changelog

Second Nature is one HTML file, so each entry here is one new version of that file. Versions are the ones the app shows in its footer.

## 2026-09-26 — a plan for the day, and a check that learns
- Day plan: the fuel you pick (Low, Some, Full) now shapes a plan for the rest of the day. It learns the hours you actually get things done from the last six weeks, puts the hardest recall in your best hour and the dread’s first step in the next best, and shrinks to three small things on a low day.
- The Claude recall check learns from you: Fair, Too harsh and Too soft votes under each check, plus the gap between your scores and Claude’s, tune how generous it is.
- Maintenance pass: once a week, Progress queues up to five suggested rewrites, better pictures, splits or new cards for chunks that keep slipping or need work. You apply or dismiss each one; nothing changes on its own.

## 2026-09-25 — tidy-ups
- Marking a practice card no longer jumps the page to the top.
- The "Make a card" buttons under the Claude check are gone.
- The Snowball tab group is folded into a Quests menu (Quests, Starter, Motivation) to save room in the tab bar.

## 2026-09-25 — a kinder recall check, cards after each recall
- The Claude recall check now scores on three parts (the idea, the why, the when). The metaphor and links to other chunks are memory aids: welcome, never required, never counted as misses. When torn between two scores it now picks the higher one if the core idea is there, and lists at most two or three misses that matter.
- The self-scoring copy says the same: Cold is the idea, the why and the when; the fourth point on the recall card is marked optional.
- A chunk's practice cards now run straight after its recall (Mostly or Cold), inside the same session, and the session resumes at the next chunk when the round is done.

## 2026-09-25 — Method figures keep their hover, lose the pointer light
- The Method page figures no longer carry the pointer-following light; the hover border, lift and glow stay.

## 2026-09-25 — Progress charts and effect bars
- Four new charts on Progress: where your chunks sit on the gap ladder (split by last score), a 12-week recall activity heatmap, weekly recalls stacked by score, and a per-subject Cold share with overdue counts. All have hover and keyboard tooltips and work in both themes.
- Effect cards on the Quests page: the fade bar shared a class name with the Claude feedback box and inherited its padding and border. It now has its own class and a slim gradient bar.

## 2026-09-24 — audit fixes, smarter recall, Claude features

### Recall and scheduling
- Scoring Fragments brings the chunk back tomorrow one rung down, instead of advancing it.
- Late recalls earn partial credit for the time the memory held.
- Recalling a chunk before it is due is logged as practice: no pips, no quest tick, no run completion, and it stays out of stats and XP.
- Calibration is now "Cold or not": you predict whether the recall will come back cold, and the app scores that prediction with confidence bands that widen when there are few data points. It reports after 8 scored recalls.
- The due list sorts by relative overdueness (days late divided by the gap) and interleaves subjects.
- Gaps are spread by about 5 percent per chunk so a batch added together does not all come due on one day.
- After a relearn the chunk gets a retest, recorded as a retest rather than a fresh score.
- Chunks that keep slipping get a leech tag, a "Keeps slipping" coach card on Today, and an "Illusions" list on Progress.
- Practice cards carry a date and are picked oldest-first.

### Quests, Snowball and the character
- Starting a task from a quest opens the Snowball with a link token, so finishing there closes the quest. A busy Snowball shows a toast instead of dropping the task.
- Two open tabs no longer fight over quest claims; one claims, the other adopts its state.
- The day turns over at midnight while the page is open.
- Quest counts read from stored day records, recall progress checks after every recall, and runs can be undone.
- Weekend reviews have stable ids so they cannot be answered twice.
- Boons are removed. Runs are put down with plain fuel and effect cost is computed per path.
- Struggling quests are detected and offered a reshape, a snooze, or an archive.
- Chapters show what is owed and a guess at who helped.

### Data, storage and polish
- Backup version 2: the file holds every collection, and restore shows a plan first, writes in batches with retries, and prunes dangling links.
- Records carry an updated timestamp so an older backup cannot overwrite newer work on restore.
- Storage full is reported honestly, and the inbox keeps your text if a save fails.
- Duplicate detection when adding a chunk, automatic subject guessing, and a stale badge on chunks not touched in a long time.
- Rendering is batched per frame, game maths and day records are cached, and search is debounced.
- The Add button waits for the database to connect, with a note after 20 seconds on a slow connection.
- Accessibility: toast announcements, Theme and Motion labels, current-step marking, 40 px touch targets on touch devices.

### Claude features (optional, hidden when Claude is not granted)
- One shared helper handles every call, with a consistent box: idle, busy with Stop, error with Try again, done. A refusal hides every Claude button for the page.
- Suggest practice cards, in the editor and on the wizard.
- Suggest links to other chunks, with a Tick button per suggestion and nothing ticked for you.
- Keep the check: "Make a card" from a missed recall, misses recorded on the chunk's history, and a drift note on Progress when your scores and Claude's disagree.
- Check this chunk: quality problems listed in the editor with an "Apply suggestion" that never saves.
- Wizard assists on the picture, cue, notes and name steps.
- Leech doctor on the "Keeps slipping" card: rewrite the gist, rewrite the picture, or split the chunk.
- Quests: reshape a struggling quest, draft a first step for a dreaded task, draft expedition steps, write a chapter story.
- Snowball "Smaller" button that asks for a smaller version of the current step.

### Known gaps
- The projection reads the ladder only.
- CSV export averages include early recalls.
- JSON export refuses when there are no chunks.
- Snowball links in flight from before this version have no token.
- The leech doctor appears only on the Today coach card.

## 2026-09-24 — Method figures and hover glow
- Nine new Method-page figures drawn from the course, plus a tidy of the existing ones.
- Octopus of attention redrawn, held slots in teal, diffuse mode as dot-to-dot links.
- Hover glow on figures is filter-only (a CSS transform on SVG groups that carry a transform attribute makes them jump).
- Smoother aurora background and no dark band when scrolling.

## 2026-09-23 — first public template
- Stripped of the owner's personal sections and data; sample character is "Sam", default name is "You".
- Links grouped by topic; Bestiary removed.
