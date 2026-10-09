# 🧭 生意四问 / Business Four Questions

用四个问题给生意点子打分的 Agent Skill：输入一个点子，输出 100 分制评分、一票否决检查、7 天低成本验证实验和提分改法。

适用于摆摊、小生意、副业、选品、创业想法，以及多个点子的横向对比。

An Agent Skill that scores business ideas with four questions — who hurts most, when it's most urgent, how buyers find you, and how long the window lasts. Get a 100-point score, veto checks, a 7-day low-cost validation test, and concrete fixes for the weakest question.

遵循 [Agent Skills 开放标准](https://agentskills.io)，兼容 Claude Code、Cursor、GitHub Copilot、Codex、Windsurf、Gemini CLI、Perplexity Computer 等 AI Agent 平台。

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## 安装 / Install

```bash
npx skills add Ficere/business-four-questions
```

> 需要 Node.js。安装后 Agent 会自动发现并按需加载该技能。
>
> Requires Node.js. Once installed, your agent will auto-discover and load this skill when relevant.

<details>
<summary>其他安装方式 / Alternative methods</summary>

**手动安装 / Manual install：**

```bash
git clone https://github.com/Ficere/business-four-questions.git
# 将整个目录复制到你的 Agent 的 skills 目录下即可
# Copy the directory to your agent's skills folder:
#   Claude Code:  ~/.claude/skills/
#   Cursor:       .cursor/skills/
#   Copilot:      .github/skills/
#   Codex:        ~/.codex/skills/
#   Gemini CLI:   .gemini/skills/
```

**Perplexity Computer：**

下载本仓库 zip → 在 [Skills 管理页面](https://www.perplexity.ai/computer/skills) 上传。

</details>

## 使用 / Usage

安装后直接用自然语言触发，无需任何配置：

```
用生意四问评估一下：在写字楼楼下卖现做沙拉，一份 25 元
```

```
在医院儿科门口卖儿童露营推车和卖气球，哪个更好？
```

```
我想做宠物上门喂养副业，帮我设计一个一周内能跑完的验证方案
```

```
这三个选品方向帮我打分排序，并说说最弱的一项怎么补
```

## 四个问题 / The Four Questions

| 问题 | Question | 看什么 |
|------|----------|--------|
| **谁最痛** | Who hurts most? | 人群能否具体到一眼认出；痛有多重；现有替代有多差；付钱的人是不是痛的人 |
| **何时最急** | When is it urgent? | 有没有明确的触发场景；是否当场就要解决；着急时还在不在乎价格 |
| **如何找到我** | How do they find you? | 他会搜什么词、出现在哪个点位或社区；能否低成本守在那里 |
| **窗口多久** | How long is the window? | 验证要花多少钱和时间；能否复制放大；多容易被模仿 |

## 功能 / Features

| 模块 | 说明 |
|------|------|
| **四问评分** | 每问 0–25 分，满分 100，每项写出具体人群、场景、搜索词或点位 |
| **一票否决** | 合规阻断、安全责任、付钱的人不痛、获客成本高于毛利，命中即封顶 39 分 |
| **证据分层** | 真实计划可检索竞品与热度，结论标注为数据、推断或假设 |
| **低成本验证** | 7 天、千元以内的验证实验，写明通过线、止损线和放大路径 |
| **提分改法** | 针对最弱一问给出换人群、换场景、换卖法或换渠道的具体改法 |
| **多点子对比** | 并列打分，指出分差来自哪一问 |

<details>
<summary>评分档位 / Score bands</summary>

| 总分 | 结论 |
|------|------|
| 80 分以上 | 做，马上验证 |
| 60–79 分 | 改后做，先补最弱的一问 |
| 40–59 分 | 换场景或人群再看 |
| 40 分以下 | 不做 |

</details>

<details>
<summary>校准样例 / Calibration example</summary>

| 生意 | 总分 | 结论 |
|------|------|------|
| 在医院儿科输液区附近卖便宜耐用的儿童露营推车 | 84 | 做 |
| 在医院门口卖气球 | 33 | 不做 |

两者人流相同，分差来自「谁最痛」和「何时最急」：推车解决的是输液那几个小时里抱孩子、举吊瓶的身体负担，气球只提供可有可无的情绪价值。完整评分见 [`references/calibration-examples.md`](references/calibration-examples.md)。

</details>

## 目录结构 / Structure

```
business-four-questions/
├── SKILL.md                       # 技能入口（Agent 自动读取）：流程、评分表、输出格式
├── references/
│   └── calibration-examples.md    # 露营推车 vs 气球的完整对照评分
├── LICENSE
└── README.md
```

## 免责声明 / Disclaimer

本技能输出基于公开信息和经验判断的评估，不构成投资、法律或财务建议。是否投入请以真实客户验证和专业意见为准。

Outputs are judgment-based assessments, not investment, legal, or financial advice. Validate with real customers before committing resources.

## License

[MIT](LICENSE)
