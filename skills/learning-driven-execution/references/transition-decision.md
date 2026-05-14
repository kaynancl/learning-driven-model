# Transition decisions: Graduate / Pivot / Stop

End of every learning cycle, the team makes a written decision. There is no "maybe" — momentum is the failure mode this is meant to prevent.

The team (engineers + PM + EM) makes the call jointly. Capture the decision as a lightweight artifact — see `assets/transition-record.md`.

## Walk the four criteria

Graduate **only** when the team can answer **yes** to all four. This is the heart of the model.

### 1. Hypothesis validated

Did at least one experiment run, and does the evidence — quantitative or qualitative — actually support the hypothesis? Are the limits of that evidence documented (sample size, conditions, scope)?

**Yes looks like:** "On 100 historical traces, the new resolver returned the correct answer in 87 cases (87%, target was ≥70%). The 13 failures cluster around case Y, which we did not test for."

**No looks like:** "The prototype works on the happy path. We didn't run it on edge cases yet."

### 2. Technical feasibility demonstrated

Did the prototype run under realistic constraints — real data volume, real latency, real integration points? Or did it only work in demo conditions?

**Yes looks like:** "We replayed three days of production traffic at 1.5× volume. p95 latency stayed under 180ms vs. the 200ms target. Memory footprint was 1.4GB on the production instance type."

**No looks like:** "It worked on the example dataset (100 rows). We haven't tried at scale yet."

### 3. Impact is measurable

Is the target metric defined? Is the baseline known? Can the team instrument production to track the change?

**Yes looks like:** "Target: median onboarding time. Current baseline: 6.5 days (90 onboarded accounts, last 60 days). Instrumentation already exists in the provisioning pipeline."

**No looks like:** "We're sure it'll be faster, but we don't have a current measurement."

### 4. Cost is justified

Is the estimated delivery effort proportional to the expected impact? Does it compare favorably to other things in the team's backlog?

**Yes looks like:** "Estimated ~5 weeks delivery. Expected impact: 40% faster onboarding for ~12 new accounts/month. Compares favorably to the alerting-templates initiative we'd otherwise pick up."

**No looks like:** "We think this is a 2–3 quarter build. The expected impact is hard to size. We haven't compared it to other priorities."

## The three outcomes

### Graduate

All four criteria are yes. Move to Delivery Mode. Document the rationale and link to the evidence. See `references/stage-4-deliver.md` for what comes next.

### Pivot

The hypothesis was wrong but the experiment surfaced a different, more promising one. Re-frame: write a new hypothesis (back through Stage 2), run another time-boxed cycle. Capture what didn't work and why — so the team or future teams don't re-run the same path.

A common pivot pattern: feasibility was fine, but the *problem* turns out to be different than assumed. The fix is in framing, not in the prototype.

### Stop

The hypothesis was wrong, or the cost is not justified, or the problem turned out to be smaller than assumed. **This is a successful outcome.** A team that stops three weak ideas early has freed capacity for higher-impact work.

Document:
- What the hypothesis was
- What evidence led to Stop (not just "didn't work" — the specific signal)
- What the team learned (so future teams don't re-explore the same ground)
- What's freed up (capacity, problem space, related ideas)

Push back if the team treats Stop as a failure. The model is broken if Stop is culturally penalized.

## When the decision is genuinely close

Sometimes the four criteria don't cleanly say yes or no. Common patterns:

- **Three yeses, one weak.** Usually means *one more focused mini-spike* — not a full Pivot. Time-box it tight (1 week max) to close the specific gap.
- **Yes on the prototype, no on the cost.** This is a real Stop. The technology works but doesn't earn its keep. Capture the conditions under which it would become worth doing later.
- **Yes on everything except impact measurability.** Don't graduate yet. Build instrumentation first, then re-measure baseline, then re-decide.

## Coaching during the decision

- Ask each question explicitly. Don't let the team gloss "yeah I think we're good".
- For each "yes", ask for the specific evidence sentence. If they can't produce one, the answer is probably no.
- Surface Stop early in the conversation. If you only present Graduate vs. Pivot, the team will pick one.
- If everyone in the room is invested in the idea, name that. Sunk cost is the most common reason teams graduate things they shouldn't.
