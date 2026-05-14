# Stage 1 — Goal Definition

This stage usually happens quickly — sometimes already done by leadership before the engineer arrives. Don't drag it out. Your job is to make sure the team has clarity on three things before any framing starts.

## What needs to be answered

**Strategic objective** — What outcome at the org / product / platform level is this in service of? One sentence. If the engineer can't name one, that's a flag — they may be solving a problem nobody asked for.

**Primary outcome metric** — The numerical thing that should move. Examples:
- "Median time from cloud account creation to logs being ingested and queryable"
- "Volume of API token-related service desk tickets"
- "Median PR review latency"

The metric should be one the team can actually instrument or already has visibility into. "Engineer happiness" is not an outcome metric unless they have a survey baseline.

**Guardrails** — Things that must *not* get worse. Common ones in platform work:
- Coverage / completeness (no data lost)
- Security / compliance posture
- Latency or availability of the existing system
- Cost (no 3× spend to save 10% latency)

## Coaching prompts

If the engineer is unclear on the goal, ask:

- "What does success look like a quarter from now if this works?"
- "If your VP / staff peer asked why this matters, what would you say in one sentence?"
- "What would you measure to know it's working?"
- "What can't get worse as a side effect?"

## What good looks like

> **Goal:** Reduce the setup time of the logging platform to manage logs for new cloud accounts.
> **Metric:** Reduce median time from cloud account creation to logs being ingested and queryable by 40%.
> **Guardrails:** No degradation in log coverage, data quality, or security/compliance posture for newly onboarded accounts.

## When to push back

- "Make engineers happier" → ask for the operational definition (NPS survey? cycle time? on-call pages?).
- "Improve the platform" → too vague. What aspect? For whom?
- The "metric" is an activity ("write more tests") rather than an outcome → reframe to the outcome the activity is supposed to drive.

Once goal is clear, move to Stage 2 — Problem Framing.
