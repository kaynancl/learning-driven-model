# learning-driven-model

A Claude Code plugin that coaches engineers through the **Learning-Driven Execution Model (LDEM)** — a same-team approach that alternates between **Build-to-Learn** (Learning Mode) and **Build-to-Earn** (Delivery Mode), with explicit hypotheses, time-boxed cycles, and evidence-based **Graduate / Pivot / Stop** transitions.

The plugin ships as a single Claude Code skill that triggers on engineering proposals where uncertainty is high — fuzzy problems, unproven feasibility, "should we even build this?" questions. It coaches; it does not gatekeep.

## What it helps you do

- **Frame a new initiative** — sharpen the hypothesis, set a baseline, scope a learning cycle.
- **Review an existing RFC, design doc, or epic** against LDEM and surface gaps.
- **Decide Graduate / Pivot / Stop** at the end of a learning cycle, walking the four transition criteria.
- **Decide whether work belongs in Learning Mode at all** — discovery is not for everything.

## Why this exists

Engineering teams routinely commit to building before validating the problem is real, leave hypotheses implicit, define success criteria too late, and lose the learning between initiatives. LDEM is one way to close that gap — and this plugin turns the model into a coaching partner you can pull into any session.

## Installation

This is a [Claude Code](https://www.anthropic.com/claude-code) plugin. With Claude Code installed, point the plugin loader at this repository:

```bash
# Clone the repo
git clone https://github.com/kaynancl/learning-driven-model.git
cd learning-driven-model

# Install into your Claude Code plugins directory
# (see Claude Code docs for the current install path on your platform)
```

Once installed, the skill triggers on phrases like *"build to learn"*, *"learning cycle"*, *"spike"*, *"graduate this"*, *"pivot or stop"*, *"is this ready to ship"*, *"is my hypothesis sharp"*, *"review my RFC"*, *"frame a hypothesis"*, *"set transition criteria"* — or any open-ended engineering proposal with high problem or solution uncertainty.

## Repository layout

```
.
├── .claude-plugin/
│   └── plugin.json                       # plugin manifest
└── skills/
    └── learning-driven-execution/
        ├── SKILL.md                      # entry router + coaching stance
        ├── references/                   # stage-specific guides (loaded as needed)
        │   ├── model-overview.md
        │   ├── stage-1-goal.md
        │   ├── stage-2-frame.md
        │   ├── stage-3-learn.md
        │   ├── stage-4-deliver.md
        │   ├── transition-decision.md
        │   ├── when-to-discover.md
        │   ├── proposal-review.md
        │   └── jira-output.md
        └── assets/                       # fill-in templates
            ├── discovery-definition.md
            ├── transition-record.md
            └── jira-epic-structure.md
```

## The model in one minute

| Mode | Goal | Output | Typical length |
| --- | --- | --- | --- |
| **Learning Mode (Build to Learn)** | Reduce uncertainty about a problem or solution | A decision — Graduate, Pivot, or Stop — backed by evidence | 1–3 weeks |
| **Delivery Mode (Build to Earn)** | Deliver production value for a validated bet | Deployed system + measurable outcome shift | 4–6 weeks |

A learning cycle ends with a written decision against **four transition criteria**:

1. **Hypothesis validated** — evidence supports it; limits are documented.
2. **Technical feasibility demonstrated** — prototype ran under realistic constraints, not demo conditions.
3. **Impact is measurable** — target metric defined, baseline set, production instrumentable.
4. **Cost is justified** — effort is proportional to expected impact vs. alternatives.

Graduate only when **all four** are true. Otherwise: **Pivot** (re-frame, run another short cycle) or **Stop** (kill with evidence; document the learning).

**Stop with evidence is a successful outcome.** A team that kills three weak ideas early has freed capacity for higher-impact work.

For a deeper walk-through, read [`skills/learning-driven-execution/references/model-overview.md`](skills/learning-driven-execution/references/model-overview.md).

## Contributing

Issues and pull requests welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[MIT](LICENSE).
