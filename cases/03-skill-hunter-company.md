# Case 03 · skill-hunter-company — the whole lifecycle as a "headhunting firm"

> One of several real launches run through this pipeline. Live repo: https://github.com/a28939876-max/skill-hunter-company

**The tool**: a headhunting firm for the skills your agent depends on. Instead of one
more search box, it runs the full executive-search lifecycle — **source → vet → bespoke
→ place → manage** (找/验/融/装/治) — orchestrating the two repos from Cases 01 and 02
plus a fusion engine as one constellation.

## What each phase produced

**P0 — worth-it search (where the pipeline argued with its own owner).** An earlier P0
had ruled "don't open-source the hunter orchestration — orchestration is a private habit,"
on the strength of a *single* dead competitor (a 0★ repo that has since vanished from
GitHub). The owner pushed back and asked for a broader search. Four parallel scans
across categories overturned the universal claim: process/methodology repos top the
charts (build-your-own-x **485k**, 12-factor-agents **23k in a year**), convention-as-code
is a crowded healthy lane (husky 35k, semantic-release 24k), spec-kit hit **112k in six
months**. The grain of truth survived too: pure *discovery-only* tools are cold
(MCPfinder 10★, one find-skill 3★). Verdict: ship — but not as a search box.

**P2 — generalize (the reframe was the work).** Across four model-vs-model debate rounds,
the positioning converged: not "another skill finder" but a **lifecycle firm** where
search is the front door and lineage + governance are the moat. The owner named it after
the original brand — `skill-hunter-company`, "skill 猎头公司" — and chose an executive-search
narrative. The headhunting metaphor dissolved an earlier stalemate: in a real firm,
*ongoing talent management is a core service, not a footnote*, so governance stopped
fighting search for the headline.

**P3 — real acceptance (run on the author's own machine).**
- `source "pptx powerpoint slides"` → a clean shortlist of **6 real candidates with real
  stars**, copies folded into one (aggregator down with HTTP 500, the GitHub desk carried it).
- `roster --days 45` → audited a real install of **34 skills**: **16 idle on the bench**, a
  ranked performer list, 0 false-positive duplicate groups — fully offline.
- `vet` orchestrated the Case-01 lineage desk end to end; `ensure_firm.py` fetched the
  sibling repos from GitHub, proving the fresh-clone path works.

**P4–P6 — polish & promote.** The "why a firm, not a search box" section was rewritten from
a feature table into five short company vignettes, then run through a de-AI-slop editor and
a code-model anti-slop review (verdict: shippable). Promotion follows the playbook —
value narrowed to one line, copy through both gates, three image classes, per-platform
manifest — all behind gate ③.

## The lesson this case taught the pipeline

P0's verdict is only as strong as its sample. A "don't ship" call built on one dead
competitor is not a finding — it's an anecdote. When the owner says "search wider," widen
*across categories*, not just within the niche; the niche being cold can hide a category
that's on fire. That, plus "run the worth-it search as a real debate, not a rubber stamp,"
is now baked into P0.
