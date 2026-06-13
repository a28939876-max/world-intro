# Polish rules + the challenge-list taxonomy

From real launches; each rule has a "why" and a "how." (P4 of the pipeline.)

## 1. De-cluster the timestamps

**Symptom**: every case and data source is dated the same day.
**Why fix**: readers instantly read "built in a day," which *lowers* credibility.
**How**:
- Case body: `2026-06-12 morning` → `one morning`; `In 2026-06 we …` → `the time we did … for …`.
- Data-source section: keep only the method (which script, which two objects, reproducible), no dates.
- Relative time inside the story can stay ("that afternoon" — narratively coherent, no absolute date leaked).
- At the methodology level, still require "reports carry a query timestamp" — that's a rule you teach others.

## 2. Aphorism voice → plain words

**Symptom**: dressed-up maxims in the body ("X is the cheapest kind of fake prosperity," "it went from A to B in one C").
**Why fix**: readers want information, not rhetoric; a posed sentence costs you in technical docs.
**How** (real rewrites):
- "fork count is the cheapest fake prosperity" → "fork counts look busy but mean the least — the fork button takes a second to click…"
- "renaming is the enemy of diff" → "a derivative renames a file and the diff stops lining up"
**Boundary**: titles may stay literary (a flavorful-but-instantly-clear line is fine); the first-screen hook story may stay. What you flatten is the body.

**Diction calibration (the personification trap)**: for things a company/org produces, don't use person-like phrasing ("author credit," "give credit back to the author"). Use "the maintainer info / the official source / official release." Example: a repost stripped the license and **maintainer info**, not "erased the author's credit."

## 3. Case-scale phrasing

**Symptom**: the README/cases imply "there are only these N cases total."
**How** (three layers):
- Under the hook, in parentheses: "cases/ holds N typical picks from many — there have been far more."
- Top of the case list: "these N are typical, not all; new ones get added."
- First line of each case's data-source note: "this is one typical pick from many real runs."

## 4. Charts & cover

- Prefer native platform rendering for data charts (GitHub: mermaid flowchart / graph / xychart-beta / pie) — zero image assets, versioned with the content, never a dead link.
- Every number in a chart must be real (from acceptance data) — leave it out before you fake it.
- A cover image is produced separately (use an anti-slop design tool if you have one), placed in assets/, centered at the top of the README.
- Each case with a figure gets a "(figure attached)" note in the README case table, prompting readers to click in.
- **An evidence shot with exact text (repo names / star counts / labels) must be HTML-rendered then screenshot, never a text-to-image model** (it garbles them); screenshot a `file://` URL with headless Chrome — never start an http.server to screenshot (a server-root vs file-location mismatch screenshots a 404 page). That evidence shot doubles as the first-screen "input → output" image (see §10).

## 5. The "what's it for" section

- Position: after the hook story, before the technical intro.
- The first screen leads with one audience (ask the user which), formatted as a table: "your situation → what it does for you," about three rows.
- Secondary audiences get one line ("also serves x, y, z"), not expanded.
- Follow with a first-person paragraph "how we use it ourselves": real usage + "the cases were collected exactly this way" + a plain-spoken close. Credibility comes from the fact of "used it first, open-sourced it after."
- The framework file's (e.g. SKILL.md) description mirrors the value phrasing: not just trigger conditions, but "what you get from using it."

## 6. The challenge-list taxonomy (three tiers)

Before publishing, ask "how will outsiders attack this," list it in three tiers, present to the user to name:

- **Tier 1 · must answer**: things that shake the foundation ("tool X already does this — what's new?", "your core check has an obvious blind spot"). Response: write it into the README body or a "pairs well with" note up front, don't wait to be found out.
- **Tier 2 · can harden**: partial answers worth strengthening (false-positive rate, coverage, gameable signals). Response: an FAQ Q&A — concede + show the defense.
- **Tier 3 · bikeshed**: keep a one-liner ready, don't put it in the doc (naming taste, out-of-scope platforms, wording preference).

Discipline: present the list, the user **names which to handle**; leave the un-named alone. FAQ tone = concede the fact + explain the defense + pin the positioning boundary, no excuses.

## 7. Polish cadence

- Each round of user feedback = one commit; the message says what changed this round.
- Restate the user's edits as a point-by-point plan before acting (confirm understanding, prevent drift).
- When the user invites questions, ask "true-intent" level (audience, voice), not execution detail.
- Selection-type changes (swap a case, shift the narrative center) get a plan + a nod first; wording changes you just do.

## 8. Case selection & viewpoint (relatable first)

**Symptom**: the case is a developer-jargon need ("a tool that audits skill quality"), or the viewpoint is on "how clever our mechanism is."
**Why fix**: a case is a mirror for the target audience — the reader has to see themselves in the need. A clever mechanism lands less than "I also want to build a journaling app."
**How**:
- The lead case picks a need ordinary people "have all the time, can state in a sentence": build an app, make a deck, install a model, keep notes.
- Each case opens with the **need verbatim** (in quotes), viewpoint pinned to "what the user got," the mechanism only peeking through in the result.
- Developer-facing / meta / big-name-validation cases get **demoted to an "advanced" subsection**: merged into one paragraph at the back, validation value kept, not stealing the stage.

## 9. Real-backfill discipline

**Rule**: every case and every result line in the doc must come from a real pipeline run.
- Pick the topic (confirm with user) → run 2–3 keyword passes per need for real → backfill the doc with **what was actually found** (names, maintainer, standout features, check verdict).
- A topic that produces a weak result gets **swapped on the spot** — no hardcoding; this is itself the honesty principle.
- The surprises from a real run are often the best material: a false-positive you reviewed by hand, copy clusters in the results — write them up as living examples.
- After backfill, put one line prominently in the README: "every line above was produced by really running this tool."

## 10. Persuasion-first structure (the README first-screen paradigm)

The whole page answers two questions: **what's it for, how do I use it.** Fixed order:

1. **Cover + a one-line soul** (slogan/idea line). Follow with **one English positioning line** (for international/HN traffic — one line that states the tool's boundary, e.g. `Find the safest and most useful variant of an X before you Y.`).
2. **One "input → output" screenshot**: left input (a need / an object), right output (the tool's real result) — faster than any prose. This is the §4 evidence shot. Pair it with **cutting a `v0.1.0` release** — a repo with no release looks unfinished.
3. **Sample blocks ×3–4 (first screen)** — each a three-part shape:
   ```
   ### "the need, verbatim"
   > original plan / expectation / sticking point: one line with a sense of the gap.
   **Result**: its own paragraph, what was actually found/done (the fun is in the gap between gripe and result).
   ```
   The gripe must appear in the README body, not buried in a case detail page.
4. **How to use: three steps** (install → say one thing → what it does), quick-start hoisted to screen two.
5. **A "without it vs with it" table**: translate features into the user's felt gains.
6. A first-person "we use it ourselves" paragraph.
7. Only then the technical detail (flow diagram, tool table), case index, FAQ, honesty note.
