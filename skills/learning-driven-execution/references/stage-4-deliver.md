# Stage 4 — Delivery Cycle

The hypothesis was validated, the team chose Graduate. Delivery Cycle now turns the validated bet into a production-grade system.

## Time-box

**4–6 weeks** for a meaningful end-to-end increment. If the work is genuinely larger, slice into multiple delivery cycles, each with its own outcome. A 12-week monolith with no internal milestones is a smell.

## What's different from Learning Cycle

| Learning Cycle | Delivery Cycle |
| --- | --- |
| Output is a *decision* | Output is a *deployed system + measurable outcome* |
| Code is disposable | Code is owned, observable, on-call |
| Speed of insight wins | Operational quality wins |
| Prototypes, mocks, scripts | Production architecture, integrations, runbooks |
| Internal users only | Real users / production traffic |

The transition from Learning to Delivery is when the team stops asking "does this work?" and starts asking "how do we run this in production?"

## What Delivery Cycle includes

- **Robust implementation.** Refactoring the prototype is normal — usually nothing of the prototype survives intact, and that's healthy. The prototype's job was to teach; the production code's job is to run.
- **Reliability and observability.** SLOs, dashboards, alerting, error budgets. If something breaks at 3 AM, who pages, on what, and what do they do?
- **Security & compliance.** Where applicable: threat model, access controls, data classification, audit trail.
- **Integrations and operational readiness.** Wiring into existing systems, playbooks, incident response.
- **Documentation for the next person** — not just the team. ADRs, runbooks, onboarding doc updates.
- **Progressive rollout.** Canary, percentage rollouts, feature flags. Don't ship to 100% on day one if you can avoid it.

## Outcome verification

Delivery is not done at "deployed". It's done at "we can confirm the hypothesis held in production". Two parts:

1. **The thing you built is running.** Health metrics green, no SEV-1s linked to the change, ownership clear.
2. **The outcome the hypothesis predicted has moved.** Compare against the baseline that was set during framing. If the metric did *not* move as predicted, that is critical learning — capture it. The hypothesis was only partially right, and the next cycle should reflect that.

## What to watch for during delivery

- **Scope creep into "while we're in here".** Adjacent improvements feel cheap during delivery but compound. Add them to a follow-up backlog instead, unless they directly affect the success metric.
- **Reverting to discovery mid-cycle.** If a Delivery Cycle initiative starts uncovering big new unknowns, that's a sign the learning cycle ended too early. It's OK to pause delivery and run a focused mini-spike, but name it.
- **Operational debt deferred to "later".** If the on-call story isn't part of the delivery scope, it usually doesn't get built. Bake it in.

## Closing out a delivery cycle

The team should produce — even briefly — a closing note that captures:

- What shipped (link to deploy / PRs / docs)
- The outcome metric: baseline → current value
- Whether the hypothesis held, partially held, or didn't
- What surprised the team (good or bad)
- Follow-ups (operational, scope, observed bugs)

This is the input to the team's retro and to the next round of goal/framing — and it's what feeds the team's accumulating "learning corpus" across initiatives.
