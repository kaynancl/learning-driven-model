# Producing Jira artifacts

Jira output is **opt-in**. Default to chat output. Only create Jira issues when the engineer explicitly asks for them, and confirm scope before doing anything that mutates Jira.

## Confirm scope before creating

When the engineer says "put this in Jira" / "create the epic" / etc., ask:

1. **What level of detail?** Just an epic? Epic + a single spike issue for the learning cycle? Epic + multiple stories for the delivery cycle?
2. **Which Jira project?** Don't assume — engineers often work across multiple projects.
3. **Who's the assignee / epic owner?** Often "leave unassigned" is the right answer; check.
4. **Are there parent links** (program epics, OKRs) **to wire up?** If yes, confirm the keys.
5. **Visible to whom?** Some teams use private projects for early-stage discovery; check before creating something that becomes searchable across the org.

Show the engineer the **full proposed content in chat first** — the epic description, any sub-issues, custom fields. Get explicit approval ("yes, create it") before calling the Jira tools.

## Recommended Jira shapes

### Shape A — Lightweight (Learning Cycle only)

One epic, one spike issue inside it.

- **Epic** — captures the full LDEM context. Description follows the Discovery Definition template (`assets/discovery-definition.md`). The epic stays alive across cycles — it gets updated as the initiative progresses.
- **Spike** (issue type "Spike" or "Task" depending on project config) — represents the time-boxed learning cycle. Title: "Learning cycle: [hypothesis summary]". Assignee + due date set.

### Shape B — Full (Learning → Delivery)

One epic, with sub-issues for each phase:

- Spike issue (Learning Cycle) — closes when the transition decision is made
- One or more stories (Delivery Cycle) — created only after Graduate
- An "Outcome verification" story at the end of delivery

### Shape C — Discovery-then-decide-later

Just an epic with the Discovery Definition embedded. No sub-issues yet. The team adds issues once they've confirmed the cycle is starting.

Recommend Shape A by default. Use Shape B when the engineer is past the transition and ready for delivery. Use Shape C when the engineer is still exploring and just wants the framing captured.

## Epic description structure

Put this in the epic description. Use the same headings as the Discovery Definition for consistency:

```
**Cycle:** Learning | Delivery | Mixed
**Stage:** Goal Definition | Problem Framing | Learning Cycle | Delivery Cycle

## Goal & metric
[Strategic objective + the metric that should move]

## Hypothesis
"If [action], then [outcome] will [direction] by [magnitude] [scope/timeframe]"

## Learning goal (Learning Cycle only)
[What must be proven? Problem-validation / feasibility / adoption / cost]

## Experiment (Learning Cycle only)
[Concrete description of what we'll run, on what data, against what baseline]

## Success criteria
[Specific thresholds — what counts as yes, what counts as no]

## Timebox
[1–3 weeks for Learning, 4–6 weeks for Delivery, with a target end date]

## Transition criteria (Learning Cycle only)
[The four criteria, with current status. Updated at end of cycle.]

## Decision (filled at end of Learning cycle)
[Graduate / Pivot / Stop, with evidence. Date filled in.]

## Links
[RFC, design doc, related epics, related discussion threads, related ADRs]
```

## What NOT to put in Jira

- Speculative metrics or fabricated numbers. If you don't have the baseline, write `[FILL: baseline]` in the description and tell the engineer it needs to be filled in before kickoff.
- Owners or dates the engineer didn't confirm.
- Decisions the team hasn't made. Don't pre-fill the Graduate/Pivot/Stop section.
- The full RFC text. Link to it instead.

## When the engineer wants you to create the issue directly

If they confirm and you have the appropriate Atlassian tools available, create the epic first, then any sub-issues with `parent` set to the epic. Use the `createJiraIssue` shape for the project's required fields (issue type, summary, description in ADF, parent). Surface the resulting issue keys + URLs in chat once done.

If anything fails (custom field required, permissions, project not found), surface the error verbatim and let the engineer decide how to proceed — don't retry creatively.

## Updating an existing epic

If the engineer points at an existing epic ("update PROJ-1234 with our Graduate decision"), use `getJiraIssue` first to see the current description, then `editJiraIssue` to update — preserve existing content; *append* the decision rather than overwriting. Show the proposed updated description in chat first, get confirmation, then make the call.
