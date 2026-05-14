# Jira epic structure for an LDEM initiative

> Use this as the epic description content. Adapt to the team's project conventions.

---

**Cycle scope:** Learning only | Delivery only | Learning → Delivery
**Stage:** Goal Definition | Problem Framing | Learning Cycle | Delivery Cycle
**Status:** Not started | Active | Decided | Delivered | Stopped

## Goal & metric

**Strategic objective:** [one sentence]
**Primary metric:** [the number that should move]
**Baseline:** [current value or `[FILL: baseline]`]
**Guardrails:** [must-not-degrade list]

## Hypothesis

> If [action], then [outcome] will [direction] by [magnitude] for [scope] within [timeframe].

## Learning goal *(Learning Cycle only)*

[Problem-validation / Solution-feasibility / Adoption-usability / Cost-sizing]

## Experiment *(Learning Cycle only)*

- **What we'll run:** [...]
- **Data source:** [...]
- **Scope:** [...]
- **Yes threshold:** [...]
- **No threshold:** [...]

## Delivery scope *(Delivery Cycle only)*

- **In scope:** [...]
- **Out of scope:** [...]
- **Operational readiness:** [SLOs, observability, on-call story]
- **Rollout plan:** [canary, % rollout, feature flags]

## Success criteria

[Specific thresholds]

## Timebox

- **Length:** [1–3 wk Learning / 4–6 wk Delivery]
- **Start:** [date]
- **End:** [date]

## Transition criteria *(Learning Cycle only)*

1. Hypothesis validated — [pending / yes + evidence / no]
2. Technical feasibility demonstrated — [pending / yes + evidence / no]
3. Impact is measurable — [pending / yes + evidence / no]
4. Cost is justified — [pending / yes + evidence / no]

## Decision *(filled at end of Learning cycle)*

- **Outcome:** [Graduate / Pivot / Stop]
- **Date:** [...]
- **Rationale:** [...]
- **Link to transition record:** [...]

## Outcome verification *(filled at end of Delivery cycle)*

- **Metric movement:** baseline [...] → current [...]
- **Did the hypothesis hold?** [Yes / Partially / No]
- **What surprised us:** [...]

## Links

- RFC / design doc: [link]
- Discovery Definition / Transition Record: [link]
- Discussion thread: [link]
- Related epics: [keys]

---

## Suggested sub-issue structure

**Shape A (Learning only):**
- Spike: "Learning cycle: [hypothesis summary]" — assignee, due date

**Shape B (Learning → Delivery):**
- Spike (Learning Cycle) — closes when transition decided
- Story: Production implementation
- Story: Observability + on-call
- Story: Outcome verification — does the metric move?

Add more stories for Delivery Cycle as needed; one per outcome-bearing increment.
