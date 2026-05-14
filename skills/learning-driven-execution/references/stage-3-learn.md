# Stage 3 — Learning Cycle

The team has a hypothesis. Now they design and run a time-boxed experiment to validate, refute, or refine it. The output of this stage is a **decision**, not code.

## Time-box

**1–3 weeks per hypothesis** is the working range. Default to 2 weeks. If the team thinks they need 4+ weeks of "discovery", probe — usually they're either (a) doing delivery in disguise, or (b) trying to cover too many hypotheses in one cycle.

## What's appropriate to build

Discovery code is **disposable by default**. Speed of insight beats production hygiene. Examples that fit:

- A throwaway prototype or mock service to validate technical feasibility
- An offline evaluation script over historical data
- A script that replays production traces against a candidate algorithm
- A simulated or stubbed integration to exercise the unknown part
- A small internal-only UI or CLI for usability tests
- A design exercise (whiteboard, RFC, ADR) where the unknown is conceptual, not technical
- A spike to *measure the baseline* when nobody knows what it is today

## What does NOT fit Learning Cycle

- Refactoring existing code that already works in production
- Hardening an already-validated prototype (that's Delivery Cycle)
- Building "MVP" code the team plans to keep — that's prototype-becoming-production, the failure mode LDEM is designed to prevent. Either commit to discarding it or treat it as Delivery.
- Open-ended research with no hypothesis attached
- Anything where you already know the answer

## Designing the experiment

Three questions to answer before starting:

1. **What's the smallest test that produces a real signal?** Resist scope creep. If a three-day spike on 100 historical traces would tell you whether the approach is viable, do that — don't build a full pipeline.

2. **What does the data look like?** Where will the signal come from? Logs, metrics, a labeled dataset, user feedback, a simulated load, a manual review of N samples? The data source determines the timebox.

3. **What's the success threshold?** Not "we'll see how it goes" — pick a number or a binary outcome. Examples:
   - "≥70% agreement on a labeled set of 100 cases"
   - "Median latency below 200ms across the test corpus"
   - "≥3 of 5 engineers say they'd adopt this in a usability session"
   - "Throughput stays within 10% of current under 2× load"

## Two flavors of uncertainty

Different hypotheses call for different experiments. Diagnose which kind first:

| Kind | Question | Example experiment |
| --- | --- | --- |
| **Problem-validation** | "Is this problem real / big enough?" | User interviews, log analysis of how often the issue occurs, comparing observed behavior vs. assumed behavior |
| **Solution-feasibility** | "Will this approach actually work?" | Prototype against realistic data, replay production traces, evaluate against a labeled sample, run under simulated load |
| **Adoption / usability** | "Will the intended users actually use this?" | Internal pilot, usability sessions with 3–5 engineers, week-long shadow run |
| **Cost / sizing** | "Is the upside worth the build?" | Back-of-envelope math, pricing the change, comparing to alternative bets |

A single learning cycle can mix two of these (e.g., feasibility + cost), but trying to do all four in two weeks usually fails.

## Instrumentation is part of the experiment

The model warns against Learning Cycle degenerating into "unstructured exploration." The fix is **define your evaluation metrics before you start building**, not after. Specifically:

- The outcome metric (the thing the hypothesis claims will change)
- A behavioral metric where relevant (do users act on it?)
- A feasibility metric (error rate, coverage, latency, etc.)

If the engineer can't say how they'll measure success before they write code, that conversation is the next 30 minutes — not the build.

## Mid-cycle checkpoint

For a 2-week cycle, do a quick checkpoint at end of week 1: is the experiment producing the kind of signal we expected? If not, kill or pivot now — don't burn the second week hoping.

## End of cycle: the decision

Bring the team to the four transition criteria (see `references/transition-decision.md`). Output is one of:

- **Graduate** → Stage 4, Delivery Cycle
- **Pivot** → re-frame the hypothesis, run another short cycle
- **Stop** → document what was learned, free the capacity

Document the decision and the evidence in a transition record — the artifact for that is in `assets/transition-record.md`.
