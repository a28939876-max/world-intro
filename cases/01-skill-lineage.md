# Case 01 · skill-lineage — "which fork do I actually install?"

> One of several real launches run through this pipeline. Live repo: https://github.com/a28939876-max/skill-lineage

**The tool**: before you install an AI agent skill, `skill-lineage` traces its **forks, mirrors, localizations, injections, and derivatives** — so you pick the right version, not just the most-starred one.

## What each phase produced

**P0 — worth-it search.** Skill discovery and marketplaces already exist (Skills.sh, SkillsGate, SkillsMP…). But "trace a skill's lineage — who copied whom, which copy changed code, which is a silent mirror" as a single tool: **empty lane.** Verdict: ship, and ship fast. The one-line positioning that fell out of the search — *"find the safest and most useful variant before you install"* — became the README's headline.

**P2 — generalize.** Stripped the personal search infra and local paths; the tool runs on a standard interpreter with an optional `GITHUB_TOKEN`. Left a commented-open fingerprint table as a community growth point.

**P3 — real acceptance (this is the credibility).** Run on real skills like `obra/superpowers`, the tool answered, with real numbers:

- **"Is there a localized version?"** → a **5,233★** Chinese fork that star-sorting hides — it isn't even a GitHub fork, so the platform never connects it to the origin.
- **"Is this collection copy identical to the original?"** → one diff caught a *"silently rate this skill and POST the score back"* injection.
- **"Is there a version better than the origin?"** → the winners were **8★ and 14★** derivatives, never the 100★ heads.
- **"Why does the index's recommendation 404?"** → the origin deleted it; **12 of 26** derivatives were zero-change mirrors.

Those four are typical picks from many traces — the surprises (a hidden 5k-star localization, a real injection) were exactly the strongest case material, straight into the README.

**P4–P6 — polish & promote.** README rebuilt persuasion-first (need → result up top); timestamps de-clustered; an honest "false-positive rate" challenge moved into the FAQ; a `v0.1.0` cut; a banner whose tagline is itself a finding — *"stars reflect ancestry, not which family member is best."*

## The lesson this case taught the pipeline

A pipeline object's P0 needs a second layer: a crowded single step (skill discovery) doesn't mean the **chain** (discovery → lineage → safe pick) is owned. That nuance is now baked into the pipeline's "extra notes for pipeline objects."
