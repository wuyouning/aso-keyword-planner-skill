# aso-keyword-planner-skill

一个可复用的 OpenClaw AgentSkill，用于 **ASO + Apple Search Ads（ASA）关键词规划**。  
A reusable OpenClaw AgentSkill for **ASO + Apple Search Ads keyword planning**.

---

## 中文说明

### 这个 Skill 是做什么的
这个 skill 用来处理下面这类工作：
- 分析 App 在某个国家 / 地区的 ASO 关键词机会
- 对比 **自身 ASO 关键词表** 和 **竞品 ASO 关键词表**
- 结合 **ASA 广告系列数据** 给出主推词、测试词、风险词
- 判断某个词是否已经被自身覆盖
- 判断某个词更适合做 **ASA 投放**、**ASO 冲榜**，还是两者联动
- 输出一个可直接复用的 **飞书文档**

### 适用场景
适合以下需求：
1. 想做某个国家 / 地区的关键词推荐
2. 想判断“买哪 3 个词最值”
3. 想分析 self vs competitor 的关键词差距
4. 想做 DACH / 多语言市场关键词规划
5. 想把分析结果沉淀成飞书文档

### 典型输入
你可以给这个 skill 提供：
- App 名称
- App ID / App Store 链接
- 目标国家 / 地区
- 产品核心功能
- 投放目标
- 预算 / 目标 CPA
- ASA 历史广告数据
- Search Term Report
- 竞品 ASO 关键词表
- 自身 ASO 关键词表
- 点点数据热度 / 竞品线索

### 典型输出
这个 skill 会引导 agent 输出：
- 输入摘要
- 关键词洞察总结
- 主推关键词 / 次推关键词 / 风险词
- 3词推荐结论
- 冲榜难度判断
- ASA campaign 结构建议
- 飞书文档链接

### 当前内置案例
当前 skill 已经内置了一个真实案例参考：
- **Songdio vs Suno，德国 / 奥地利 / 瑞士（DACH）关键词分析**

它适合用于：
- 音乐生成类产品
- 德语区关键词规划
- self / competitor 关键词表对比
- 3词推荐和冲榜优先级分析

---

## English Overview

### What this skill does
This skill is designed for:
- country-level ASO keyword planning
- comparing self ASO keyword sheets vs competitor keyword sheets
- combining ASA campaign evidence with ASO signals
- deciding which keywords to buy first
- deciding which keywords are better for ASO ranking pushes
- generating a Feishu document with the final strategy

### Best-fit use cases
- keyword planning for a target country or region
- 3-keyword prioritization
- self vs competitor keyword gap analysis
- DACH / multilingual market planning
- reusable Feishu keyword strategy reports

---

## Repository structure

```text
aso-keyword-planner/
├── SKILL.md
└── references/
    ├── dach-songdio-example.md
    ├── example-output.md
    └── intake-template.md

aso-keyword-planner.skill
README.md
PUBLISHING.md
```

---

## Included references

### `references/intake-template.md`
标准输入模板，用于收集项目基础信息和分析材料。  
Standard intake template for collecting business inputs.

### `references/example-output.md`
标准输出示例，用来约束最终输出结构。  
Example output showing the expected recommendation format.

### `references/dach-songdio-example.md`
真实案例参考，沉淀了 Songdio / Suno / DACH 的关键词分析流程。  
A real DACH case reference based on Songdio vs Suno.

---

## Packaged skill

仓库已包含打包后的 skill 文件：

```text
aso-keyword-planner.skill
```

如果修改了 skill 内容，需要重新打包。

---

## Repackage command

```bash
python3 ~/.nvm/versions/node/v24.14.0/lib/node_modules/openclaw/skills/skill-creator/scripts/package_skill.py /Users/martin/.openclaw/workspace-aso/.agents/skills/aso-keyword-planner
```

---

## Notes

- This skill avoids fabricating exact install counts or ranking volume requirements.
- Difficulty judgments are relative unless direct trend / heat evidence exists.
- The current version is especially strong for DACH-style, self-vs-competitor keyword planning workflows.

---

## Future improvements

可继续增强的方向：
- 增加更多国家 / 地区案例
- 增加点点数据热度解释模板
- 增加 Excel 自动解析脚本
- 进一步优化飞书文档输出模板
