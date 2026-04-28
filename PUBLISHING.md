# Publishing Notes

## Repo

GitHub:
- https://github.com/wuyouning/aso-keyword-planner-skill

## Main artifacts

- skill source: `.agents/skills/aso-keyword-planner/`
- packaged file: `aso-keyword-planner.skill`

## What to verify before publishing elsewhere

1. `SKILL.md` is up to date
2. reference files match the current workflow
3. packaged `.skill` file is regenerated after changes
4. README reflects the latest supported use cases

## Repackage command

```bash
python3 ~/.nvm/versions/node/v24.14.0/lib/node_modules/openclaw/skills/skill-creator/scripts/package_skill.py /Users/martin/.openclaw/workspace-aso/.agents/skills/aso-keyword-planner
```

## Current positioning

This skill is designed for:
- ASO keyword recommendation
- ASA keyword planning
- self vs competitor sheet comparison
- 3-keyword recommendation mode
- Feishu document generation workflow

## Future improvements

- add more country-specific references
- add point-data / 点点数据 interpretation examples
- add a more explicit Excel parsing helper script if repeated often
- optionally publish to clawhub after final cleanup
