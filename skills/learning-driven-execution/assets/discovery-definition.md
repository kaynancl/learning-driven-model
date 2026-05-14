# Discovery Definition — [Initiative name]

> A short, structured framing for a learning cycle. Should fit on one screen.

## Goal & metric
**Strategic objective:** [One sentence — the org/product outcome this serves]
**Primary metric:** [The number that should move]
**Baseline:** [Current value, measured how, on what data] — or `[FILL: baseline]` if not yet measured
**Guardrails:** [Things that must not get worse]

## Hypothesis
> If we [action], then [outcome metric] will [direction] by [magnitude] for [scope] within [timeframe].

[Optional: 1–2 sentences explaining why we believe this]

## Learning goal
What kind of uncertainty are we testing?
- [ ] Problem-validation (is the problem real / sized as we think?)
- [ ] Solution-feasibility (does the approach actually work under realistic constraints?)
- [ ] Adoption / usability (will the intended users actually use it?)
- [ ] Cost / sizing (is the upside worth the build?)

## Experiment
**What we'll run:** [Concrete description — prototype, replay, simulation, interviews, etc.]
**Data source:** [Where the signal comes from — production logs, labeled set, user sessions, etc.]
**Sample size / scope:** [N traces, M users, etc.]
**What "good" looks like:** [Specific threshold — "≥X%", "<Y ms", "≥3 of 5 engineers said…"]
**What "no" looks like:** [The disconfirming case — what would make us Stop]

## Timebox
**Length:** [1–3 weeks]
**Start date:** [date]
**Mid-cycle checkpoint:** [date — usually end of week 1]
**Decision date:** [date]

## Team
**Engineers:** [names]
**PM:** [name]
**EM:** [name]

## Transition criteria
We will Graduate to Delivery only when **all four** are true:
1. Hypothesis validated, with documented limits — [filled at end]
2. Technical feasibility demonstrated under realistic constraints — [filled at end]
3. Impact is measurable, baseline known, instrumentation possible — [filled at end]
4. Cost is justified vs. alternatives — [filled at end]

If not all four within the timebox: Pivot or Stop.

## Out of scope
[What we are explicitly *not* exploring in this cycle, even if relevant]

## Open questions
[Things we're still unsure about as we kick off]

## Links
- RFC / design doc: [link]
- Related Jira / epics: [link]
- Discussion thread: [link]
