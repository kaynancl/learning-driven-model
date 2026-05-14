# Stage 2 — Problem Framing

Once the goal is clear, the team frames a concrete problem in service of that goal — and turns it into a testable hypothesis. This is the most important stage to do well, because everything downstream (experiments, success criteria, transition decisions) hangs on the hypothesis.

## What to produce

Three short artifacts (a few sentences each):

1. **Problem statement** — what's wrong today, and for whom. Backed by *something* concrete: a metric, an interview quote, a benchmark, an observed behavior. If the only evidence is "I think this is broken", that's the first thing to check.

2. **Hypothesis** — the canonical form is *"If we do X, outcome Y will change by Z."* It is testable, has a direction, and names the metric.

3. **Expected impact and risk level** — rough sizing. Not a precise forecast; a sense of whether this is a 5% improvement or a 50% one, and whether being wrong is a small or large hit.

## Anatomy of a strong hypothesis

| Weak | Stronger | Why |
| --- | --- | --- |
| "Self-service tokens will reduce support load" | "If we add self-service token rotation for the top-10 token-using services, weekly token-related SD tickets drop by ≥50% within 30 days of rollout" | Names *who*, *what*, *how much*, *by when* |
| "Caching will improve latency" | "If we cache resolver responses for 60s, p95 lookup latency drops below 200ms with no staleness regressions reported in error budget" | Quantitative target + guardrail |
| "Engineers will use the new dashboard" | "If we ship the dashboard with the three flows engineers asked for, ≥40% of platform team members open it at least 1×/week within 4 weeks" | Falsifiable adoption target |
| "AI agent will help with code review" | "If we run an AutoReview agent on all repo PRs, agreement rate with human reviewers reaches ≥70% on a labeled sample of 100 PRs, *and* ≥30% of reviewers report it caught something they would have missed" | Has both an objective and a subjective check |

The pattern: **action + measurable outcome + magnitude + scope/timeframe**.

## Coaching prompts

When the hypothesis is fuzzy, push with one of these:

- "What would change in production if this works? How would you see it?"
- "What number is supposed to move, and from what to what?"
- "What evidence would make you stop?"
- "Who is the user? Are they a person, a system, or a team?"

If the hypothesis spans multiple things ("if we do A, B, and C, then X, Y, and Z will improve") — split it. One bet per learning cycle is plenty.

## Red flags

- **No baseline.** "It's slow today" — measured how? If they don't know, the first move of the learning cycle is to find out. That's a legitimate (and small) spike.
- **No falsification.** If no possible result would change their mind, they're not running an experiment — they're rationalizing a decision already made. Surface this.
- **Hypothesis = solution.** "If we use Kafka, things will be better" is solution-anchored. Reframe to the *problem* it's meant to solve, then ask whether Kafka is the only path.
- **Outcome metric is a vanity metric.** Page views, logins, dashboard opens — only count if they connect to a real outcome. Push for the second-order metric.
- **Scope is "the whole platform".** Cut down to the smallest scope that would still produce a meaningful learning signal.

## When framing is "good enough" to start a learning cycle

You don't need a perfect hypothesis. You need one sharp enough that a 2–3 week experiment can produce evidence for or against it. If the team can answer:

- What experiment will we run?
- What result counts as "yes"?
- What result counts as "no"?
- How long will we give it?

…then it's good enough. Move to `references/stage-3-learn.md`.
