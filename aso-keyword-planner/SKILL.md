---
name: aso-keyword-planner
description: Generate ASO and Apple Search Ads keyword recommendations from user-provided app info, ASA campaign data, competitor ASO keyword sheets, and self ASO keyword sheets. Use when the user wants keyword planning, keyword prioritization, three-keyword recommendations, keyword difficulty judgment, coverage checks, or a Feishu document summarizing keyword strategy and campaign structure for specific countries or regions.
---

# ASO Keyword Planner

Build a reusable ASO + ASA keyword recommendation package from structured business inputs.

## Core workflow

1. Collect the minimum required inputs.
2. Classify the request mode.
3. Analyze keyword coverage from self and competitor data.
4. Rank keyword opportunities by relevance, coverage depth, monetization intent, and execution difficulty.
5. Output prioritized keyword recommendations.
6. Create a Feishu document when the user asks for a saved deliverable.

## Supported request modes

### Mode A: quick draft
Use when the user only provides:
- app name
- app ID or App Store URL
- target country or countries
- product core functions
- main goal
- budget / CPA target

Output:
- first-draft keyword pool
- recommended 3 to 10 keywords
- campaign structure suggestion
- risk notes

### Mode B: data-enhanced analysis
Use when the user additionally provides one or more of:
- ASA campaign export
- search term report
- competitor ASO keyword sheet
- self ASO keyword sheet
- 点点数据 keyword heat / competitor clues

Output:
- coverage judgment
- competitor gap analysis
- keyword priority tiers
- recommendation for which terms to buy first
- recommendation for which terms to push with ASO
- optional Feishu document

## Minimum required inputs

Collect these if missing:
- App name
- App ID or App Store URL
- target country / region
- core product functions
- main objective
- budget
- target CPA if applicable

## Strongly recommended inputs

Prefer to collect these when available:
- ASA historical campaign summary or export
- search term report
- competitor ASO keyword sheet
- self ASO keyword sheet
- competitor list
- current app title / subtitle / keyword field

## Intake reference

When the user starts from scratch or the request is underspecified, read:
- `references/intake-template.md`

Use that file to collect the minimum viable business inputs before analysis.

## Input priority

Use evidence in this order:
1. user-provided ASA campaign data
2. user-provided search term report
3. self ASO keyword sheet
4. competitor ASO keyword sheet
5. 点点数据 heat / popularity / competitor signals
6. semantic reasoning from product function and market language

## Spreadsheet handling

When the user provides ASO Excel sheets:
- inspect the workbook instead of guessing from the filename
- identify whether the sheet belongs to self or competitor
- identify country / locale from the sheet title row
- extract at least: keyword, rank, popularity, update time when present
- do not treat all visible keywords as worth buying
- separate high-signal terms from noise, typo terms, and weak-intent terms

If both self and competitor sheets are available:
- compare overlapping keywords
- note where self already has coverage
- note where competitor ranks much higher
- identify gaps where ASA can support ASO

## Real-case references

If the task resembles the Songdio / Suno / DACH workflow discussed in chat, read:
- `references/dach-songdio-example.md`

If you need an example of the final response shape, read:
- `references/example-output.md`

Use these references when the user asks for:
- Germany / Austria / Switzerland keyword planning
- music generation apps
- 3-keyword prioritization from self + competitor sheets
- ASO + ASA combined recommendations
- a Feishu doc summarizing the final plan

## Analysis rules

### 1. Coverage judgment
For each recommended keyword, explicitly decide:
- already covered by the app
- covered but weak ranking
- not covered or unclear

If ranking data is provided, cite the observed ranking.

### 2. Competitor comparison
Separate:
- competitor brand terms
- functional terms
- scenario terms
- noisy / misleading terms

Do not mix competitor terms with scenario terms in the final recommendation.

### 3. Recommendation logic
Prioritize keywords that satisfy most of these conditions:
- strong product relevance
- clear monetization or conversion intent
- evidence of competitor strength
- existing self coverage that can be improved
- manageable ranking difficulty

De-prioritize keywords that are:
- very broad with weak intent
- off-category
- likely to produce cheap but low-quality installs
- obvious noise from typo / homophone / unrelated traffic

### 4. Three-keyword recommendation mode
When the user asks for only 3 keywords, rank by:
1. business relevance
2. current self coverage
3. expected difficulty to push upward
4. expected return if ranked higher

State clearly:
- whether each keyword is already covered
- whether it is better for ASA, ASO, or both
- relative difficulty: low / medium / high

If one term is clearly too broad or too expensive to push now, propose a more practical local-language replacement.

### 5. Difficulty judgment
Do not invent exact download counts.
If the user asks how much volume is needed to reach rank 1, answer in relative terms unless trend and heat evidence exists.

Use this scale:
- low difficulty
- medium difficulty
- medium-high difficulty
- high difficulty

Base the judgment on:
- current rank depth
- title / subtitle relevance
- competitor rank strength
- keyword breadth and ambiguity
- market language fit

### 6. Language handling
For DACH or multilingual markets:
- consider both local-language and English functional terms
- keep local-language recommendations separate from English recommendations when useful
- avoid literal translations if the data suggests different real search behavior

## Fixed output structure

Always produce these sections unless the user asks for a narrower format.

### Section 1: input summary
- app
- target market
- objective
- available evidence
- assumptions

### Section 2: keyword insight summary
- self-covered terms
- competitor-strong terms
- opportunity terms
- risky / noisy terms

### Section 3: recommended keyword list
Use tiers such as:
- primary keywords
- secondary test keywords
- observation keywords
- negative / avoid keywords

### Section 4: execution priority
For each priority keyword, explain:
- current coverage status
- why it is recommended
- whether it is better for ASA / ASO / both
- relative difficulty

### Section 5: campaign / execution guidance
Include when the user asks for media buying or ASA planning:
- campaign structure
- exact vs broad suggestions
- competitor vs scenario split
- negative keyword ideas
- budget or CPA notes

### Section 6: Feishu document generation
When the user asks for a saved deliverable:
1. draft a clean Markdown report
2. create a Feishu doc
3. return the doc URL

## Feishu document title suggestions

Use one of these patterns depending on the task:
- `<Country> ASO关键词与ASA投放建议`
- `<Country> 核心关键词优先级与投放建议`
- `<Region> ASO / ASA 关键词规划方案`
- `<AppName> <Country> 关键词与广告投放方案`

## Safety and quality rules

- Do not fabricate heat, volume, or install counts.
- Distinguish evidence-backed conclusions from assumptions.
- Mark when a recommendation is based on semantic reasoning rather than direct market data.
- Prefer fewer stronger recommendations over long noisy lists.
- If the user wants a reusable execution package, include copy-ready keyword blocks.
- If self and competitor sheets conflict, prefer direct self coverage data for coverage judgment.

## Lightweight intake template

Use this when the user starts from scratch:

```text
App名称：
App ID / 链接：
目标国家 / 地区：
核心功能：
投放目标：
预算：
目标CPA：
历史ASA数据：有/无
竞品ASO词表：有/无
自身ASO词表：有/无
竞品名单：
当前标题 / 副标题 / 关键词字段：
是否需要飞书文档：是/否
```

## Feishu deliverable template

When generating the Feishu doc, prefer this structure:
- 背景与目标
- 数据输入与分析依据
- 核心关键词结论
- 关键词优先级分层
- ASA投放建议
- ASO强化建议
- 风险与后续动作
