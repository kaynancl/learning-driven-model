# LDEM at a glance

The Learning-Driven Execution Model is one answer to the rework / "demo-to-production" gap. It is a **decision model**, not a process layer.

## Core idea

The same team alternates between two operational modes:

| Mode | Goal | Output | Typical length |
| --- | --- | --- | --- |
| **Learning Mode (Build to Learn)** | Reduce uncertainty about a problem or solution | A decision: Graduate, Pivot, or Stop — backed by evidence | 1–3 weeks |
| **Delivery Mode (Build to Earn)** | Deliver production value for a validated bet | Deployed system + measurable outcome shift | 4–6 weeks |

Cycles do not need to run back-to-back on the same initiative. A team can run a learning cycle on initiative A, then deliver on initiative B (already validated), and return to A later.

## Four stages of an initiative

```
Goal Definition  →  Problem Framing  →  Learning Mode  →  Delivery Mode
   (leadership +      (team + PM —          (team —              (team —
    team — strategic    hypothesis,           experiment,           production
    objective, target   expected impact)      decide)               build, measure)
    metric, guardrails)
```

Stages 3 and 4 are the explicit modes. Stages 1 and 2 happen quickly — usually one or two short conversations, not multi-week activities.

## Transition criteria (Learning → Delivery)

Graduate only when **all four** are true:

1. Hypothesis validated — evidence supports it, limits documented.
2. Technical feasibility demonstrated — prototype ran under realistic constraints, not demo conditions.
3. Impact is measurable — target metric defined, baseline set, production instrumentable.
4. Cost is justified — effort is proportional to expected impact vs. alternatives.

If not all four within the timebox: **Pivot** (re-frame, run another short cycle) or **Stop** (kill with evidence; document the learning).

## Capacity (annual guideline, not a rule)

| Category | Range |
| --- | --- |
| Delivery | ~60–70% |
| Discovery | ~20–30% |
| Maintenance / operational | ~10–20% |

Treat these as a starting hypothesis. Refine the split as your team learns what works.

## What does not change

- Teams own their backlog and execution.
- OKRs / planning / retros are not replaced.
- The team's existing system of record (Jira, Linear, etc.) stays the system of record.
- No new approval gates or governance layer.

## What does change

- Before high-uncertainty work: a short Discovery Definition (hypothesis + success criteria + timebox).
- Discovery work runs in its own time-boxed cycle — not blended into delivery.
- Each learning cycle ends with a written Graduate / Pivot / Stop decision.
- Capacity allocation between modes becomes an explicit, tracked choice.

## Cultural rule

**Stopping with evidence is a successful outcome.** A team that kills three weak ideas early has freed capacity for higher-impact work. Track "ideas killed with evidence" as a positive metric. Document what was learned.
