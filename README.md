# 生意四问 · Business Four Questions

用四个问题判断一个生意值不值得做，并给出最低成本的验证方案。
An Agent Skill that scores a business idea with four questions and designs a low-cost validation test.

| 问题 | Question |
|---|---|
| 谁最痛？能否具体描述人群 | Who hurts most, and can you name them? |
| 何时最急？什么场景让他现在就想解决 | When is it most urgent? |
| 如何找到我？他会搜索什么、在哪里出现 | How will they find you? |
| 窗口有多久？如何最低成本验证并快速放大 | How long is the window, and how do you validate cheaply? |

## 功能 · Features

- 每问0–25分，满分100：80分以上马上验证，60–79分先补最弱项，40–59分换场景再看，低于40分放弃。
  Each question is scored 0–25 (100 total), with clear go / fix / pivot / drop bands.
- 一票否决：合规阻断、安全责任、痛的人不付钱、获客成本高于毛利。
  Veto checks for compliance blockers, safety liability, payer mismatch and unit economics.
- 输出7天、千元以内的验证实验，写明通过线与止损线，并给出提分改进方向。
  Outputs a 7-day, sub-¥1000 validation experiment with pass/stop thresholds, plus improvement moves.
- 可同时比较多个点子，并指出分差来自哪一问。
  Compares multiple ideas side by side and shows which question drives the gap.

## 示例 · Example

在医院儿科输液区卖便宜耐用的儿童露营推车（84分，做），对比在医院门口卖气球（33分，不做）。两者人流相同，分差来自“谁最痛”和“何时最急”。完整评分见 [`references/calibration-examples.md`](references/calibration-examples.md)。

A cheap, sturdy kids' wagon sold near a pediatric IV ward scores 84 (go); balloons at the hospital gate score 33 (drop).

## 使用 · Usage

把本目录放入支持 [Agent Skills](https://agentskills.io) 的智能体的技能目录，然后直接说：
Place this folder in your agent's skills directory, then ask:

> 用生意四问评估一下：在写字楼楼下卖现做沙拉
> Evaluate this business idea with the four questions: ...

## 结构 · Structure

```
business-four-questions/
├── SKILL.md                          # 工作流程、评分表、输出格式
└── references/
    └── calibration-examples.md       # 露营推车 vs 气球校准样例
```
