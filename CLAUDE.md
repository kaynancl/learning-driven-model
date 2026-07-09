# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

A Claude Code **plugin** that ships a single skill: a coaching agent for the Learning-Driven Execution Model (LDEM), an initiative-scoped process where an epic/project moves through a **Learning Cycle** (reduce uncertainty, 1–3 weeks, ends in Graduate/Pivot/Stop) and, if it graduates, a **Delivery Cycle** (ship measurable production impact, 4–6 weeks). Same people run both cycles for a given initiative; a team can have several initiatives in flight, each in its own cycle.

There is no application code, build step, test suite, or CI in this repo — it is entirely Markdown content plus a plugin manifest. There is nothing to build, lint, or test; "development" here means editing prompt/coaching content.

## Repository layout

```
.claude-plugin/plugin.json                # plugin manifest (name, description, keywords)
skills/learning-driven-execution/
  SKILL.md                                 # entry router + coaching stance (loaded on every trigger)
  references/                              # stage-specific guides, pulled in only when needed
    model-overview.md                      # one-page summary of LDEM — SKILL.md tells the model to read this first
    stage-1-goal.md / stage-2-frame.md     # framing a new initiative
    stage-3-learn.md / stage-4-deliver.md  # learning cycle / delivery cycle mechanics
    transition-decision.md                 # Graduate / Pivot / Stop walkthrough
    when-to-discover.md                    # when NOT to run a learning cycle
    proposal-review.md                     # reviewing an RFC/design doc/epic against LDEM
    jira-output.md                         # guidance for producing Jira artifacts
  assets/                                  # fill-in templates, referenced by SKILL.md when producing artifacts
    discovery-definition.md
    transition-record.md
    jira-epic-structure.md
```

`SKILL.md`'s YAML frontmatter (`name`, `description`) is what Claude Code uses to decide when to trigger the skill — the `description` field encodes the trigger phrases and is the most load-bearing text in the repo.

## Editing conventions (from CONTRIBUTING.md)

- **SKILL.md is loaded on every trigger** — keep it router-and-stance content only (entry-point selection, coaching stance, when to push back). Push actual procedural detail into `references/`, which loads on demand.
- Match the existing tone: coach, don't gatekeep; short and direct; concrete examples over abstract explanation.
- No hardcoded names, internal links, or organization-specific references — this is a public, general-purpose plugin.
- Avoid "MUST" / "ALWAYS" / "NEVER" — the skill explicitly avoids sounding like a compliance checklist; explain *why* instead of commanding.
- Before editing a file, read it end-to-end first (per CONTRIBUTING.md).
- When adding new trigger phrases, they belong in the `description` field of `SKILL.md`'s frontmatter, not just the body.

## Content architecture worth understanding before editing

The coaching flow in `SKILL.md` is a **router**: it identifies which of four entry points the engineer is in (frame a new initiative / review an existing proposal / transition decision / reference Q&A), then dispatches to the matching `references/*.md` file rather than inlining the detail. When editing any reference file, check `SKILL.md`'s "Choose the entry point" table and "Producing artifacts" section for cross-references that may need updating too — the router and the reference files are meant to stay in sync (file names, section names, and the conditions under which each is loaded).

Artifacts (`assets/*.md`) are only produced on explicit engineer request, never proactively, and unknown fields are marked `[FILL: …]` rather than fabricated — this constraint is stated in `SKILL.md` and should be preserved if assets are extended.
