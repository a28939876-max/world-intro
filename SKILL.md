---
name: world-intro
description: Introduce your private skill (or internal tool) to the world — an opinionated, gated, end-to-end pipeline that takes something you use well and makes it something others want. It decides whether it's even worth open-sourcing (real competitor search, not paper analysis), generalizes it out of your personal environment, proves it on real data that becomes the README's case studies, polishes the narrative against anti-AI-slop rules, ships it, and promotes it across platforms so it actually gets seen. Use when someone says "open source this skill/tool", "publish as OSS", "make a public version", "help me launch my open-source project". NOT for routine code pushes (no open-sourcing intent), opening a PR to an existing project, or just writing a README.
---

# world-intro · Introduce your skill to the world

> 行道于天下 — once you have a skill worth sharing, get it **found, understood, verified, used, and improved upon** by others, so it becomes someone else's "stone from another hill that can polish your jade."

Turning "I use it and it's great" into "strangers want it" is its own craft. This is a six-phase pipeline with three human gates; each phase feeds the next. Every rule here was paid for in a real release — see [cases/](cases/).

```
P0 worth-it search → P1 paradigm + gate① → P2 generalize → P3 real acceptance → P4 polish → P5 publish + gate② → P6 promote + gate③
```

The five verbs map onto the phases: **found** = P0 search + P6 promotion · **understood** = P4 narrative · **verified** = P3 acceptance + challenge-FAQ · **used** = P2 generalization + one-line install · **improved upon** = community growth points + author attribution.

## P0 — Is it even worth it? Search first, build second

Paper analysis lies. Before touching anything, **really search for prior art** (GitHub repo search, aggregator indexes, social proof; use whatever search infra you have, otherwise web search). Render a three-way verdict on "should this be open-sourced":

- **Empty lane** → ship it, and ship fast (the window is finite).
- **Crowded but no dominant player** → downgrade the positioning: have the README name the strongest competitor and state the difference plainly (e.g. "the zero-dependency lightweight take"), and accept that the official/leading project may absorb you.
- **Already owned** (a mature, high-star, enterprise-grade solution exists) → **don't open source.** Invert: wire that mature solution into your own pipeline as a backend, and contribute your unique accumulation (fingerprints, data, use cases) upstream as a PR.

Write the evidence (competitor names / stars / the actual difference) into a short research note — it's the input to P1 and your ammunition for the inevitable "how is this different from X?".

## P1 — Paradigm + gate①: borrow structure, not words

1. Pick a **narratively complete** open-source project as your paradigm (it need not be in your domain). Extract its portable mechanisms — the common five: a story-driven hook opening (the first screen tells a story, doesn't list features), a two-layer product (a loadable framework + a ready-to-use case/asset library), real cases as the distribution engine, self-serve templates, one-line install.
2. **"Mechanism vs matrix" discipline**: borrow only structural mechanisms, never copy prose; leave behind anything bound to their environment.
3. Produce a proposal containing: 2–3 name candidates, language strategy, repo structure, case list, the matrix-stripping table, acceptance objects, and **what you will NOT do**.
4. **Gate①**: let the user decide three things — naming / language / acceptance scope — via an explicit question. Everything else is yours to decide.

## P2 — Generalize: strip the matrix, keep the mechanism

Move the tool from "my environment" into "anyone's environment":

- Private shared libraries → **inline** them into a single file: self-contained, zero third-party deps, runs on a standard interpreter.
- Personal auth / paths / conventions → delete, or convert to standard env vars (e.g. optional `GITHUB_TOKEN`).
- Paid/private data sources → make optional; the default path must work with zero config.
- Tooling you name from your own setup (a specific image generator, a publishing tool, a de-slop editor) → generalize to a role ("your image-gen tool", "your platform-publishing tool") and keep the specific name only as an `e.g.` example.
- Bilingual comments and prompts (primary language + English); keep data fields in English.
- **Design community growth points**: leave clearly marked, comment-invited places for PRs (fingerprint lists, rule tables).
- Anything that relies on undocumented host-tool behavior: annotate "tested conclusion + version" and give a fallback path.

## P3 — Real acceptance: only a real run counts; reuse the output twice

- Run the full pipeline end-to-end on the 1–2 **real objects** fixed at gate①. It's only a finished product once it runs.
- The real data the run outputs goes **straight into the README as case studies** — the numbers are real and reproducible, which is the strongest credibility you have.
- The **surprises during acceptance are often the best case material** (the target object exposes an ecosystem problem, etc.) — don't discard them as noise.

## P4 — Polish: iterate by the rules, anticipate the challenges

Nine rules (full operation + the challenge-list taxonomy in [pipeline/polish-rules.md](pipeline/polish-rules.md)):

1. **Relatable case selection**: the lead case uses a need the target audience "has all the time and gets in one sentence" (build an app, make a deck, install a model) — no jargon, no meta-needs; demote developer-facing cases to an "advanced" subsection; keep big-name validation but don't let it steal the stage.
2. **Run it for real, then backfill**: once the case is chosen, actually run the pipeline and backfill the doc with the real result; if it doesn't produce something good, swap the case on the spot — the doc only contains what really ran.
3. **Persuasion up front**: the README's first screen puts a "need → result" block directly; format = the need verbatim + the original-plan gripe (the fun is in the gap) + **the result as its own paragraph**; don't bury the gripe in a case detail page.
4. **The whole page answers "what's it for, how do I use it"**: sample block (what for) → three-step how-to (quick-start hoisted to screen two) → a "without it vs with it" table (translate features into felt gains) → technical detail last.
5. **De-cluster the timestamps**: all cases dated the same day = "obviously just built." Switch to relative phrasing; require timestamps only at the methodology level.
6. **Aphorism voice → plain words; calibrate diction**: rewrite the dressed-up metaphor lines to plain; titles may be literary but must read instantly; for company/org output, don't use person-like words ("author credit") — use "the maintainer / the official source".
7. **Cases aren't only N**: say plainly "these N are typical picks from many", and repeat it in each case's footnote.
8. **Charts render natively on the platform** (GitHub: mermaid), zero image assets, never a dead link; a cover image may be produced separately.
9. **Anticipate challenges**: list "things people will attack" by severity in three tiers (must answer / can harden / bikeshed), present to the user to name — the named ones go into FAQ/body, the un-named are left alone. Showing your weak spots beats being caught with them.

Commit after each polish round; stay traceable.

## P5 — Publish + gate②: nothing goes out without a user nod

Repo-creation paths, author attribution, force-push details in [pipeline/publish-pitfalls.md](pipeline/publish-pitfalls.md). Flow:

1. **Gate②**: show the finished product; **before pushing to remote, the user must confirm the account and repo name.**
2. Create the repo (per local conditions: gh CLI / user creates via web / user-provided PAT). **An SSH key can push, not create.**
3. Replace the README placeholder owner, set the remote, push.
4. Verify live: visibility, README rendering, image/cover resources return 200.
5. Author attribution: ensure the commit author email links to the user's platform account (a noreply email is most reliable); rewriting history follows the safe flow in the reference.
6. **Sibling backlinks**: if you have related already-open repos, add a link back to this project in their README and push (two-way loop, mutual traffic).
7. Remind the user to fill in the About description and topics (give paste-ready copy).

## P6 — Promote: shipping isn't the finish line; being seen is

A repo pushed with star=0 that nobody knows about = not open-sourced. Full playbook (value-prop narrowing, anti-slop copy discipline, three image types, per-platform aspect ratios, the publishing manifest, README first-screen + release, the promotion gate) in [pipeline/promotion-playbook.md](pipeline/promotion-playbook.md). Essentials:

1. **See how the comparables promote first**: reuse the P0 competitors — do they have a Twitter/blog/social presence, what's the tone — to decide which platforms you cover.
2. **Narrow the value prop to one sentence + a hook opening**: "user's situation + the pain you kill" in one line; every platform's copy and image rallies around it; the first line / first image states the biggest selling point — don't let it sink to the middle.
3. **Copy passes two gates**: each platform's body goes through a de-AI-slop editor + a code-model review against the hard anti-slop rules (feed the rules in as ground truth); the opening hook uses a single, specific, interesting real episode — don't lift cases/ verbatim.
4. **Three image types**: concept art (image-gen, for the value/pain) · **evidence shot — must be rendered from HTML then screenshot via `file://`, never from a text-to-image model (it garbles repo names/numbers), and never by starting a local http.server (you'll screenshot a 404 page)** · banner. Every number comes from P3 real acceptance.
5. **Per-platform aspect ratios**: vertical 3:4 carousel cards for image-feed platforms, a 16:9 hero for timeline platforms (a tall image gets cropped), native ratio for article platforms; produce a `promo/PUBLISH-IMAGES.md` manifest (which image goes where, in what copy slot).
6. **README first screen + release**: a one-line English positioning at the top, one "input → output" screenshot (= the evidence shot, used twice), and cut a `v0.1.0` release — a repo with no release looks unfinished.
7. **Gate③**: present copy and images as a set; **only post per-platform after the user confirms** — same level as the publish gate.

> The actual production can hand off to specialized tools: article copy to an article-writer skill, image-feed cards to a card-post skill, multi-platform distribution to a broadcast/publishing skill, covers/banners to a graphic-design skill. This pipeline's job is to **narrow the value prop, hold the tone discipline, classify the images, sequence the platforms, and keep the gates** — leave the rendering to those.

## Extra notes for pipeline objects (when what you're open-sourcing is a composed chain)

- **P0, one more layer**: beyond "has anyone done the same thing", check "has anyone **chained these steps**" — a crowded single step doesn't mean the chain is owned.
- **P2 dependency call**: when an upstream component is itself open source, prefer **fetching it at runtime on demand** (a small `ensure_xxx.py` pulling the script from its repo's raw link into a local cache) to form a sibling link; vendoring + crediting is the fallback; pure orchestration (no hard script) is a weak sell — either fold it into an existing repo as a new mode, or make sure the chain has an independent value anchor (like a pre-install security check).
- **P3 acceptance must pass through side-effect steps**: if there's an "install / write-to-disk / send-out" step, the acceptance has to really run it — into a sandbox dir (e.g. `.acceptance/`, gitignored), kept as evidence or cleaned up after.
- **P3 acceptance picks different terrains**: at least one "copy-cluster" scenario + one "independent-group" scenario, to prove the pipeline branches correctly under both.

## Boundaries

- Three gates are non-negotiable: the plan gate (naming/language/scope), the publish gate (account/repo name), the promotion gate (per-platform confirmation before anything goes out).
- Don't decide for the user whether to open-source: the P0 verdict is advice; the call is theirs.
- Destructive operations (history rewrite, force push): explain first, then let the user choose or run it themselves.
