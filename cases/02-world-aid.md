# Case 02 · world-aid — "you say what you want; it rounds up the tools"

> One of several real launches run through this pipeline. Live repo: https://github.com/a28939876-max/world-aid

**The tool**: you describe a need in plain words, and `world-aid` searches the whole field of existing skills, groups the duplicates, flags the origin, runs a pre-install safety check, and lays the options out for you to pick.

## What each phase produced

**P0 — worth-it search (the pipeline-object case).** Search tools exist; lineage tools exist (see Case 01). But the **chain** "search → group dupes → check before install → install" — nobody had wired that end to end. The independent value anchor is the pre-install safety step, so it wasn't pure orchestration. Verdict: ship.

**P2 — generalize.** The value prop was narrowed, over several rounds with the user, to one consumer-grade sentence: *"you say what you want to do, and it rounds up the existing tools for you, so you don't go hunting."*

**P3 — real acceptance (the case that sells it).** Need, verbatim: **"turn a YouTube video into text."**

- Two keyword passes returned **13 candidates**.
- Grouping merged the duplicates down to **9 genuinely different implementations** (4 of the 13 were reposts of one head).
- The flashiest one — a **7★** "youtube-transcript-tor" promising to "bypass IP blocks via Tor" — looked the most capable. The pipeline's on-machine code review (codex) read it and flagged: it quietly takes admin rights to `sudo systemctl start tor` and writes to a cloud-bot directory that doesn't exist on your machine. It solves *someone else's* problem.

Lesson surfaced by the run, straight into the README: **finding the whole field is what lets you see that "the most impressive" ≠ "the most fitting"** — and stars don't track fit (the 430★ head was for a whole knowledge-base flow; a low-star one was the right plain-transcript pick).

**P4–P6 — polish & promote.** README led with the felt pain (the first result isn't the best fit); copy ran through a de-AI-slop editor and a code-model review against hard anti-slop rules, across rounds. For promotion the pipeline produced: concept art (before/after, tool round-up), an **HTML-rendered evidence shot** (the 13→9→1 find with real repo names/stars — rendered, not text-to-image, so the names don't garble), platform-fit cards (3:4 vertical carousel for the image feed, a 16:9 hero for the timeline), and a `promo/PUBLISH-IMAGES.md` manifest.

## The lesson this case taught the pipeline

The evidence shot must be **HTML-rendered and screenshot via `file://`** — a text-to-image model garbles repo names and numbers, and starting a local `http.server` to screenshot once cost a published image that turned out to be a 404 error page. That hard rule now lives in the promotion playbook.
