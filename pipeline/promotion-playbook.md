# Promotion playbook (P6): shipping isn't the finish line

From the promotion stage of real launches. A repo pushed with star=0 that nobody knows about = not open-sourced. This chapter is about getting it **seen, understood, and wanted**. **Promotion is an outbound action — like P5, it passes a user gate: copy and images get a look-over, and only post per-platform after confirmation.**

## 0. See how the comparables promote (same search discipline as P0)

Before writing any copy, revisit the P0 competitors: **do they have a Twitter, an image-feed presence, a tech blog, a newsletter? what do they post, in what tone, which post did well?** Most active open-source projects have at least one channel. This step decides two things: which platforms you cover, and what the comparable content looks like. A lane with no channels is itself an opening.

## 1. Narrow the value prop: one sentence, one hook

- **Compress the core value to one sentence**, built as "the user's situation + the pain you kill" — no feature pile.
  - Too-broad: "search, group, identify origin, safety-check, install — all in one."
  - Narrowed: "you say what you want to do, and it rounds up the tools for you — no more hunting."
- **The opening must have a hook**: the first line / first image states the biggest selling point or the sharpest pain. Readers decide in three seconds whether to scroll past.
- Once the value prop is confirmed with the user, **every platform's copy and every image rallies around it** — don't let one say "finds everything" and another say "strong safety check"; it dilutes.

## 2. Copy discipline: plain, real, reviewed

Each platform's body passes two gates: **a de-AI-slop pass + a code-model review against the rules**. Feed the hard rules below to the reviewer **as ground truth** and have it score line-by-line and point to violations:

- No more than 3 consecutive "one-sentence short paragraphs"; merge short bits into full paragraphs of action/reaction/causation.
- Don't lean on connective filler ("therefore / however / meanwhile / right after / the next second / if you will / which means").
- No piling of jargon and high-abstraction words; plain words where plain words work.
- Don't overuse em-dashes, contrast constructions, or over-tidy parallel clauses (these are AI-slop tells).

**Story material**: the opening hook uses **one specific, slightly interesting real episode**, told in more detail — **don't lift the repo's cases/ verbatim as "my story"** (those are for the README; reposting reads as lazy). Pick the story around the core value: leading on "finds the whole field" → tell one real search; leading on "saves time" → tell one real time-save.

Cadence as in P4: the user flags an issue → fix → run it back through the de-slop/review pass → show the user, loop until they nod.

## 3. Images: three types, three ways to make them

| Type | Job | How to make it | Key discipline |
|---|---|---|---|
| **Concept art** | the value / the pain (before-after, a round-up) | a text-to-image tool, one consistent storybook style | minimal text, carry meaning in the picture; one style throughout |
| **Evidence shot** | the real run result (repo names, stars, grouping, check verdict) | **render HTML, then screenshot — never text-to-image** | see ★ below |
| **Banner / cover** | the repo + per-platform headers | a graphic-design tool or text-to-image | one main banner, re-cropped per platform |

★ **Why the evidence shot must be HTML-rendered**: text-to-image models **garble or invent** repo names, numbers, and labels. Anything with exact text gets: write HTML (reuse the banner palette) → screenshot a `file://` URL with headless Chrome (`chrome --headless=new --screenshot --force-device-scale-factor=2 "file://$PWD/x.html"`). **Never start a local http.server and screenshot it** — if the server root and the HTML location differ you'll screenshot a 404 error page (a real launch shipped an `evidence.png` that was a 19KB screenshot of a 404 page). Content taller than the window gets cut off — render with a generously tall window, then crop to the exact height by "the last non-background pixel row." Every number comes from P3 real acceptance.

## 4. Per-platform fit: wrong ratio = not posted

Same content, re-cut per platform — **don't post one image everywhere**:

- **Image-feed platforms (e.g. Xiaohongshu/RED, Instagram)**: vertical **3:4 (1080×1440) carousel cards**, 3–5 of them. A typical sequence: cover (hook title + concept art) → evidence (one real run) → value (concept art) → CTA (three steps + repo + tags). Bake the cover text into the image; a landscape concept image posted as-is letterboxes, so re-lay it as a vertical card. Put the clickable link in the first comment if the body can't carry one.
- **Timeline platforms (e.g. Twitter/X)**: a landscape **16:9 (1600×900) hero** as the first image (the timeline crops preview to 16:9, a tall image becomes a middle strip); the tall evidence image as the second (tap to see all). One native-language post + one English post (for HN / the tech crowd).
- **Article platforms (e.g. a newsletter / WeChat 公众号)**: inline image ratio is free, native ratios are fine; use the pain-contrast image or the banner as the header; the tall evidence image fits well next to the "it pulled up a dozen" paragraph.

## 5. The publishing manifest: write down "which image goes where"

Produce a `promo/PUBLISH-IMAGES.md` (not posted with the copy) so publishing isn't guesswork:

1. **Asset table**: each image's filename / size·ratio / role / platforms it fits.
2. **Per-platform sequence**: which images, in what order, which is the cover, which copy slot each sits in, and the platform gotchas (link in comments, no tall image as the timeline hero, etc.).
3. **To-do (optional)**: optional-but-skipped items (an English hero, a tighter share-card), with the HTML source location noted for re-rendering after a copy change.

Keep every card's HTML source and copy md in `promo/`; re-render after a copy change, no redesign.

## 6. README first screen & release (where promotion lands people)

Promotion drives people to the repo; if the first screen doesn't hold them in 3 seconds you wasted the click. While publishing/polishing, do these:

- **A one-line English positioning at the top** (for international/HN traffic): one line stating the tool's boundary.
- **One "input → output" screenshot**: left input, right output, faster than any prose. This is the P6 evidence shot — used twice.
- **Cut a release** (`v0.1.0`): a repo with no release looks "not done"; tag it, write two changelog lines, credibility jumps.

## 7. The promotion gate

- Present copy and images as a set; **only post per-platform after the user confirms** — same level as the publish gate.
- The user decides accounts, whether a link is carried, and timing.
- After posting, loop back: add the best-performing channel links to the README/About (closing the "seen → click in → re-distributed" loop).
