# When does an initiative belong in Learning Cycle?

Not everything goes through discovery. Forcing well-understood work through a learning cycle is process for its own sake — exactly what the model is trying to avoid.

## Discovery (Learning Cycle) fits when…

- The **problem is poorly understood** — we're not sure what's actually broken or for whom.
- The **solution space is uncertain** — multiple plausible approaches exist and we can't pick one with confidence.
- **Technical feasibility is unclear** — will this approach work at production scale, with real data, under real constraints?
- **Impact size is unknown** — even if we shipped it, we don't know how much it would move the needle.
- The work introduces **new technology** (new tools, frameworks, languages) or significantly changes a critical path — we need to learn the failure modes before betting on it.
- A **prototype could meaningfully de-risk a much larger build** — a 2-week spike protects a 12-week delivery.

## Discovery does NOT fit when…

- The solution is **well-understood** — clear pattern, low uncertainty, the team has done this before.
- The work is **operational / maintenance** — small refactors, playbook automation, library upgrades.
- The change is **incremental and low-risk** — the metric and the approach are already understood.
- The team is using "discovery" as cover for **building something they already decided to build**.

## Coaching prompts

When an engineer wants to do "discovery" on something low-uncertainty, ask:

- "What would you actually learn from a 2-week spike here?"
- "If we skipped discovery and went straight to delivery, what would go wrong?"
- "Which of the four uncertainty buckets does this hit — problem, solution, feasibility, impact?"

If none of those answers land, it's delivery — frame it as such.

When an engineer wants to skip discovery on something high-uncertainty, ask:

- "How are we going to know if this is the right thing before we've built 6 weeks of it?"
- "What's the hypothesis we're betting on? If we're wrong, when do we find out?"
- "What does failure look like? Will we even notice?"

If those answers are weak, push for at least a 1-week scoped learning cycle — even just to set baseline and validate one assumption.

## Edge cases

**"It's a small change but I'm not sure how the existing system will react."**
Often a 1–3 day spike (instrument, simulate, dry-run) is enough. Doesn't need a full cycle. Frame it as a focused feasibility question, not full discovery.

**"It's an obvious problem but nobody has tried it."**
"Obvious" is doing a lot of work here. Why has nobody tried it? Is there a hidden constraint? A 1-week spike to surface the constraints often saves a quarter of wasted delivery.

**"Leadership has already decided we're doing this."**
A learning cycle in this context can still be valuable — but reframe it. The hypothesis isn't "should we do this" (already decided), it's "*how* do we do this most effectively" or "what's the riskiest unknown we should de-risk first". Don't pretend to validate the decision if the decision is locked.

**"We're adopting a new tool / framework."**
Almost always benefits from a focused learning cycle even if the tool is well-known industry-wide. The question isn't "is the tool good", it's "does it fit *our* constraints and integrate with *our* systems".
