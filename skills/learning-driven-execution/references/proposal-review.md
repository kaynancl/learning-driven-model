# Reviewing an existing proposal against LDEM

When an engineer pastes a doc, RFC, design proposal, or Jira epic and asks "does this fit the model" / "is this ready to start" / "what's missing" — run a structured review.

## Read the proposal end-to-end first

Don't start nitpicking before you've understood what the engineer is trying to do. Read the whole thing. Then form a one-line summary of what it's proposing — if you can't, that's already a finding (the proposal is unclear about its own intent).

## Run the eight-question lens

Walk through these in order. For each, note: **Present**, **Implicit/weak**, or **Missing**.

1. **Goal & metric.** Is there a clear strategic outcome and a numerical metric the work will move?
2. **Baseline.** Is the current state measured, or just asserted?
3. **Hypothesis.** Is the bet stated as a falsifiable "if X then Y by Z"?
4. **Uncertainty diagnosis.** Has the proposal correctly diagnosed whether the uncertainty is in problem / solution / feasibility / impact?
5. **Cycle declaration.** Does the proposal identify itself as a Learning Cycle or Delivery Cycle? Or does it conflate the two (the most common gap)?
6. **Experiment design** (if Learning) or **delivery scope** (if Delivery). Concrete and time-boxed?
7. **Success criteria.** Specific, measurable thresholds — not "users will be happy"?
8. **Transition criteria** (if Learning). Has the team thought about what triggers Graduate / Pivot / Stop?

## Common findings (and how to surface them)

Frame findings as observations + suggested moves, not as a grading rubric.

**Solution-anchored framing.** The proposal jumps straight to a technical solution without surfacing the underlying problem. → Suggest stepping back: "What's the user-visible problem this solves? Is the technical solution the only path?"

**Hypothesis is just a description.** "We will add X feature" is not a hypothesis. → Push for the *bet*: what does the team believe will be true if it works, that they're currently uncertain about?

**No baseline.** The proposal claims "currently slow / painful / inefficient" without numbers. → The first move is measuring. That can itself be a 3-day spike.

**Discovery in disguise.** A 6-week "delivery" plan that has substantial open questions in week 1. → Recommend extracting the open questions into a focused learning cycle first.

**Delivery in discovery clothing.** A "spike" that's actually building production code the team plans to keep. → Name the contradiction. Either commit to discarding the spike code, or scope it as Delivery.

**Multiple hypotheses bundled.** Proposal tests three things at once. → Suggest splitting — one bet per cycle.

**Transition criteria absent.** The proposal describes what to build but not what would make the team Stop. → Add a section: under what evidence would we abandon this?

**Scope too big for one cycle.** A 12-week monolith. → Slice into outcome-bearing increments, each with its own success criteria.

**Operational work mislabeled as discovery.** Library upgrade, refactor, well-known pattern. → Just deliver it; no learning cycle needed.

## How to deliver the review

In chat, by default. Structure:

```
**Summary in one line:** [the proposal's intent]

**LDEM lens:** [Learning / Delivery / Mixed — and which it should be]

**Strengths:**
- [2–4 bullets — what's already sharp]

**Gaps to close before starting:**
- [3–6 bullets, each with a concrete suggested move]

**Optional: a sharper framing**
- [1 paragraph re-framing the hypothesis or scope, if helpful]
```

Keep it under one screen. Engineers will not read a long structured review.

## When the proposal is fine as is

Say so. Don't manufacture findings. If the team has a sharp hypothesis, a baseline, and a time-boxed experiment with success criteria — give them a green light and a single sentence on what would make it even better.

## When asked to rewrite the proposal

Offer to. But check first: do they want a Discovery Definition (LDEM-shaped artifact, see `assets/discovery-definition.md`), or a revision of their existing doc? They are different requests. The Discovery Definition is short and structured. A revised RFC may be longer and follow their team's template.
