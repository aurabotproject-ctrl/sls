# ⚔️ Summarise Like Samurais
### A 200-Lesson Journey from Apprentice to Master — Teaching Summarising Through Bible Stories

**Audience:** Ages 9–12
**Lesson length:** ~15 minutes
**Total lessons:** 200 (40 Bible stories &times; a 5-lesson cycle per story)
**Core skill:** Reading a passage and identifying essential information vs. unnecessary detail, then re-expressing it clearly in the student's own words.

> **What changed in this version:** every story is now written in **three paragraphs** (same three paragraphs across all three reading levels), and every story takes **five lessons** instead of one: read the whole story and check comprehension, then summarise paragraph 1, paragraph 2, and paragraph 3 one at a time using the S.W.O.R.D. method, then pull all three into one finished summary of the whole story. This is slower but far deeper — students practise the *process* of summarising, not just the output.

> **Latest update:** Lesson 1 now has a **print reading** button (differentiated scrolls, printable per level), a **print all readings** button (scales as more stories are built), and a **teacher lesson plan** button with **New Zealand Curriculum links for Years 5–6** and its own print option. See Section 13, "Printing & Teacher Lesson Plans," for the full build notes.
>
> **Newest update:** Lesson 1 now also supports **fully offline, teacher-led delivery**. A **🖥️ Presentation Mode** turns the lesson into a full-screen, teacher-controlled slideshow (arrow keys or on-screen Next/Back, a scroll-level switcher, Esc to exit) that walks the *whole class* through the reading and discussion prompts, while students work entirely on paper. A matching **📝 Print worksheet** button generates the paper half of the lesson — the comprehension check, the retell space, and the Master's Seal — as a print-ready student handout (with an on-screen preview first). The rank ladder also now carries illustrated artwork per rank, generated from the Section 11 image prompts. See Section 14, "Presentation Mode & Offline Worksheets," for full build notes.
>
> **Latest build:** Story 1 (Creation) now has its **full five-lesson cycle** built and playable, not just Lesson 1. A **Lesson tab bar** above the demo switches between all five lessons of the cycle. Lessons 2–4 each walk the student through a complete S.W.O.R.D. pass (Search/Watch/Order/Remove/Deliver) on one paragraph, with a saved one-sentence summary that Lesson 5 recalls automatically to build the whole-story "Full Scroll." Every lesson got its own Teacher Lesson Plan, Presentation Mode deck, and printable Worksheet, all generated from a single shared data layer.
>
> **Newest build:** Stories 2–5 (Noah's Ark, Abraham's Call & Journey, Joseph's Coat & Dreams, and Joseph Forgives His Brothers) are now built to the same standard as Story 1 — full three-level scrolls, comprehension data, and all three Lessons 2–4 S.W.O.R.D. paragraphs — and the app was refactored around a `STORIES` array and a `setActiveStory()` function so any number of stories can share the same five lesson panels. A new **Story tab bar** sits above the lesson tabs, letting the demo switch between all five built stories; switching stories re-renders every lesson's text, chips and starters, and each story's saved work lives under its own story-scoped `localStorage` keys, so nothing bleeds between stories. See Section 15, "The Full Five-Lesson Cycle," for the build notes on both the single-story cycle and this new multi-story architecture.
>
> **Latest build:** Rank 5, "Trusted Retainer" (Stories 21–25 — The Birth of Jesus, The Shepherds & the Angels, John the Baptist, The Baptism of Jesus, Jesus Calls His First Disciples) and Rank 6, "Honoured Samurai" (Stories 26–30 — The Sower & the Seeds, The Good Samaritan, The Lost Sheep, The Prodigal Son, The Wise & Foolish Builders) are now built to the same standard as Ranks 1–4, using the exact same `STORIES`/`setActiveStory()` architecture with zero new code — just ten more entries pushed into `STORIES_CHRISTIAN` plus their ten Story Scene hero images. The Story tab bar now shows all 30 built stories; every one of the 30 has its full five-lesson cycle (Read & Understand, three S.W.O.R.D. paragraph lessons, and the Full Scroll recap), its own Teacher Lesson Plan/Presentation Mode/Worksheet, its own Story Scene image, and its own story-scoped `localStorage` keys. See Section 15 for the updated story list and build notes for Stories 31–40.
>
> **Latest build — the Bible Stories curriculum is complete:** Rank 7, "Elite Samurai" (Stories 31–35 — Jesus Feeds the Five Thousand, Jesus Calms the Storm, Jesus Walks on Water, Zacchaeus the Tax Collector, Jesus Raises Lazarus) and Rank 8, "Master Samurai" (Stories 36–40 — The Last Supper, The Crucifixion, The Resurrection, Doubting Thomas, Pentecost and the Holy Spirit) are now built, using the exact same `STORIES`/`setActiveStory()` architecture with zero new code. **All 40 stories, all 8 ranks, all 200 lessons of the Bible Stories curriculum are now 100% built, playable, and printable** — every story has its full five-lesson cycle, its own Teacher Lesson Plan/Presentation Mode/Worksheet, its own Story Scene hero image, and its own story-scoped `localStorage` keys. See Section 15 for the final build notes.
>
> **Latest build:** Japanese Legends Stories 1–10 (Rank 1 "Apprentice Samurai" and Rank 2 "Novice Swordsman" — Momotaro, Issun-boshi, Shita-kiri Suzume, Hanasaka Jiisan, Kobutori Jiisan, Tsuru no Ongaeshi, Kasa Jizo, Bunbuku Chagama, Urashima Taro, Kappa no Sara) are now built with full five-lesson cycles and Story Scene images, including Momotaro's scene image which had been missing until now. 30 Japanese Legends stories remain (Section 9B).
>
> **Latest build — three-file structure (to fix GitHub upload/size issues):** the app's Story Scene images (the large per-story hero illustrations) have been moved **out of `app.html`** and into two external data files, because the single-file version had grown past 5.7MB and GitHub was reporting problems with a file that size. The app is now **three files that must be kept together in the same folder**:
> - **`app.html`** — the app itself (now ~1.6MB)
> - **`data-bible-scenes.js`** — all 40 Bible Stories Story Scene images (`STORY_SCENES_CHRISTIAN`)
> - **`data-japanese-scenes.js`** — all 10 (soon 40) Japanese Legends Story Scene images (`STORY_SCENES_JAPANESE`)
>
> `app.html` loads both via `<script src="data-bible-scenes.js">` / `<script src="data-japanese-scenes.js">` tags in its `<head>`, right before its own inline script. This works identically whether the app is opened by double-clicking `app.html` locally, or hosted on GitHub Pages/Netlify — **as long as all three files are uploaded to the same folder**. If only `app.html` is uploaded (or the two `.js` files are missing/renamed), the page will still load but every Story Scene image will be blank (everything else — text, lessons, quizzes — still works, since only the images moved). Future story batches should keep adding new entries to these two external files, not back into `app.html`, to keep it small.

---

## 1. The Big Idea

Every student begins as an **Apprentice Samurai**, training in the **Dojo of Summary**. Their weapon isn't a blade — it's their mind. Just as a samurai trains daily in small, disciplined sessions to master the sword, students train daily in small 15-minute sessions to master **summarising**.

Each lesson uses a **Bible story** as the "text to summarise," and every story is provided in **three reading levels** (same story, three difficulties) so it can flex to each student's reading ability without changing the summarising skill being taught.

As students progress through the 200 lessons, the **scaffolding (prompts, sentence starters, guided questions) gradually disappears**, until by the final rank they are summarising fluently and independently — "from muscle memory," like a true master.

---

## 2. The Samurai Rank System

Students climb through **8 Ranks**, 5 stories (= 25 lessons) each. Each rank has its own belt colour, badge, and a themed dojo backdrop.

| Rank | Stories | Lessons | Title | Belt Colour | Focus |
|---|---|---|---|---|---|
| 1 | 1–5 | 1–25 | 🥋 Apprentice Samurai | White | What IS a summary? Finding "who/what" |
| 2 | 6–10 | 26–50 | ⚔️ Novice Swordsman | Yellow | Finding key events & putting them in order |
| 3 | 11–15 | 51–75 | 🛡️ Disciplined Warrior | Orange | Cutting unnecessary detail |
| 4 | 16–20 | 76–100 | 🏹 Skilled Ronin | Green | Summarising in your own words (not copying) |
| 5 | 21–25 | 101–125 | 🎌 Trusted Retainer | Blue | Summarising longer/more complex passages |
| 6 | 26–30 | 126–150 | 🏯 Honoured Samurai | Purple | Summarising with a clear structure (beginning/middle/end) |
| 7 | 31–35 | 151–175 | 🐉 Elite Samurai | Brown | Speed & independence — minimal prompts |
| 8 | 36–40 | 176–200 | 👑 Master Samurai | Black | Full independence — teaching/checking others' summaries |

At the end of Rank 8 (Lesson 200), students receive a **"Master Samurai Scroll of Certification."**

### 2.1 Curriculum Toggle — Christian vs. Japanese Legends

The app now supports **two parallel story curricula** that share every other part of the design: the 8-rank/belt ladder above, the mascot art, rank badges, dojo backdrops, S.W.O.R.D. method, print layouts, presentation mode, and every UI element. A toggle switch at the top of the page reads **"Christian" / "Japanese Legends"**:

- **Christian** (default) follows the 40-story Bible curriculum map in Section 9.
- **Japanese Legends** follows a new 40-story map of Japanese folktales and myths, well-known and age-appropriate for 9–12 year-olds (Section 9B), chosen to teach the same virtues (courage, kindness, gratitude, honesty, perseverance) through a different cultural lens that fits the samurai/dojo theme naturally.

Flipping the toggle only swaps which `STORIES` array is active (`STORIES_CHRISTIAN` vs `STORIES_JAPANESE`) and resets to that curriculum's Story 1 — it does not touch ranks, badges, backdrops, fonts, or any other art. Only the **Story Scene** hero image (Section 11.D) differs per curriculum, since it depicts a moment from that specific story. As of this build, **Stories 1–10 (Momotaro through Kappa no Sara, Ranks 1–2)** have the full 5-lesson interactive cycle built in the Japanese Legends curriculum, each with its own Story Scene image — see Section 15.1.

---

## 3. The S.W.O.R.D. Method

The one tool every student carries through the whole program — a memorable acronym that *is* the skill:

| Letter | Meaning | What the student does |
|---|---|---|
| **S** | **Search** for the main characters | Who is this story about? |
| **W** | **Watch** for the key events | What actually happened? |
| **O** | **Order** the events | What happened first, next, last? |
| **R** | **Remove** the unimportant details | What can be cut without losing the meaning? |
| **D** | **Deliver** it in your own words | Say/write it as your own sentences |

Every lesson practises "drawing the SWORD" — this phrase can be used as a fun verbal cue ("Draw your sword!" = "Let's summarise!").

---

## 4. The Bushido Code of Summarising

A short "code" poster for the wall of the classroom/app home screen — five honour rules students recite or reflect on:

1. **Honour the truth** — never change what the story actually says.
2. **Discipline to cut** — a true samurai only keeps what matters.
3. **Clarity is strength** — a summary should be understood in one read.
4. **Speak with your own voice** — never just copy the original words.
5. **Practice makes mastery** — every small lesson makes you sharper.

---

## 5. The Three-Scroll Reading System

Every Bible story appears as **three parallel scrolls** — same story, same events, same names — written at three reading levels. Teachers/the app can assign the scroll appropriate to a student's reading level, independent of their samurai rank (a Rank 1 student can read Scroll III if they're a strong reader, etc.)

**New requirement: every scroll, at every level, is written in exactly THREE paragraphs — a beginning, a middle, and an end.** This is what makes the new 5-lesson cycle possible: Lessons 2, 3 and 4 of each story each focus on summarising one specific paragraph, so the paragraph breaks must line up across all three reading levels (Paragraph 1 always covers the same part of the story, whichever scroll the student reads).

| Scroll | Level | Style | Length |
|---|---|---|---|
| **Scroll I – Recruit Scroll** | Simple | Short sentences, common vocabulary | ~260–300 words across 3 short paragraphs (~85–105 words each) |
| **Scroll II – Warrior Scroll** | Intermediate | Slightly longer sentences, some descriptive language | ~380–420 words across 3 paragraphs (~125–150 words each) |
| **Scroll III – Master Scroll** | Advanced | Richer vocabulary, some compound/complex sentences | ~500–560 words across 3 paragraphs (~170–200 words each) |

> **Length update:** the bands above were widened so the gap between reading levels does more work — Scroll I (Simple) is now roughly the length the Advanced scroll used to be, Scroll III (Advanced) is now roughly double its old length, and Scroll II (Intermediate) sits at the midpoint between the new Scroll I and Scroll III. The *style* differences (sentence length/complexity, vocabulary) between the three levels are unchanged — only the amount of story detail and description each level carries has grown. Story 1 (Creation) has been rewritten to these new bands (see Section 13); every future story should follow the same widened bands.

**Example — David and Goliath (Scroll II – Warrior Scroll, shown in its three paragraphs):**

- *Paragraph 1 (Beginning):* "The Israelite army was afraid of a huge enemy soldier named Goliath, who challenged them to fight every day. Goliath was a champion of the Philistines, and no soldier in Israel's camp dared to face him."
- *Paragraph 2 (Middle):* "David, a young shepherd, arrived at the camp and believed God would help him defeat the giant. He refused the king's armour, choosing instead his sling and five smooth stones from the stream."
- *Paragraph 3 (End):* "David ran at Goliath and struck him down with a single stone. The Philistine army fled in fear, and the Israelite army was encouraged and won the battle that followed."

*(Every one of the 40 stories should be written this way: three reading levels, each broken into the same three paragraphs, so a "Paragraph 2 summary" lesson always targets the same story beat no matter which scroll a student is reading.)*

---

## 6. The Five-Lesson Story Cycle

Every one of the 40 stories is now taught across **five ~15-minute lessons**, so students read the whole story once, then spend a full lesson on each paragraph before finally pulling it all together. This is the biggest structural change from v1 (which taught a whole story, start to finish, in a single lesson).

| Lesson in cycle | Name | Purpose |
|---|---|---|
| **1 — Read & Understand** | The Whole Scroll | Student reads the *entire* story (all 3 paragraphs, at their assigned level) once, start to finish, with no summarising yet. The lesson ends with a short set of comprehension questions (who, what, where, what happened) to confirm they understood the story before any summarising begins. The Bushido Code is introduced/recapped here as the "why" of the whole cycle. |
| **2 — Summarise Paragraph 1** | Draw the Sword: The Beginning | Re-read paragraph 1 only. Work through S.W.O.R.D. (Search → Watch → Order → Remove → Deliver) on just that paragraph. Student produces a 1-sentence summary of paragraph 1. |
| **3 — Summarise Paragraph 2** | Draw the Sword: The Middle | Same S.W.O.R.D. process, applied to paragraph 2 only. Student produces a 1-sentence summary of paragraph 2. |
| **4 — Summarise Paragraph 3** | Draw the Sword: The End | Same S.W.O.R.D. process, applied to paragraph 3 only. Student produces a 1-sentence summary of paragraph 3. |
| **5 — The Full Scroll** | Bringing It Together | Student sees their own three paragraph-summaries from Lessons 2–4 side by side, and combines/polishes them into one 2–4 sentence summary of the *whole* story — cutting overlap, smoothing the join, checking it against the Bushido Code checklist (truth, cut, clarity, own voice). This is the "Master's Seal" moment for the story and where the XP/Scroll Stamp is earned. |

Within each of Lessons 2–4, the same short internal rhythm is used (a scaled-down version of the old single-lesson flow): **Katana Warm-Up** (30 sec recall) → **Re-read the paragraph** (1 min) → **The Way of Summary** (S.W.O.R.D. walkthrough, 5–7 min, scaffolding level depends on rank/phase) → **Dojo Challenge** (write the paragraph's 1-sentence summary, 2–3 min) → **Quick self-check** (1 min).

---

## 7. Scaffolding Progression (The Key Design Principle)

This is what makes the 200 lessons a real *progression* rather than 200 repeats of the same activity. Prompts are deliberately **removed** as students advance, forcing the skill to become internal.

| Phase | Stories | Lessons | Ranks | Scaffolding Level | What it looks like |
|---|---|---|---|---|---|
| **Phase 1 – Heavy Guidance** | 1–10 | 1–50 | 1–2 | Full scaffolding | Sentence starters given for each paragraph ("The main person was ___. The important thing that happened was ___."). Highlighting activity: student highlights only "important" words in the paragraph before writing. Teacher/app models one example first. |
| **Phase 2 – Guided Practice** | 11–20 | 51–100 | 3–4 | Medium scaffolding | Guiding questions only (no sentence starters): "Who? What happened? What can you cut?" Word-count target given per paragraph (e.g. "summarise this paragraph in 10 words or fewer"). |
| **Phase 3 – Light Touch** | 21–30 | 101–150 | 5–6 | Minimal scaffolding | One single prompt only per paragraph: "Draw your SWORD." Student plans and writes with no further help. Occasional self-check checklist. |
| **Phase 4 – Full Independence** | 31–40 | 151–200 | 7–8 | No scaffolding | Student reads each paragraph and summarises it with zero prompts, within a time limit (e.g. 90 seconds per paragraph). In final rank, students also *critique/improve* a sample summary — showing true mastery by being able to teach the skill. |

**Suggested general rule for the app:** track each student's accuracy across attempts. If a student consistently struggles at a given phase, the app can quietly re-offer one extra scaffold level before pushing them forward — keeping the "reduction of prompts" tied to competence, not just lesson number.

---

## 8. Sample Full 5-Lesson Cycle (Story 2 — Phase 1, "Noah's Ark")

*(This section was written as an illustrative design sample before Story 2 was actually authored; Story 2 — Noah's Ark — is now fully built in the app, with its own final wording, per Section 15. The sketch below is kept for reference but the shipped text differs slightly.)*

**Rank:** Apprentice Samurai | **Scroll:** I or II depending on reader

**Story text (Scroll II – Warrior Scroll), in its three paragraphs:**
- *Paragraph 1:* "God saw that the world had become full of wickedness, but Noah was a good man who obeyed Him. God told Noah to build a huge boat called an ark, because a great flood was coming."
- *Paragraph 2:* "Noah and his family gathered two of every kind of animal and brought them onto the ark. Then the rain began to fall, and it did not stop for forty days and forty nights, until the whole earth was covered in water."
- *Paragraph 3:* "At last the rain stopped and the water went down, and Noah's family and the animals came out onto dry land. God placed a rainbow in the sky as a promise that He would never flood the whole earth again."

**Lesson 6 (Read & Understand):** Student reads all three paragraphs straight through. Comprehension questions: Who is this story about? What did God tell Noah to do? What happened after the flood? No summarising yet.

**Lesson 7 (Summarise Paragraph 1):** Katana Warm-Up — "What's the first letter of SWORD stand for?" (Search). Re-read paragraph 1. Highlight who's in it (Search) and what happens (Watch). Sentence starter: "Noah built ___ because God told him ___." Dojo Challenge: write a 1-sentence summary of paragraph 1. Quick self-check.

**Lesson 8 (Summarise Paragraph 2):** Same rhythm, applied to paragraph 2. Circle the two biggest events in order (Watch + Order): animals enter ark → rain falls for 40 days. Cross out details that aren't needed in a summary, e.g. the exact wording "two of every kind" vs. just "the animals" (Remove). Sentence starter: "Then ___, and the flood ___." Dojo Challenge: 1-sentence summary of paragraph 2.

**Lesson 9 (Summarise Paragraph 3):** Same rhythm, applied to paragraph 3. Sentence starter: "In the end, ___." Dojo Challenge: 1-sentence summary of paragraph 3.

**Lesson 10 (The Full Scroll):** Student sees their three saved sentences from Lessons 7–9 side by side. They combine and smooth them into one 2–3 sentence summary of the whole story, checking it against the Bushido Code: Is it true to the story? Did I cut what didn't matter? Is it clear in one read? Is it in my own words? ✅ Earn a "Scroll Stamp" for completing the story.

---

## 9. The 40-Story Curriculum Map

Each rank uses **5** Bible stories (= 25 lessons), roughly progressing through the Bible narrative — giving the whole program a satisfying overarching story-of-the-Bible arc alongside the skill progression. This list was cut down from an earlier 80-story draft (10 stories/rank) to the strongest, most well-known, most teachable 5 stories per rank — trimming duplicated beats and less essential episodes so every slot earns its place. (Any story can still be swapped for denominational/curriculum preferences.) **All 40 stories, all 8 ranks, are now fully built in the app** — see Section 15.

### Rank 1 — Apprentice Samurai (Stories 1–5 / Lessons 1–25): Beginnings
1. Creation
2. Noah's Ark
3. Abraham's Call & Journey
4. Joseph's Coat & Dreams
5. Joseph Forgives His Brothers

### Rank 2 — Novice Swordsman (Stories 6–10 / Lessons 26–50): Exodus & Journey
6. Baby Moses in the Basket
7. Moses & the Burning Bush
8. Crossing the Red Sea
9. The Ten Commandments
10. Joshua & the Fall of Jericho

### Rank 3 — Disciplined Warrior (Stories 11–15 / Lessons 51–75): Judges & Early Kings
11. Gideon & the Fleece
12. Samson's Strength (told gently — focused on his God-given strength and calling as a judge; the final pillar scene is told as his last act of trust in God, without dwelling on his own death)
13. David & Goliath
14. David & Jonathan's Friendship
15. Solomon's Wise Judgement

### Rank 4 — Skilled Ronin (Stories 16–20 / Lessons 76–100): Prophets & Courage
16. Elijah on Mount Carmel
17. Shadrach, Meshach & Abednego
18. Daniel in the Lions' Den
19. Jonah & the Great Fish
20. Esther Becomes Queen

### Rank 5 — Trusted Retainer (Stories 21–25 / Lessons 101–125): The Life of Jesus Begins
21. The Birth of Jesus
22. The Shepherds & the Angels
23. John the Baptist
24. The Baptism of Jesus
25. Jesus Calls His First Disciples

### Rank 6 — Honoured Samurai (Stories 26–30 / Lessons 126–150): Parables
26. The Sower & the Seeds
27. The Good Samaritan
28. The Lost Sheep
29. The Prodigal Son
30. The Wise & Foolish Builders

### Rank 7 — Elite Samurai (Stories 31–35 / Lessons 151–175): Miracles & Encounters
31. Feeding the 5,000
32. Jesus Calms the Storm
33. Jesus Walks on Water
34. Zacchaeus the Tax Collector
35. Raising Lazarus (told with a focus on hope, faith, and joy rather than lingering on death or grief)

### Rank 8 — Master Samurai (Stories 36–40 / Lessons 176–200): The Greatest Story
36. The Last Supper
37. The Crucifixion (told gently, age-appropriately, focused on sacrifice & love)
38. The Resurrection
39. Doubting Thomas (told with a focus on hope, faith, and joy)
40. Pentecost & the Holy Spirit (capstone — students summarise the finished Bible arc independently as their "Master's Trial")

*Note: For Story 37 (The Crucifixion), keep language gentle and focused on themes of love, courage, and sacrifice rather than graphic detail — fully appropriate for the 9–12 audience.*

---

## 9B. The Japanese Legends Curriculum Map (Alternate Cycle)

Selected via the Christian/Japanese Legends toggle (Section 2.1). Uses the **same 8-rank skill ladder** as Section 9 (same belt colours, same summarising-skill focus per rank), but tells well-known Japanese folktales instead — chosen for strong name-recognition, a satisfying beginning/middle/end shape, and virtues that echo the Christian cycle's own arc (kindness, courage, gratitude, wisdom) without violence, blood, or weapons-on-people, matching the same content rules as Section 11.

**Vetted for a Christian-school setting:** since this app is used in a Christian school, every title below is a purely secular folktale — brave people, clever animals, kind strangers, magical creatures (kappa, tanuki, kitsune, tengu, dragons — treated as fantasy-story creatures, the same way a Western fairy tale uses elves or talking wolves, never as objects of worship). None of the 40 stories are myths about Shinto gods or goddesses (no Amaterasu, Susanoo, Izanagi/Izanami, Fujin/Raijin, or the Dragon King's divine court), and none retell a creation myth that could compete with Genesis — an earlier draft of this list included a few of those and they have been swapped out for equivalent secular legends (see Rank 4 #18, Rank 5 #21, and Rank 7–8 #33–37 below, all of which now feature ordinary human heroes instead). Two entries that reference an undersea "palace" purely as fantasy scenery (#9 Urashima Taro, #29 Why the Jellyfish Has No Bones) are written to be told as fantasy-kingdom stories, not as tales of a worshipped sea deity. **Stories 1–10 (Ranks 1–2) are now built in the app — see Section 15.1.** Each story below also has its **Story Scene image prompt** (matching the Section 11.D template, Master Style Block appended); built stories have had their image generated and wired in, and the remaining stories' prompts are ready for whenever they get built.

### Rank 1 — Apprentice Samurai (Stories 1–5 / Lessons 1–25): Foundation Tales ✅ *built*
1. **Momotaro (Peach Boy)** ✅ — *"A silhouetted young boy in simple clothing standing proudly beside a dog, a monkey, and a pheasant on a rocky shoreline, a small wooden boat behind them, a distant island with a fortress silhouette across the water, glowing sunrise circle behind the group."*
2. **Issun-boshi (One-Inch Boy)** ✅ — *"A tiny silhouetted boy no taller than a sewing needle, standing on a large lily pad with a chopstick as a paddle and a needle as a sword, a wide river and reeds around him, glowing sunset circle low on the horizon."*
3. **Shita-kiri Suzume (The Tongue-Cut Sparrow)** ✅ — *"A silhouetted old man kneeling gently in a bamboo grove, offering his hand to a small sparrow perched on his fingers, a simple thatched cottage in the background, glowing sunset circle behind the trees."*
4. **Hanasaka Jiisan (The Old Man Who Made the Trees Bloom)** ✅ — *"A silhouetted old man scattering ash from a small urn over a bare tree, blossoms bursting into silhouette bloom above him, a small dog sitting loyally at his feet, glowing sunrise circle behind the branches."*
5. **Kobutori Jiisan (The Old Man Who Lost His Lump)** ✅ — *"A silhouetted old man dancing joyfully in a forest clearing at dusk, a ring of small oni figures watching and clapping around him, glowing sunset circle behind the trees."*

### Rank 2 — Novice Swordsman (Stories 6–10 / Lessons 26–50): Gratitude & Kindness ✅ *built*
6. **Tsuru no Ongaeshi (The Crane Wife)** ✅ — *"A silhouetted crane mid-transformation into a woman's silhouette beside a simple loom in a wooden cottage doorway, wing-like fabric draped around her, glowing sunset circle through the window behind."*
7. **Kasa Jizo (The Grateful Statues)** ✅ — *"A silhouetted old man placing straw hats on a row of small stone statues lined up in the snow along a mountain path, glowing pale sunset circle low behind the hills."*
8. **Bunbuku Chagama (The Lucky Teakettle)** ✅ — *"A silhouetted tanuki (raccoon dog) mid-transformation into a bubbling teakettle with small paws and a tail, balanced on a low table in a simple room, glowing warm sunset circle through a paper screen window."*
9. **Urashima Taro** ✅ — *"A silhouetted young fisherman riding on the back of a large sea turtle beneath the waves, glowing sunset light filtering down through the water above them, a distant reef and cluster of sea plant silhouettes below."* (told as a pure fantasy undersea-kingdom story about the passage of time and keeping promises — no deity/ruler-worship framing)
10. **Kappa no Sara (The Kappa's Promise)** ✅ — *"A silhouetted kappa (river spirit) bowing at a riverbank beside a silhouetted farmer, a shallow dish balanced on the kappa's head, reeds and a glowing sunset circle reflected on the water."*

### Rank 3 — Disciplined Warrior (Stories 11–15 / Lessons 51–75): Cleverness & Wit
11. **Inaba no Shirousagi (The White Rabbit of Inaba)** — *"A silhouetted rabbit hopping lightly across the backs of a line of silhouetted crocodiles spanning a strait of water, a distant shoreline and glowing sunrise circle ahead."*
12. **The Boy Who Drew Cats** — *"A silhouetted boy sitting cross-legged in a temple hall, surrounded by many small silhouetted cat shapes he has drawn across the screens and walls, glowing sunset circle through an open doorway."*
13. **The Stonecutter** — *"A silhouetted stonecutter standing on a mountainside with his chisel, looking up at a huge glowing sunset circle framed between two peaks, simple tools resting at his feet."*
14. **Nezumi no Yomeiri (The Mouse's Wedding)** — *"Two silhouetted mice in tiny formal dress standing together on a garden stone, larger silhouettes of the sun, a cloud, the wind, and a wall stretching across the background sky, glowing sunset circle overhead."*
15. **Obasute Yama (The Wise Old Woman)** — *"A silhouetted young man carrying his elderly mother in a woven basket on his back up a mountain path at dusk, glowing sunset circle behind the peak above them."*

### Rank 4 — Skilled Ronin (Stories 16–20 / Lessons 76–100): Courage & Strength
16. **Kintaro (Golden Boy)** — *"A silhouetted young boy with a small axe over his shoulder, riding on the back of a bear through a forest clearing, other forest animals following behind, glowing sunrise circle through the trees."*
17. **Tawara Toda (The Rice-Bag Warrior)** — *"A silhouetted warrior standing calmly on a wooden bridge facing a huge coiled centipede silhouette stretching across distant mountains, glowing sunset circle behind the peaks."*
18. **Sannen Netaro (Three-Year Sleeping Taro)** — *"A silhouetted young man rising from a sleeping mat outside a simple farmhouse, effortlessly lifting a huge boulder above his head to redirect a rushing river, startled villagers watching from a distance, glowing sunrise circle behind him."*
19. **Yoshitsune and the Tengu of Mt. Kurama** — *"A silhouetted young boy practising with a wooden sword on a forest mountainside, a tall winged tengu figure with a long nose watching and guiding him, glowing sunset circle through the pine trees."*
20. **The Grateful Fox** — *"A silhouetted fox sitting attentively beside a small shrine gate (torii) at the edge of a village, a silhouetted farmer bowing respectfully nearby, glowing sunset circle behind the gate."*

### Rank 5 — Trusted Retainer (Stories 21–25 / Lessons 101–125): Wisdom & Patience
21. **Hachikazuki (The Princess with the Bowl on Her Head)** — *"A silhouetted young woman wearing a large wooden bowl over her head and shoulders, standing quietly in a garden as a nobleman's silhouette approaches, glowing sunset circle behind the garden trees."*
22. **Kaguya-hime (The Bamboo Princess)** — *"A silhouetted bamboo cutter kneeling before a glowing stalk of bamboo split open to reveal a tiny princess silhouette inside, a bamboo grove stretching into the distance, glowing sunset circle behind the stalks."*
23. **The Mirror of Matsuyama** — *"A silhouetted young girl kneeling before a small standing mirror in a simple room, her mother's gentle silhouette faintly visible behind her in the reflection, glowing sunset light through a paper window."*
24. **Omusubi Kororin (The Rolling Rice Ball)** — *"A silhouetted old man peering into a small round hole in a hillside where a rice ball has just rolled in, a line of tiny mouse silhouettes peeking out, glowing sunset circle behind the hill."*
25. **Warashibe Choja (The Straw Millionaire)** — *"A silhouetted young man walking a village road, holding a single strand of straw in one hand and leading a horse with the other, a simple house and glowing sunset circle in the distance ahead."*

### Rank 6 — Honoured Samurai (Stories 26–30 / Lessons 126–150): Structure & Consequence
26. **Yuki-onna (The Snow Woman)** — *"A silhouetted woman made of falling snow standing quietly in a snow-covered forest at dusk, cold pale-blue and pink gradient sky behind her, faint glowing moon overhead."*
27. **Kachi-kachi Yama (The Rabbit's Clever Lesson)** — *"A silhouetted rabbit paddling a small clay boat across a pond, a mischievous tanuki silhouette in a second, cracking boat nearby, glowing sunset circle reflected on the water."*
28. **Setsubun: The Night the Village Drove Away the Oni** — *"A silhouetted family standing in a doorway throwing handfuls of beans toward two fleeing oni silhouettes outside, glowing warm light from the house against a dusk sky."*
29. **Why the Jellyfish Has No Bones** — *"A silhouetted jellyfish drifting through a coral reef beside playful fish shapes, sunlight beams filtering down from the surface above, glowing warm sunset colour wash through the water."* (a light just-so animal-origin fable, not tied to any deity's court)
30. **The Two Frogs of Osaka and Kyoto** — *"Two silhouetted frogs standing on their hind legs atop a mountain pass, each looking toward a different distant city skyline, glowing sunset circle directly behind the peak between them."*

### Rank 7 — Elite Samurai (Stories 31–35 / Lessons 151–175): Loyalty & Honour
31. **Benkei and the Bridge at Gojo** — *"Two silhouetted warrior figures facing each other on a curved wooden bridge, one young and slight, one tall carrying a naginata pole-arm at rest, glowing sunset circle behind the bridge's railing."*
32. **Hachiko's Promise** — *"A silhouetted dog sitting patiently outside a train station entrance at dusk, silhouettes of commuters passing by in the distance, glowing warm station lights and a sunset sky behind."*
33. **Sarukani Gassen (The Monkey and the Crab)** — *"A silhouetted crab standing bravely beside a chestnut, a bee, and a large stone mortar, facing a startled monkey silhouette up in a persimmon tree, glowing sunset circle behind the branches."*
34. **Tokoyo and the Sea Serpent** — *"A silhouetted girl diving into the sea with a dagger at her side, a huge serpent silhouette coiling in the depths below her, glowing sunset light filtering down through the waves above."*
35. **Musashi and the Duel at Ganryu Island** — *"Two silhouetted swordsmen facing each other on a narrow sandy shoreline, one holding a long wooden sword carved from an oar, a small boat pulled up on the sand behind him, glowing sunrise circle low over the water."*

### Rank 8 — Master Samurai (Stories 36–40 / Lessons 176–200): Legacy & Mastery
36. **Ninomiya Sontoku: The Boy Who Read While He Worked** — *"A silhouetted young boy walking a mountain path with a large bundle of firewood strapped to his back, reading a small book held open in front of him as he walks, glowing sunrise circle over the hills behind."*
37. **Miyamoto Musashi's Final Lesson** — *"A silhouetted older swordsman kneeling calmly in a dojo courtyard, a circle of young student silhouettes seated respectfully around him, two wooden swords resting on the ground between them, glowing sunset circle through the dojo gateway."*
38. **The Legend of Mount Fuji** — *"A silhouetted elixir jar resting on a mountain summit with a thin trail of smoke rising into the sky, the huge silhouette of Mount Fuji's peak below, glowing sunrise circle beside the mountain."*
39. **Kintoki: Kintaro Grown Tall** — *"A silhouetted adult warrior in simple armour standing atop a mountain ridge, the faint silhouette of a bear sitting beside him, glowing sunset circle behind the ridge line — a grown echo of Story 16."*
40. **Momotaro's Legacy: The Treasure Shared** *(capstone — students summarise the whole Japanese Legends arc independently as their "Master's Trial")* — *"A silhouetted village gathering at dusk, a young man surrounded by a dog, a monkey, and a pheasant handing baskets of treasure to a crowd of villager silhouettes, glowing sunset circle over the rooftops behind them."*

---

- **XP & Scroll Stamps:** 1 stamp per completed Dojo Challenge; visual scroll fills up across each rank.
- **Belt Ceremony Screen:** Every 10 lessons, an animated "belt promotion" moment with new belt colour and badge.
- **Streak Flame:** Small icon that tracks consecutive days practised (gentle, non-punishing — pauses rather than resets on a missed day).
- **Master's Wall:** A gallery where a student's best summaries (self-selected or teacher-selected) are displayed like trophies/scrolls on a dojo wall.
- **Final Certification:** Lesson 200 ends with a printable/digital **"Master Samurai of Summary" certificate**, with the student's name in calligraphy-style font.

---

## 11. Image Prompts — Silhouette Sunset Anime Style (School-Appropriate — No Violence/Blood/Weapons-on-people)

All artwork follows one consistent art direction, inspired by bold graphic-novel-style anime posters: flat black silhouettes, almost no interior linework, set against a glowing gradient sky, with a huge sun or moon behind the subject. Figures are recognisable purely by shape and pose. Swords/armour may appear as *silhouette costume shapes only* — never mid-action, never aimed at another figure.

**Master Style Block** — paste this at the end of every prompt below to keep the whole app visually consistent:

> *"...bold anime poster illustration, subject rendered as a near-solid black silhouette with minimal interior detail, backlit against a large glowing circular sun/moon, dramatic gradient sky (deep purple fading to sunset orange, pink, and dusk blue), soft pale cream clouds, layered silhouetted mountains in the background, flat graphic shapes, high contrast, warm cinematic lighting, clean vector-style linework, no gore, no weapons in use, school-appropriate, children's educational app art style."*

**Palette reference (for consistency across every image):**
- Deep dusk purple — `#4B2E83`
- Sunset orange — `#E8734A`
- Sunset pink/magenta — `#D94F70`
- Dusk sky blue — `#3E6FA6`
- Pale cream (clouds/highlights) — `#F4E9D8`
- Silhouette black — `#14100D`

### A. Character Progression (Mascot growth across ranks)
1. *"A young samurai apprentice, silhouetted, wearing a simple headband with trailing ties, standing in three-quarter profile holding a writing brush in one hand and a rolled scroll tucked under the other arm, in front of a traditional wooden building with a hanging banner bearing a simple flower crest, distant mountains and a pagoda silhouette on the horizon, calm confident pose."* + Master Style Block
2. *"Same young samurai apprentice character, now with a small yellow sash/belt visible as a silhouette accent, standing beside a low wooden table with an open scroll, slightly more upright and confident stance, cherry blossom petals drifting through the air as small dark shapes."* + Master Style Block
3. *(Repeat for each rank, swapping only the belt-accent colour — orange, green, blue, purple, brown, black — and gradually straightening the posture and adding a second small silhouette detail such as a satchel of scrolls, until Rank 8:)* *"...an older, composed Master Samurai silhouette in a flowing ceremonial kimono with a black sash, seated cross-legged on a low platform, one hand raised gently as if teaching, a smaller apprentice silhouette seated respectfully nearby, scrolls stacked beside them."* + Master Style Block

### B. Rank Badges / Belt Icons (for UI)
4. *"A circular badge icon: a simplified silhouette of a folded scroll tied with a ribbon in [white/yellow/orange/green/blue/purple/brown/black], set against a small glowing sunset-gradient circle background (purple-orange-pink), thin cream ring border, flat vector app-icon style, no text."*
5. *"A circular emblem icon featuring a silhouetted writing brush crossed behind a scroll, in [belt colour] as an accent line only, sunset-gradient circular background, clean flat vector app icon."*

### C. Dojo Backdrops (per rank, for lesson screen backgrounds)
6. *"A wide background illustration of a traditional Japanese dojo exterior at dusk, rendered as layered silhouettes (roofline, paper-screen windows, a hanging banner), glowing orange-pink sun low behind the building, gradient purple-to-blue sky, pale cream clouds, no people, calm and inviting, flat graphic poster style."*
7. *"A wide background illustration of a Japanese garden at sunset — a silhouetted wooden bridge over a still pond, silhouetted cherry blossom trees framing the edges, a glowing sun reflected on the water, layered mountain silhouettes in the distance, gradient dusk sky, no people, flat graphic poster style."*
8. *"A wide background illustration of a distant silhouetted castle and pagoda skyline along a shoreline, huge glowing sunset circle behind them, layered blue-pink mountains, calm water with soft reflections, gradient purple-orange-blue sky, no people, flat graphic poster style."*

### D. Story Scene Template (generic, reusable per Bible story)
9. *"A silhouetted scene depicting [insert Bible story moment, e.g. 'a young shepherd figure standing calmly before a much larger silhouetted figure across an open field' / 'a silhouetted figure and companions walking beside two-by-two animal silhouettes toward a large wooden vessel'], simple recognisable poses, glowing sunset/sunrise circle as the focal light source behind the main figures, layered silhouetted landscape in the background, no faces or fine detail needed, no violence, no blood, school-appropriate."* + Master Style Block
   - *(Reuse this template for each of the 40 stories — describe only the single key visual moment as clean, readable silhouette shapes, e.g. "a silhouetted figure with arms raised over a parted sea," "a small silhouetted boy figure offering a basket to a seated crowd of silhouettes on a hillside.")*

### E. UI / Decorative Elements
10. *"A single scroll icon rendered as a solid black silhouette shape tied with a thin cream cord, sitting in front of a small glowing sunset-gradient circle, minimal flat vector style, suitable for a loading icon."*
11. *"A thin decorative border pattern of silhouetted cherry blossom branches and drifting petal shapes along the edges, sunset-gradient colour wash behind them, for framing a certificate, no text included."*
12. *"A small flat icon of a silhouetted paper lantern glowing warmly from within, set against a tiny sunset-gradient circle, for use as a 'streak' or 'daily practice' icon."*

### F. Certificate Artwork
13. *"An elegant certificate background: a wide, softly glowing sunset-gradient sky (purple to orange to blue) across the top third, a thin line of layered silhouetted mountains and a distant pagoda along the bottom edge, plenty of open cream space in the centre for a name and calligraphy-style title, celebratory and warm, no weapons or violent imagery, suitable for a children's achievement certificate."*

---

## 12. Quick Build Checklist

- [x] Write all 40 stories in 3 scroll levels each, each scroll broken into exactly 3 matching paragraphs (120 total text pieces) — **all 40 stories (Story 1–40) are done**
- [x] Build the 8 mascot progression images — generated as one 8-panel sheet (Section 11.A), sliced into individual images, and wired into the 8 rank cards on the landing page
- [x] Build the 8 dedicated rank *badge* icon assets (Section 11.B — small circular UI badges, separate from the mascot progression art above) — generated, sliced, and wired into every rank card
- [x] Build the 3 dojo backdrop images (Section 11.C) — generated and wired in as background art behind the lesson header, Presentation Mode, and the rank ladder section
- [x] Build the Story Scene Template (Section 11.D) for all 40 built stories (1–40) — generated, compressed to webp, and wired in as `STORY_SCENES_CHRISTIAN[idx]`, shown as a hero banner in the lesson panel and swapped by `setActiveStory()`
- [x] Build the 5-lesson story-cycle template (Read & Understand → Paragraph 1 → Paragraph 2 → Paragraph 3 → Full Scroll) — built and playable for Story 1 (Creation); still a one-off build for this story, not yet a reusable component other stories can be pushed into (see Section 15)
- [ ] Implement scaffolding-phase logic (Phase 1–4) tied to rank, adjustable by performance
- [ ] Build XP/Scroll Stamp + Belt Ceremony animation
- [ ] Build Master's Wall gallery feature
- [ ] Build final certificate generator for Lesson 200 completion — the decorative border art (Section 11.E, item 11) is now generated, compressed, and embedded as `CERTIFICATE_BORDER_B64`, ready to use, but the generator itself is still unbuilt
- [ ] Pilot-test the full 5-lesson cycle for Story 1, 11, 21, 31 (one per phase) with real 9–12 year-olds before building the rest
- [x] Print button on each lesson's reading (differentiated scrolls, one page per level, Name/Date line) — built for Lesson 1
- [x] "Print all readings" button that scales automatically as new stories are added to `STORY_DATA` — now prints all 40 built stories back to back (120 pages)
- [x] Stories 2–40 pushed into `STORY_DATA`, so both print buttons cover all 40 built stories without extra wiring
- [x] Teacher lesson plan (with NZC Years 5–6 links, via the refreshed Phase 2 English Learning Area) + its own print button — built for Lesson 1
- [ ] Write a teacher lesson plan for Lessons 2–5 of Story 1, and for every future story, following the Lesson 1 template (NZC links, learning intention, success criteria, differentiation, 5-step teaching notes, assessment, extension/support)
- [x] Presentation Mode: a full-screen, teacher-controlled slideshow version of Lesson 1, for classes running the lesson entirely on paper — built for Lesson 1
- [x] Printable student worksheet (the offline paper version of the comprehension check, retell, and Master's Seal) with an on-screen preview modal — built for Lesson 1
- [x] Extend Presentation Mode + the printable worksheet to Lessons 2–5 of Story 1 — done; every lesson now has its own Presentation Mode deck and worksheet
- [x] Extend Presentation Mode + the printable worksheet + the 5-lesson cycle to Stories 2–5, following the Story 1 pattern — done, via the new `STORIES` array + `setActiveStory()` architecture (see Section 15)
- [x] Extend the same pattern to Stories 6–10 (Rank 2, "Novice Swordsman") — done, with zero architecture changes: just 5 more entries pushed into `STORIES_CHRISTIAN` plus their 5 Story Scene images (see Section 15)
- [x] Extend the same pattern to Stories 11–20 (Rank 3, "Disciplined Warrior," and Rank 4, "Skilled Ronin") — done, with zero architecture changes: just 10 more entries pushed into `STORIES_CHRISTIAN` plus their 10 Story Scene images (see Section 15)
- [x] Extend the same pattern to Stories 21–30 (Rank 5, "Trusted Retainer," the Life of Jesus Begins, and Rank 6, "Honoured Samurai," Parables) — done, with zero architecture changes: just 10 more entries pushed into `STORIES_CHRISTIAN` plus their 10 Story Scene images (see Section 15)
- [x] Extend the same pattern to Stories 31–40 (Rank 7, "Elite Samurai," Miracles & Encounters, and Rank 8, "Master Samurai," The Greatest Story) — done, with zero architecture changes: just 10 more entries pushed into `STORIES_CHRISTIAN` plus their 10 Story Scene images (see Section 15). **The 40-story Bible Stories curriculum is now 100% complete, all 8 ranks.**
- [x] Build out the Japanese Legends curriculum's Stories 1–10 (Rank 1, "Apprentice Samurai," Foundation Tales, and Rank 2, "Novice Swordsman," Gratitude & Kindness) — done, with zero architecture changes: Stories 2–10 (Issun-boshi, Shita-kiri Suzume, Hanasaka Jiisan, Kobutori Jiisan, Tsuru no Ongaeshi, Kasa Jizo, Bunbuku Chagama, Urashima Taro, Kappa no Sara) pushed into `STORIES_JAPANESE` following the exact `story_content_6to10.py`-style shape, and Story 1 (Momotaro) got its first-ever Story Scene image alongside 9 new ones for Stories 2–10, replacing the old `STORY_SCENES_JAPANESE = [null]` placeholder. Urashima Taro (#9) is told as a pure fantasy undersea-kingdom story about the passage of time and keeping promises, per the Section 9B vetting note (no deity/ruler-worship framing). **10 of the Japanese Legends curriculum's 40 stories are now built (Ranks 1–2 complete); Stories 11–40 remain.**

---

## 13. Web App Design System (as built — v1)

This section documents the actual design decisions made in the first working build of the app (landing page + Lesson 1 demo), so future lessons and screens stay visually consistent.

### Typography (v2 — replaced the original "Hero Block" system)

The original build used a single custom display font ("Hero Block", a soft rounded block sans) for every heading, paired with Inter for body/UI text. That was replaced because it read as too soft/whimsical against the cinematic, poster-style samurai artwork — the page wanted something taller, sharper and more condensed to match. The new system:

| Role | Typeface | Used for | Notes |
|---|---|---|---|
| **Display / titles** | **Teko** (Google Font) | Hero title, section titles, rank titles, lesson titles, step names, modal headers, the SWORD letters | Tall condensed display face designed for headlines/posters, giving the Japanese-poster feel the artwork calls for. Weights 500/600/700 embedded (woff2, base64 — no external request, matching the offline-first pattern already used for images). The hero title itself uses two different weights for contrast: "Summarise" at 600, "like Samurais" at 500 (with "Samurais" bumped to 700 for emphasis within the line) — and "like Samurais" was sized up significantly from the original build so it reads as part of the title lockup rather than a secondary line. |
| **UI chrome** | **Barlow Condensed** (Google Font) | All buttons, toolbar buttons, tab pills, nav CTA, presentation-mode nav/exit buttons, small uppercase kicker labels | New third tier, sitting between the tall display face and the body copy — condensed like the headings but at UI weights (400/500/600 embedded, woff2 base64), so buttons and labels feel part of the same poster-like system without competing with actual reading text. |
| **Body / reading text** | **Inter** | Paragraphs, worksheet/comprehension text, the fill-in-the-blank and textarea inputs, all long-form running text | Deliberately left untouched and *not* condensed — the point of the new system is contrast between a dramatic, condensed title/UI layer and a plain, highly legible body face for anything a student actually has to read closely. Loaded from Google Fonts, weights 400–800. |
| **CJK accents** | **Shippori Mincho B1** | The 侍 watermark, the 一二三四五六七八 rank/rule numerals, "Scroll stamp earned" badge text | Unchanged — neither Teko nor Barlow Condensed has CJK glyphs, so these stay pinned to this font. Loaded from Google Fonts, weights 400/700. |

Three CSS variables now drive this: `--font-display` (Teko), `--font-ui` (Barlow Condensed), `--font-body` (Inter) — swapping any one of the three only requires changing that variable's `@font-face` block and value, not hunting through every rule.

### Wordmark & heading emphasis (as implemented)

- The brand/wordmark is now styled **"summarise `like` samurais"** — "like" set in lowercase, "Summarise" and "Samurais" both bold, with "Summarise" set at a visibly larger size than "Samurais" so the eye lands on the skill (summarising) before the theme (samurais). Now rendered in Teko, matching the hero.
- All section titles (`.section-title`) and their eyebrow labels (`.section-label`) are set heavier than the original build — section titles moved from weight 400 to weight 700, eyebrow labels to 800 — so the page reads with a clearer visual hierarchy on scroll.

### Colour tokens (as implemented in CSS custom properties)

| Token | Hex | Role |
|---|---|---|
| `--purple` | `#4B2E83` | Core palette — dusk sky top, accents |
| `--purple-deep` | `#2C1B4D` | Darker purple for gradients/depth |
| `--orange` | `#E8734A` | Core palette — sun glow, primary accent, hover states |
| `--pink` | `#D94F70` | Core palette — sunset mid-tone |
| `--blue` | `#3E6FA6` | Core palette — dusk sky bottom |
| `--blue-deep` | `#213F5F` | Darker blue for gradients/depth |
| `--cream` | `#F4E9D8` | Core palette — text on dark, scroll paper background |
| `--ink` | `#14100D` | Core palette — page background, text on cream |
| `--ink-soft` | `#231C17` | Card/panel background, one step lighter than page background |

**Belt colours** (extended from the palette to cover all 8 ranks — the brief's core 6-colour palette didn't include a yellow, green, or brown, so these three were added in the same muted, dusk-toned register rather than pure/saturated hues):

| Rank | Belt | Hex |
|---|---|---|
| 1 | White | `#F4E9D8` (= cream) |
| 2 | Yellow | `#E3B23C` (dusty gold, added) |
| 3 | Orange | `#E8734A` (= core orange) |
| 4 | Green | `#6B8F5E` (muted sage, added) |
| 5 | Blue | `#3E6FA6` (= core blue) |
| 6 | Purple | `#8A5FBF` (lighter purple, added for contrast against the dark purple background) |
| 7 | Brown | `#8A5A34` (warm brown, added) |
| 8 | Black | `#14100D` (= core ink) |

### Printing & Teacher Lesson Plans (as implemented)

Every built lesson now ships with three tools in a toolbar directly under the lesson header (above the step progress dots):

| Button | What it does |
|---|---|
| **🖨️ Print this reading** | Opens the browser's print dialog with a clean, black-on-white printout of the *current story's* three differentiated scrolls (Scroll I, II, III), each on its own page, each with the beginning/middle/end paragraphs, a word count, and a Name/Date line so it can double as a student handout at whichever reading level suits them. |
| **🖨️ Print all readings** | Prints every built story's readings back to back (one story = three pages, one per scroll level). Now prints all 40 built stories (120 pages total) — the code loops over the `STORY_DATA` array, which is derived from `STORIES`. |
| **📋 Teacher lesson plan** | Opens a modal with a full teacher-facing lesson plan for that lesson: NZ Curriculum links, learning intention, success criteria, context, materials, differentiation guidance for the three scrolls, a step-by-step walkthrough matching the five in-app steps (with teacher talk moves and "look for" formative-assessment notes), assessment opportunities, and extension/support ideas. Has its own **🖨️ Print lesson plan** button inside the modal, which prints just that content as a clean paper lesson plan. |

**How printing works technically:** a single hidden `#printArea` div sits at the end of `<body>`, empty by default (`display:none`). Each print button builds an HTML string (reading pages, or a clone of the lesson-plan modal body) and drops it into `#printArea`, then calls `window.print()`. A print-only `@media print` stylesheet hides everything else on the page and shows only `#printArea`, so the browser's print/PDF output only ever contains the reading or lesson plan — never the app chrome. `#printArea` is cleared again after printing (`afterprint` event).

**Print font sizes (page-count constrained):** the `@media print` stylesheet was re-tuned so printed output hits fixed page targets rather than growing with content: **each differentiated Scroll (I/II/III) fits on exactly one page** (Scroll III, the longest at ~534 words, was the binding case), and **every lesson's Student Worksheet fits within two pages** — in practice all five lessons currently land on a single page each, so a worksheet prints as one sheet (one side, or double-sided with a blank back). Paragraph text prints at 15px, story titles at 26px, worksheet body copy at ~12.5–13px, and so on — see the `@media print` block in the CSS for the full list.

A second, easy-to-miss fix was needed alongside the font shrink: the print rule originally used `visibility:hidden` on the rest of the page (`body *{visibility:hidden;}`) with `#printArea` pulled out via `position:absolute`. That keeps every hidden element's layout box in the document flow, so the *invisible* full-length landing page was still what determined the PDF's page count — shrinking the print fonts alone had no effect. The fix was to switch to `body > *{display:none !important;}` (which removes layout entirely) for every top-level element except `#printArea`, so the print output's height is driven only by the printed content itself. `.print-ws .ws-checklist{page-break-inside:avoid;}` was also added so a worksheet's final checklist never gets split across a page boundary.

**NZ Curriculum links used (Years 5–6):** the app now cites the **refreshed** English Learning Area, *Phase 2 (Years 4–6)*, which came into effect **1 January 2026** and replaced the old "curriculum level 3" framework for these year groups. The Lesson 1 plan links to the Phase 2 Reading strand's Comprehension-strategies content — specifically the Year 5 and Year 6 "summarising" practice statements, plus the making-inferences/connections and text-structure practices — and frames Lesson 1 (which deliberately has no summarising yet) as the comprehension foundation that those summarising practices are built on. Source: Ministry of Education, *NZC – English Phase 2 (Years 4–6)*, on Tāhūrangi (https://newzealandcurriculum.tahurangi.education.govt.nz/nzc---english-phase-2/5637238346.p). **Build note:** as more lessons are added, their lesson plans should keep citing this same Phase 2 page (or Phase 3, Years 7–8, if the app is ever extended past Year 6) rather than the old 8-level NZC structure, since that's what's officially in force for schools now.

### Hero & rank artwork — status

Image Prompt **A.1** from Section 11 ("A young samurai apprentice, silhouetted...") has already been generated and is in use as the site's hero artwork — the apprentice with the writing brush, rolled scroll, headband, and dojo/banner backdrop. It's embedded directly in the page (webp, base64) so the app works fully offline with no broken image links.

A second image — the apprentice seated at a low writing table with brushes and an open scroll, same silhouette style — is now embedded too, used as the cover art for **Presentation Mode**'s title slide and its closing "Master's Seal" slide.

The **8-rank mascot progression** (Section 11.A) has been generated as a single 8-panel contact sheet, one pose per rank in order, sliced into 8 individual images, and wired into the rank ladder on the landing page — each of the 8 rank cards now shows its own illustration instead of just a belt-colour dot.

**Rank Badges (Section 11.B)** — generated as a single 4×2 contact sheet (one scroll-and-ribbon badge per belt colour, white through black), auto-cropped to each circular badge, compressed to webp, and embedded base64. These now sit in the `belt-dot`'s old spot on every rank card (`.rank-top`), at 28px with a **2.5px ring in that rank's own belt colour** layered over the artwork — keeping the at-a-glance colour-coding the flat dot used to provide, while upgrading it to real artwork. Wired via a new `RANK_BADGES` array (same pattern as the existing `RANK_IMAGES` mascot array).

**Dojo Backdrops (Section 11.C)** — all three generated (dojo exterior, garden bridge, castle/pagoda shoreline), resized to ~900px wide and compressed to webp (~40–60KB each), embedded base64, and wired in as background art rather than left unused:
- **Dojo exterior** → sits behind every `.lesson-header` bar (the "Lesson 1 of 5: Creation — Read & Understand" strip), under the existing purple/orange gradient, which was darkened slightly (0.5→0.78 / 0.28→0.55 opacity) so the header text stays fully legible over the scene.
- **Garden bridge** → sits behind the whole Presentation Mode overlay, layered under the existing purple-to-blue gradient (also darkened slightly for legibility) so the full-screen teaching view has real depth instead of a flat gradient.
- **Castle/pagoda shoreline** → sits behind the `#ranks` landing-page section (the "Eight ranks, one path" ladder), under a near-opaque dark overlay (`rgba(20,16,13,0.92–0.96)`) so it reads as subtle atmosphere rather than a competing image.

Since `.lesson-header` and `.pm-overlay` are shared classes, both backdrops apply automatically to all 5 lessons — no per-lesson wiring needed.

**Story Scenes (Section 11.D) — now generated and wired in for all forty built Bible Stories, and for all ten built Japanese Legends stories.** A silhouette hero illustration was generated for **Story 1 (Creation)**, **Story 2 (Noah's Ark)**, **Story 3 (Abraham's Call & Journey)**, **Story 4 (Joseph's Coat & Dreams)**, **Story 5 (Joseph Forgives His Brothers)**, **Story 6 (Baby Moses in the Basket)**, **Story 7 (Moses & the Burning Bush)**, **Story 8 (Crossing the Red Sea)**, **Story 9 (The Ten Commandments)**, **Story 10 (Joshua & the Fall of Jericho)**, **Story 11 (Gideon & the Fleece)**, **Story 12 (Samson's Strength)**, **Story 13 (David & Goliath)**, **Story 14 (David & Jonathan's Friendship)**, **Story 15 (Solomon's Wise Judgement)**, **Story 16 (Elijah on Mount Carmel)**, **Story 17 (Shadrach, Meshach & Abednego)**, **Story 18 (Daniel in the Lions' Den)**, **Story 19 (Jonah & the Great Fish)**, **Story 20 (Esther Becomes Queen)**, **Story 21 (The Birth of Jesus)**, **Story 22 (The Shepherds & the Angels)**, **Story 23 (John the Baptist)**, **Story 24 (The Baptism of Jesus)**, **Story 25 (Jesus Calls His First Disciples)**, **Story 26 (The Sower & the Seeds)**, **Story 27 (The Good Samaritan)**, **Story 28 (The Lost Sheep)**, **Story 29 (The Prodigal Son)**, **Story 30 (The Wise & Foolish Builders)**, **Story 31 (Jesus Feeds the Five Thousand)**, **Story 32 (Jesus Calms the Storm)**, **Story 33 (Jesus Walks on Water)**, **Story 34 (Zacchaeus the Tax Collector)**, **Story 35 (Jesus Raises Lazarus)**, **Story 36 (The Last Supper)**, **Story 37 (The Crucifixion)**, **Story 38 (The Resurrection)**, **Story 39 (Doubting Thomas)**, and **Story 40 (Pentecost and the Holy Spirit)**, each resized to 900px wide and compressed to webp (~53–65KB each), embedded base64 as `STORY_SCENES_CHRISTIAN[idx]`, and shown as a full-width hero banner in the "Story one: the full five-lesson cycle" panel, right above the lesson tabs, swapping automatically with `setActiveStory()` as the Story tab changes. The Lesson 1 Presentation Mode slide also picks up the same image for its opening slide. All 40 Bible Stories now have a Story Scene hero image.

**Japanese Legends Story Scenes (Stories 1–10) were added in the same pass.** Momotaro (Story 1) got its first-ever scene image (a boy standing with a dog, monkey, and pheasant on a rocky shoreline), and Stories 2–10 (Issun-boshi, Shita-kiri Suzume, Hanasaka Jiisan, Kobutori Jiisan, Tsuru no Ongaeshi, Kasa Jizo, Bunbuku Chagama, Urashima Taro, Kappa no Sara) each got theirs too, all resized to 900px wide and compressed to webp (~60–65KB each), embedded base64 as `STORY_SCENES_JAPANESE[idx]`, replacing the old `[null]` placeholder. The collapse-cleanly behaviour (no broken image, no empty gap) stays in place as a safeguard for the remaining Japanese Legends stories (11–40) that don't have one yet.

**Certificate border art (Section 11.E, item 11) is now embedded** as `CERTIFICATE_BORDER_B64` (900×600 webp, ~37KB, cherry-blossom branch/petal frame around empty cream space, no text) — ready for a future certificate generator to use, but that generator itself still doesn't exist; see the Quick Build Checklist. The rest of the UI/Decorative Elements (E — loading icon, streak icon) and the remaining Certificate Artwork (F) were also generated but still aren't wired in, since the features they belong to (a loading state, an XP/streak system, the certificate generator) haven't been built.

### What's built so far

- Landing page: hero, Bushido Code of Summarising, SWORD method (interactive), rank ladder (all 8 ranks, now illustrated — see above). Titles and subtitles are set heavier/bolder than the original build, "Summaries for Samurais" is fully bold, "Summaries" is set larger than "SAMURAIS", and "like" is lowercase in the wordmark.
- Forty full interactive lesson demos — the complete curriculum, one per story, each with the full 5-lesson cycle: **Story 1 — Creation**, **Story 2 — Noah's Ark**, **Story 3 — Abraham's Call & Journey**, **Story 4 — Joseph's Coat & Dreams**, **Story 5 — Joseph Forgives His Brothers** (Rank 1, "Apprentice Samurai," Phase 1 heavy scaffolding), **Story 6 — Baby Moses in the Basket**, **Story 7 — Moses & the Burning Bush**, **Story 8 — Crossing the Red Sea**, **Story 9 — The Ten Commandments**, **Story 10 — Joshua & the Fall of Jericho** (Rank 2, "Novice Swordsman," same Phase 1 scaffolding), **Story 11 — Gideon & the Fleece**, **Story 12 — Samson's Strength**, **Story 13 — David & Goliath**, **Story 14 — David & Jonathan's Friendship**, **Story 15 — Solomon's Wise Judgement** (Rank 3, "Disciplined Warrior"), **Story 16 — Elijah on Mount Carmel**, **Story 17 — Shadrach, Meshach & Abednego**, **Story 18 — Daniel in the Lions' Den**, **Story 19 — Jonah & the Great Fish**, **Story 20 — Esther Becomes Queen** (Rank 4, "Skilled Ronin"), **Story 21 — The Birth of Jesus**, **Story 22 — The Shepherds & the Angels**, **Story 23 — John the Baptist**, **Story 24 — The Baptism of Jesus**, **Story 25 — Jesus Calls His First Disciples** (Rank 5, "Trusted Retainer," the Life of Jesus Begins), **Story 26 — The Sower & the Seeds**, **Story 27 — The Good Samaritan**, **Story 28 — The Lost Sheep**, **Story 29 — The Prodigal Son**, **Story 30 — The Wise & Foolish Builders** (Rank 6, "Honoured Samurai," Parables), **Story 31 — Jesus Feeds the Five Thousand**, **Story 32 — Jesus Calms the Storm**, **Story 33 — Jesus Walks on Water**, **Story 34 — Zacchaeus the Tax Collector**, **Story 35 — Jesus Raises Lazarus** (Rank 7, "Elite Samurai," Miracles & Encounters), and **Story 36 — The Last Supper**, **Story 37 — The Crucifixion**, **Story 38 — The Resurrection**, **Story 39 — Doubting Thomas**, **Story 40 — Pentecost and the Holy Spirit** (Rank 8, "Master Samurai," The Greatest Story). A Story tab bar switches between them; each story's Lesson 1 has the student read the whole three-paragraph story once and answer comprehension questions, with no summarising yet (that starts in Lessons 2–4). Every story is written in three matching paragraphs across all three reading levels, at the widened word-count bands in Section 5.
- **Print & teacher tools, for every built story:** a "Print this reading" button (prints the current story's three differentiated scrolls, one per page), a "Print all readings" button (prints all 40 built stories back to back via the `STORY_DATA` array), and a "Teacher lesson plan" button opening a full NZC-linked lesson plan (Years 5–6, Phase 2 English) for the current story and lesson, with its own print option. See "Printing & Teacher Lesson Plans" above for details.
- **Offline/paper delivery, for every built story:** a "🖥️ Presentation Mode" full-screen slideshow and a "📝 Print worksheet" student handout, both rebuilt per story/lesson on open — see Section 14, "Presentation Mode & Offline Worksheets," for full details.
- **The full five-lesson cycle for Stories 1–40, and the `STORIES`/`setActiveStory()` multi-story architecture** — see Section 15 for full details. **The 40-story Bible Stories curriculum (all 8 ranks) is now 100% complete.**
- Not yet built: the belt ceremony animation, XP/streak systems, Master's Wall gallery, the final certificate generator, and the remaining 30 Japanese Legends stories (Section 9B; Stories 1–10, Ranks 1–2, now have their full interactive cycle built) — see the Quick Build Checklist in Section 12

---

## 15. The Full Five-Lesson Cycle, and the Multi-Story Architecture (Stories 1–40, complete)

This is the newest layer: all forty stories — Creation, Noah's Ark, Abraham's Call & Journey, Joseph's Coat & Dreams, Joseph Forgives His Brothers (Rank 1), Baby Moses in the Basket, Moses & the Burning Bush, Crossing the Red Sea, The Ten Commandments, Joshua & the Fall of Jericho (Rank 2), Gideon & the Fleece, Samson's Strength, David & Goliath, David & Jonathan's Friendship, Solomon's Wise Judgement (Rank 3), Elijah on Mount Carmel, Shadrach Meshach & Abednego, Daniel in the Lions' Den, Jonah & the Great Fish, Esther Becomes Queen (Rank 4), The Birth of Jesus, The Shepherds & the Angels, John the Baptist, The Baptism of Jesus, Jesus Calls His First Disciples (Rank 5), The Sower & the Seeds, The Good Samaritan, The Lost Sheep, The Prodigal Son, The Wise & Foolish Builders (Rank 6), Jesus Feeds the Five Thousand, Jesus Calms the Storm, Jesus Walks on Water, Zacchaeus the Tax Collector, Jesus Raises Lazarus (Rank 7), and The Last Supper, The Crucifixion, The Resurrection, Doubting Thomas, Pentecost and the Holy Spirit (Rank 8) — each have their **full five-lesson cycle** built, wired together, and playable end to end, and the app was refactored so any of them can be switched into the same five lesson panels on demand. Stories 6–10, 11–20, 21–30, and 31–40 were each added on top of the exact same architecture with zero code changes — only new content and new Story Scene images each time. **This completes the 40-story, 8-rank, 200-lesson Bible Stories curriculum.**

### The Story tab bar

A new row of tabs sits above the lesson tabs, one per built story ("Story 1 · Creation" through "Story 20 · Esther Becomes Queen"). Clicking one calls `setActiveStory(idx)`, which re-points every module-level data variable at that story and re-renders the whole lesson demo in place — the lesson tab bar underneath it always resets back to Lesson 1 on a story switch, so the student always lands on "Read & Understand" for whichever story they just picked. At 20 tabs, `.story-tabs-nav{flex-wrap:wrap}` continues to reflow the row cleanly across multiple lines with no horizontal scroll or overflow, so no extra CSS was needed for this pass either.

### The Lesson tab bar

Above the lesson demo (below the story tabs), five tabs ("Lesson 1" through "Lesson 5") switch which lesson is shown; only one is visible at a time (`.lesson-instance.active-lesson`). Each lesson is its own self-contained block with its own header, toolbar, stepper, and steps — switching tabs doesn't lose anything already typed in another lesson, since each lesson's inputs save to their own `localStorage` key as the student types (the same autosave pattern Lesson 1's retell box already used).

### Lessons 2–4: one S.W.O.R.D. pass per paragraph

Each of these three lessons targets exactly one paragraph (Lesson 2 → the Beginning, Lesson 3 → the Middle, Lesson 4 → the End) and walks the same five-step rhythm described in Section 6 of this document:

1. **Katana Warm-Up** — a short recall of the S.W.O.R.D. letters. Lesson 2's warm-up also names the current story by title, generated from a stored template with the title swapped in on every story switch.
2. **Re-read the paragraph** — the same three-scroll-level tabs as Lesson 1, but showing only that one paragraph.
3. **Draw the S.W.O.R.D.** — all five moves against just that paragraph: **Search** (tap the real character out of a set of character/place/thing options), **Watch + Order** (tap four events into sequence), **Remove** (tap the phrases that could be cut from a summary), and **Deliver** (a sentence-starter fill-in-the-blank, matching the Phase 1 heavy-scaffolding rule in Section 7 for Ranks 1–2).
4. **Dojo Challenge** — a one-sentence summary of that paragraph, saved automatically under a story-scoped key (e.g. `ssl_story1_lesson2_summary`, `ssl_story2_lesson2_summary`, …).
5. **Quick self-check** — a 2-item checklist and a stamp reveal, distinct per lesson ("First/Second/Third SWORD drawn").

### Lesson 5: The Full Scroll

Brings the story home in four steps:

1. **Your three S.W.O.R.D.s** — reads back the three saved sentences from Lessons 2–4 via `localStorage`, one card per paragraph. A student who hasn't done Lessons 2–4 yet sees "Not written yet — complete Lesson N first" instead of blank cards.
2. **Combine & Polish** — a "Start from my three sentences" button pre-fills the textarea by joining the three saved sentences, which the student then edits down into one smooth 2–4 sentence summary. (Tested end to end: writing summaries in Lessons 2–4, switching to Lesson 5, and confirming the recap and the pre-fill both pick up the saved text — including after a full page reload, since it's backed by `localStorage`.)
3. **Bushido Checklist** — all four Bushido rules (not just three), checked off against the finished summary.
4. **Master's Seal** — the closing "Story N complete!" moment, with a preview line naming the next built story by title (or "coming soon" once Story 20's cycle finishes, since Story 21 isn't built yet).

### Teacher tools extended to all five lessons, for every built story

The **Teacher Lesson Plan**, **Presentation Mode**, and **printable Worksheet** are shared across all five lessons *and* all five stories, with their content rebuilt on open from whichever story tab and lesson toolbar button was clicked:

- `buildLessonPlanBody(n)` returns a full NZC-linked lesson plan for lesson `n` of the current story — Lesson 1's plan pulls the story's title and its first two `searchWords` (the convention across every story: the first two entries in `searchWords`/`PARA_LESSONS[n].search` are always the correct character answers, decoys after) into its "Look for" formative-assessment note; Lessons 2–4 each get a plan built around that paragraph's Search/Order/Remove content; Lesson 5's plan covers combining and the Bushido checklist as its rubric, and its closing line looks up the *next* story in `STORIES` to preview by name.
- `pmSlidesForLesson(n)` returns the Presentation Mode slide deck for lesson `n` — Lessons 2–4 share one 8-slide template parameterised by paragraph data; Lessons 1 and 5 read the current story's title dynamically for their title/closing slides.
- `buildWorksheetBody(n)` returns the printable/on-screen worksheet for lesson `n` — Lessons 2–4 share a template with Search/Order/Remove/Deliver/self-check sections; Lesson 1's "Retell It" prompt and Lesson 5's "Master's Seal" line both use the current story's title/number.
- `buildStoryPrintPages(story)` (unchanged) still powers both "Print this reading" (now `STORY_DATA[currentStoryIdx]`, so it prints whichever story tab is open) and "Print all readings" (still `STORY_DATA.map(...)`, so it now prints all 30 built stories back to back — 90 pages, one per scroll level per story).

### The multi-story architecture: `STORIES` + `setActiveStory()`

Story 2 onward needed a real data-driven refactor, not just more content, so the app now has:

- **`STORIES_CHRISTIAN`** (live-aliased as `STORIES` while the Bible Stories curriculum is active) — an array of 40 objects (one per built story, the complete curriculum), each holding `storyNumber`, `title`, `scrolls` (the `{I, II, III}` three-paragraph text), `searchWords`, `orderEvents`, `factStatements`, and `para` (keyed `"2"`/`"3"`/`"4"`, each with `label`, `search`, `order`, `remove`, and `starter` — the exact fill-in-the-blank HTML for that paragraph's Deliver step). Story 1's entry is the original Creation content, copied over unchanged; Stories 2–5 come from the content authored in `story_content.py` (Noah's Ark, Abraham's Call & Journey, Joseph's Coat & Dreams, Joseph Forgives His Brothers); Stories 6–10 come from `story_content_6to10.py` (Baby Moses in the Basket, Moses & the Burning Bush, Crossing the Red Sea, The Ten Commandments, Joshua & the Fall of Jericho); Stories 11–20 come from `story_content_11to20.py` (Gideon & the Fleece, Samson's Strength, David & Goliath, David & Jonathan's Friendship, Solomon's Wise Judgement, Elijah on Mount Carmel, Shadrach Meshach & Abednego, Daniel in the Lions' Den, Jonah & the Great Fish, Esther Becomes Queen); Stories 21–30 come from `story_content_21to30.py` (The Birth of Jesus, The Shepherds & the Angels, John the Baptist, The Baptism of Jesus, Jesus Calls His First Disciples, The Sower & the Seeds, The Good Samaritan, The Lost Sheep, The Prodigal Son, The Wise & Foolish Builders); Stories 31–40 come from `story_content_31to40.py` (Jesus Feeds the Five Thousand, Jesus Calms the Storm, Jesus Walks on Water, Zacchaeus the Tax Collector, Jesus Raises Lazarus, The Last Supper, The Crucifixion, The Resurrection, Doubting Thomas, Pentecost and the Holy Spirit).
- **`currentStoryIdx`** — which story is active (starts at `0`).
- **`scrolls`, `searchWords`, `orderEvents`, `factStatements`, `PARA_LESSONS`** — these are still the same module-level variables every helper function (`buildParaScrollTabs`, `buildToggleChips`, `buildOrderChips`, `pmParagraphSlide`, etc.) already reads, but they're now *live pointers* re-assigned to `STORIES[currentStoryIdx]`'s data on every story switch, rather than one-off constants. Because the helper functions read these variables at call time (not at function-definition time), reassigning them is enough to make every already-built helper story-aware with no changes to the helpers themselves.
- **`setActiveStory(idx)`** — the function the story tabs call. It reassigns the five pointers above, updates the `.lesson-tag`/`.lesson-title` text in all 5 `.lesson-instance` panels, resets Lesson 1's scroll level and rebuilds its comprehension chips, updates Lesson 2's warm-up text and every lesson's `.starter-box` HTML, rebuilds the Search/Order/Remove chip rows for Lessons 2–4, recomputes Lesson 5's recap keys and re-renders its recap grid, and resets the lesson tab bar back to Lesson 1.
- **Story-scoped `localStorage` keys** — every saved input (retell, the three paragraph summaries, the combined summary) is now keyed `ssl_story{N}_lesson{M}_{type}` via a small `ssKey(storyNum, lessonNum, type)` helper, so nothing a student types in one story ever bleeds into another. `initDojoInput` was changed to read its storage key live off `input.dataset.storageKey` (set/updated by `setActiveStory`) instead of a closed-over constant, and exposes a `loadFromStorage()` method on the input so `setActiveStory` can re-sync the field's value (and its word counter) after swapping the key.
- **`STORY_DATA`** (used for printing) is now derived with `STORIES.map(...)` instead of being hand-written, so it always mirrors the 30 built stories with no duplication.

Tested end to end (Stories 1–5): cycling through all 5 story tabs × all 5 lesson tabs (25 combinations) with zero console/JS errors; typing in Story 1's retell box, switching to Story 2 and confirming its retell box is empty, then switching back to Story 1 and confirming the earlier text persisted (and that only `ssl_story1_...`/`ssl_story2_...` keys existed in `localStorage`, never a shared one); and printing both the reading and worksheet for Story 1 and Story 3, confirming the same page-count limits from Section 13 still hold (each scroll level still fits one printed page, each worksheet still fits within 2 pages) now that the print HTML is generated from per-story data instead of one hard-coded story.

Re-tested end to end after adding Stories 6–10 (Rank 2): all 10 story tabs render with the correct title/tag/scene image/comprehension chips/S.W.O.R.D. content for each story, with zero console/JS errors; `localStorage` keys stayed correctly scoped per story (`ssl_christian_story6_...` through `ssl_christian_story10_...`, no bleed into Stories 1–5 or into each other); toggling to the Japanese Legends curriculum and back to Bible Stories still works and correctly resets to Story 1; and printing the reading (all 3 levels) and worksheet for Stories 6, 8, and 10 confirmed the same page-count limits still hold (each scroll level fits one printed page — 3 pages total per story reading — and each worksheet fits within 2 pages), even though a couple of the new Level III ("Master Scroll") paragraphs run a bit longer than Stories 1–5's word-count band.

Re-tested end to end again after adding Stories 11–20 (Rank 3, "Disciplined Warrior," and Rank 4, "Skilled Ronin"): `node --check` on the extracted `<script>` passes cleanly; the `STORIES_CHRISTIAN` array parses as valid JS with all 20 entries in order (`storyNumber` 1–20) and the array's shape verified server-side before the file was touched further; with Playwright (chromium), all 20 story tabs render, and clicking through tabs 11–20 confirmed each one's title/tag/hero scene image/comprehension chips/S.W.O.R.D. exercises/recap render correctly with zero console/JS errors; `localStorage` keys stayed correctly scoped per story (confirmed via each lesson input's `data-storage-key`, e.g. `ssl_christian_story11_lesson1_retell` vs. `ssl_christian_story20_lesson1_retell`, with no bleed between any of the 20 stories); toggling to the Japanese Legends curriculum (Momotaro still works, one tab) and back to Bible Stories still correctly restores all 20 tabs and resets to Story 1; and print-testing (pypdf) the reading (all 3 levels) and Lesson 1 worksheet for Stories 12, 15, 17, and 20 confirmed the same page-count limits still hold (each scroll level fits one printed page — 3 pages total per story reading — and each worksheet fits within 2 pages). A few of the new Level III ("Master Scroll") paragraphs were trimmed during authoring (from as high as ~660 words down to ~520–590 words per story) to stay within the same per-page print budget as Stories 1–10, following the same word-tightening approach used previously — cutting redundant phrasing while preserving every story beat.

Re-tested end to end again after adding Stories 21–30 (Rank 5, "Trusted Retainer," the Life of Jesus Begins, and Rank 6, "Honoured Samurai," Parables): `node --check` on the extracted `<script>` passes cleanly; the `STORIES_CHRISTIAN` array parses as valid JS with all 30 entries in order (`storyNumber` 1–30) and the array's shape verified server-side both before and after injection into `app.html`; with Playwright (chromium), all 30 story tabs render, and clicking through tabs 21–30 confirmed each one's title/tag/hero scene image/comprehension chips/S.W.O.R.D. exercises/recap render correctly with zero console/JS errors; `localStorage` keys stayed correctly scoped per story (confirmed via `ssKey()`'s `story{storyNum}` naming, e.g. `ssl_christian_story21_lesson1_retell` vs. `ssl_christian_story30_lesson1_retell`, with no bleed between any of the 30 stories); toggling to the Japanese Legends curriculum (Momotaro still works, one tab) and back to Bible Stories still correctly restores all 30 tabs and resets to Story 1; and print-testing (pypdf, with Playwright's `page.pdf(print_background=True)`) the reading (all 3 levels) and Lesson 1 worksheet for Stories 22, 25, 28, and 30 confirmed the same page-count limits still hold (each scroll level fits one printed page — 3 pages total per story reading — and each worksheet fits within 2 pages) with no Level III trimming needed this round, as every new story's Master Scroll was authored within the ~480–560 word band from the start.

### Build notes for Stories 31–40 (Rank 7 "Elite Samurai" and Rank 8 "Master Samurai") — the final batch

Stories 31–40 were added with no architecture changes at all, confirming the design held right through to the last entry: each new story was written to the same `story_content.py`-style shape (`scrolls` in 3 levels × 3 matching paragraphs, `searchWords`/`orderEvents`/`factStatements` as plain strings, and `para["2"/"3"/"4"]` with `label`/`search`/`order`/`remove`/`starter`), appended to the `STORIES_CHRISTIAN` array, and given one more Story Scene image. Nothing in `setActiveStory()`, the lesson-plan/worksheet/presentation builders, or `STORY_DATA` needed to change — they all already read from `STORIES` generically, and the Story tab bar (`.story-tabs-nav{flex-wrap:wrap}`) reflowed automatically at all 40 tabs, with no extra CSS needed.

Content-sensitivity notes followed for this batch (see Section 11): Story 37 (The Crucifixion) is told gently, focused on Jesus's choice, love, and sacrifice rather than graphic detail — the sky darkening and the Temple curtain tearing carry the dramatic weight instead of any physical description of suffering. Story 35 (Raising Lazarus) and Story 39 (Doubting Thomas) are told with a focus on hope, faith, and joy rather than lingering on death or grief.

Re-tested end to end after adding Stories 31–40: `node --check` on the extracted `<script>` passes cleanly; the `STORIES_CHRISTIAN` array parses as valid JS with all 40 entries in order (`storyNumber` 1–40); with Playwright (chromium), all 40 story tabs render, and clicking through tabs 31, 34, 37, and 40 confirmed each one's title/hero scene image (`.has-image` on `#storyScene`)/comprehension fact chips (4 per story) render correctly with zero console/JS errors (ignoring expected sandbox network/font blocks); toggling to the Japanese Legends curriculum (Momotaro still works) and back to Bible Stories still works correctly; and print-testing (pypdf, with Playwright's `page.pdf(print_background=True)`) the reading (all 3 levels) and Lesson 1 worksheet for Stories 37 and 40 confirmed the page-count limits held with no trimming needed (3 pages total per story reading, one per scroll level; worksheet within 2 pages) — every new story's Master Scroll was authored well inside the established per-page print budget from the start.

**With this batch, the 40-story Bible Stories curriculum is complete: all 8 ranks, all 40 stories, all 200 lessons, fully built, playable, and printable.**

### Build notes for Japanese Legends Stories 1–10 (Rank 1 "Apprentice Samurai" and Rank 2 "Novice Swordsman")

Stories 2–10 (Issun-boshi, Shita-kiri Suzume, Hanasaka Jiisan, Kobutori Jiisan, Tsuru no Ongaeshi, Kasa Jizo, Bunbuku Chagama, Urashima Taro, Kappa no Sara) were authored to the same `scrolls`/`searchWords`/`orderEvents`/`factStatements`/`para` shape as `STORIES_JAPANESE[0]` (Momotaro) and `STORIES_CHRISTIAN`, with `factStatements` as plain strings (not `[text, bool]` tuples — verified against the live `app.html` shape before writing any content, since an earlier batch elsewhere had made that mistake). All 9 new stories were appended to `STORIES_JAPANESE` via a surgical `str.replace` injection anchored on Momotaro's closing `starter` string, with `app.html` backed up first (`app.html.bak_before_jp_2to10`). Story 1 (Momotaro) also got its first-ever Story Scene image in this batch — `STORY_SCENES_JAPANESE` was `[null]` before this pass and now holds all 10 images (Momotaro through Kappa no Sara), replacing the placeholder entirely. Urashima Taro (Story 9) was written as a pure fantasy undersea-kingdom story about the passage of time and keeping promises, per the Section 9B Christian-school vetting note — the Dragon Palace and its princess are fantasy-story scenery, never framed as a worshipped sea deity or divine court.

Level III ("Master Scroll") word counts needed active trimming during authoring: several early drafts ran 700–840 words, well above the established per-page print budget (Story 6 "Baby Moses in the Basket," at 635 words, was the previous highest safely-printing precedent), so every Level III paragraph set was tightened down to roughly 550–680 words per story through several rounds of cutting redundant modifiers and appositive phrases while preserving every plot beat, then re-verified word-by-word before injection.

Re-tested end to end after adding Japanese Legends Stories 1–10: `node --check` on the extracted `<script>` passes cleanly; the `STORIES_JAPANESE` array parses as valid JS with all 10 entries in order (`storyNumber` 1–10); with Playwright (chromium), the curriculum toggle correctly shows 10 story tabs for Japanese Legends, and clicking through tabs 1 (Momotaro), 2 (Issun-boshi), 6 (Tsuru no Ongaeshi), and 10 (Kappa no Sara) confirmed each one's title renders, its Story Scene now shows (`.has-image` on `#storyScene` — including Momotaro, which had no image before this batch), and its comprehension fact chips render (4 per story, via `#factChips .chip`), all with zero console/JS errors (ignoring expected sandbox network/font blocks); toggling back to Bible Stories confirmed all 40 Christian stories still render correctly with their scene images intact (regression check, since that curriculum was already 100% complete and needed to stay that way); and print-testing (pypdf, with Playwright's `page.pdf(print_background=True)`) the reading (all 3 levels) and Lesson 1 worksheet for Stories 6 and 9 confirmed the page-count limits held (3 pages total per story reading, one per scroll level; worksheet within 2 pages) with no further trimming needed after the authoring-stage word-count work above.

**With this batch, 10 of the Japanese Legends curriculum's 40 stories are built (Ranks 1–2, all with Story Scene art); Stories 11–40 (Ranks 3–8) remain to be written.**

---

## 14. Presentation Mode & Offline Worksheets (as implemented)

This is the newest layer on top of Lesson 1: a way to run the *entire* lesson without students ever touching a device. The app becomes the teacher's front-of-room display and paper generator; the students' only tool is a pencil.

### Why this exists

The original in-app Lesson 1 walks one student through five steps on their own screen (warm-up → read → comprehension check → retell → seal). That's great for 1:1 or small-group device use, but a teacher running a whole class from one shared screen or projector needed a different shape: something to *display* while the class works on paper together, plus paper for students to actually write on. Presentation Mode and the printable worksheet are that second shape — they don't replace the interactive lesson, they sit alongside it as an offline delivery option for the same content.

### 🖥️ Presentation Mode

A new toolbar button opens a full-screen overlay (`#presentationOverlay`) that turns Lesson 1 into a 10-slide, teacher-controlled deck:

1. **Title** — Lesson/story/rank info, the writing-desk illustration, and an instruction to hand out the worksheet and printed Scroll first.
2. **Bushido rule one** ("Honour the truth") with a discussion prompt.
3–5. **The three paragraphs** (Beginning/Middle/End), shown at whichever scroll level the teacher picks — see below — each with its own discussion prompt.
6–8. **The three comprehension checks** (Who / Order / True-or-False), presented as talking points rather than tappable chips, each pointing back to the matching section of the printed worksheet.
9. **Retell it** — the instruction slide for the paper retelling.
10. **Master's Seal** — the three success-criteria questions, the standing-apprentice illustration, and a transition line into Lesson 2.

Controls: **Next / Back** buttons, the **Left/Right arrow keys**, a slide counter ("3 / 10"), and an **Exit** button or the **Escape** key to leave. A **scroll-level switcher** (I / II / III) sits in the top bar so the teacher can display whichever reading level matches the group in front of them — the paragraph slides re-render instantly when it's changed, reusing the same `scrolls` data as the interactive lesson and the print buttons, so there's only one place the story text is ever written.

### 📝 Print worksheet (offline lesson)

A second new toolbar button opens a preview modal (styled like a paper scroll, matching the printed-reading look) showing the **paper half** of Lesson 1 — everything the interactive version normally does on-screen once reading is done:

- Name/date line
- The Bushido rule one reminder
- The "who is this story about" character list, to circle
- The four story events, each with a number box, to sequence 1–4
- The four true/false statements, each with TRUE/FALSE to circle
- Nine ruled lines for the "retell it in your own words" writing task
- The three Master's Seal checkboxes

It's deliberately *not* the story text itself — that's already covered by the existing "Print this reading" button, so a teacher pairs the two: the differentiated Scroll for reading, and this worksheet for everything after reading. The modal's own **🖨️ Print worksheet** button prints just this content, sized to fit within **two printed pages per student** (all five lessons currently print to a single page each), so a worksheet is one sheet of paper — one side, or the back of the printed Scroll if double-siding. See "Print font sizes (page-count constrained)" in Section 13 for how the sizing was tuned.

### Build notes for extending this to future lessons/stories

Both features are wired to the same underlying data (`scrolls`, `searchWords`, `orderEvents`, `factStatements`, the Bushido `codeItems`) that the interactive lesson and the print buttons already use, so there's no duplicated story content anywhere. As Lessons 2–5 of Story 1 (and every future story) are built:

- Presentation Mode's slide list (`pmSlides`) will need a version per lesson type — Lessons 2–4 (single-paragraph S.W.O.R.D. work) will need different slide content than Lesson 1 (whole-story read) or Lesson 5 (bringing it all together).
- The worksheet builder (`buildWorksheetBody`) will need an equivalent per-lesson version — e.g. Lessons 2–4's worksheet should have space to draw the SWORD, not a comprehension check.
- Once more than one story/lesson exists, both features should take a lesson/story argument the way `buildStoryPrintPages(story)` already does, rather than being hard-coded to Story 1 / Lesson 1 as they are today.

---

## 16. Splitting Out the Story Scene Images (Three-File Structure)

Once the Bible Stories curriculum reached 40 stories and Japanese Legends reached 10, the single `app.html` file had grown past 5.7MB, almost all of it base64-encoded Story Scene images inline inside the one `<script>` block. GitHub was reporting a problem with a file that size, so the two big image arrays were extracted out into their own `.js` files:

- **`data-bible-scenes.js`** holds `var STORY_SCENES_CHRISTIAN = [...]` — all 40 Bible Stories hero images, in the same base64 data-URI array format as before, indexed to match `STORIES_CHRISTIAN`.
- **`data-japanese-scenes.js`** holds `var STORY_SCENES_JAPANESE = [...]` — all 10 (soon 40) Japanese Legends hero images, indexed to match `STORIES_JAPANESE`.
- **`app.html`** dropped to roughly 1.6MB. Its `<head>` now loads both files as plain global scripts, before its own inline `<script>` runs:
  ```html
  <script src="data-bible-scenes.js"></script>
  <script src="data-japanese-scenes.js"></script>
  ```
  Because these are ordinary `<script src>` tags (not `fetch`/`XHR`/ES module imports), this works identically over `file://` (double-clicking `app.html` locally) and over `http(s)://` (GitHub Pages, Netlify, any static host) — there's no CORS restriction on script tags the way there is on `fetch()` from `file://`.

**Deployment rule going forward:** all three files must be uploaded to GitHub (or wherever the app is hosted) **in the same folder**, with those exact filenames. If `app.html` is uploaded alone, or the two data files are missing/misnamed, the app still loads and every lesson still works — only the Story Scene hero images will be blank, because the arrays they read from (`STORY_SCENES_CHRISTIAN`/`STORY_SCENES_JAPANESE`) simply won't exist yet.

**Build rule going forward:** every future batch of Story Scene images should be appended directly to the matching external file (`data-bible-scenes.js` or `data-japanese-scenes.js`), not embedded back into `app.html` — this is what keeps `app.html` itself small and fast to open, even as the curriculum grows toward 80 total stories (40 + 40) and their images.

---

*Domo arigato — happy building! May your students summarise with the discipline, clarity, and honour of a true samurai.* 🗾
