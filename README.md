# aso-keyword-planner-skill

A reusable OpenClaw AgentSkill for ASO + Apple Search Ads keyword planning.

This skill helps analyze:
- app metadata and market context
- ASA campaign exports
- competitor ASO keyword sheets
- self ASO keyword sheets
- keyword coverage, priority, and difficulty
- Feishu document generation for final keyword strategy deliverables

## What this skill does

Given structured inputs, it can guide an agent to:
1. identify self-covered keywords
2. compare self vs competitor keyword positions
3. recommend primary / secondary / risky keywords
4. produce 3-keyword prioritization
5. judge relative difficulty for pushing keywords higher
6. suggest ASA structure and negative keyword logic
7. generate a Feishu document with the final plan

## Best-fit use cases

- country-level ASO keyword planning
- ASA keyword prioritization
- DACH or multilingual market keyword design
- competitor vs self ASO gap analysis
- deciding which 3 keywords to buy and push first
- building a reusable Feishu keyword strategy document

## Skill contents

```text
.agents/skills/aso-keyword-planner/
├── SKILL.md
└── references/
    ├── dach-songdio-example.md
    ├── example-output.md
    └── intake-template.md
```

## Included references

### `dach-songdio-example.md`
A real DACH case based on Songdio vs Suno keyword analysis.

### `intake-template.md`
A standard input collection template for future runs.

### `example-output.md`
A standard output example showing expected recommendation structure.

## Packaged skill

This repo also includes the packaged skill file:

```text
aso-keyword-planner.skill
```

## Typical inputs

- App name
- App ID or App Store URL
- target country / region
- core functions
- goal
- budget / target CPA
- ASA campaign data
- search term report
- competitor ASO keyword sheet
- self ASO keyword sheet
- competitor list

## Typical outputs

- input summary
- keyword insight summary
- recommended keyword tiers
- execution priority
- ASA campaign guidance
- Feishu document link

## Notes

- The skill is designed to avoid fabricating download volume or exact rank-driving numbers.
- Difficulty judgments are relative unless direct heat / trend evidence is provided.
- The current skill is especially strong for DACH-style, self-vs-competitor keyword planning workflows.
