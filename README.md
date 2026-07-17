# L1 × AI 设计评审 / L1 × AI Design Review

适用于 **macOS + Codex 桌面端** 的团队设计 Skill。

A team design skill for **macOS + Codex Desktop**.

**调用名 / Invocation:** `$l1-ai-design-review`

## 30 秒判断：现在该不该用？ / 30-Second Fit Check

同时满足以下三项，就使用本 Skill：

Use this skill when all three conditions are true:

- 设计稿、改动前后稿或可评审原型已经完成。

  The design file, before/after designs, or reviewable prototype is complete.

- 改动是单页局部的小型迭代，例如字段、提示、筛选、局部模块、空 / 异常状态或单页交互。

  The change is a small, local, single-page iteration, such as a field, hint, filter, local module, empty/error state, or interaction.

- 你需要在进入开发前检查影响面、状态遗漏、文案和验收项。

  You need to check impact, missing states, copy, and acceptance criteria before development.

以下情况不要使用：设计稿尚未完成、完整功能 / 流程、多页面或多角色专题，或需要直接输出开发规格。

Do not use it for incomplete designs, full features or flows, multi-page or multi-role topics, or direct development specifications.

## 它能帮你做什么？ / What It Does

- 检查局部改动的影响面、任务路径、层级、文案和局部一致性。

  Checks the impact surface, task path, hierarchy, copy, and local consistency.

- 检查默认、选择、禁用、加载、空、错误、成功、长内容和窄屏 / 溢出状态。

  Checks default, selected, disabled, loading, empty, error, success, long-content, and narrow-screen/overflow states.

- 按 P0 / P1 / P2 给出可执行修改建议和验收清单。

  Produces actionable P0/P1/P2 recommendations and an acceptance checklist.

- 发现权限、生命周期、上传 / 提交、字段 / 配置契约、多页面或多角色联动时，标记 **L2 移交**。

  Marks an **L2 handoff** when permissions, lifecycle, upload/submission, field/configuration contracts, or multi-page/multi-role dependencies are involved.

它不替代产品、开发或测试对 L2 问题的判断，也不会猜测接口、权限、审计或技术方案。

It does not replace product, engineering, or QA decisions for L2 issues, and it does not guess APIs, permissions, audit rules, or technical solutions.

## 安装 / Installation

1. 下载本仓库的 ZIP，或克隆仓库；保留 `l1-ai-design-review` 文件夹完整结构。

   Download this repository as a ZIP or clone it. Keep the complete `l1-ai-design-review` folder structure.

2. 打开「终端」，在仓库下载位置执行：

   Open Terminal and run the following command from the downloaded repository location:

```bash
mkdir -p ~/.codex/skills
cp -R l1-ai-design-review ~/.codex/skills/
```

3. 重启 Codex 桌面端，或新开一个会话。

   Restart Codex Desktop or open a new conversation.

4. 输入以下语句；若 Codex 识别并执行评审，安装成功：

   Enter the following request. Installation is complete when Codex recognizes and runs the review:

```text
使用 $l1-ai-design-review 评审这份已完成的局部 UI 设计稿。
Use $l1-ai-design-review to review this completed local UI design change.
```

安装后路径应为：`~/.codex/skills/l1-ai-design-review/`。请勿只复制单个文件。

The installed path should be `~/.codex/skills/l1-ai-design-review/`. Do not copy only individual files.

## 怎么使用？ / How to Use It

准备以下最小输入：

Prepare these minimum inputs:

- 已完成的设计稿、改动前后稿或可评审原型；

  Completed design, before/after designs, or a reviewable prototype;

- 当前页面上下文；

  Current page context;

- 改动说明和业务目标。

  Change description and business goal.

示例 / Examples:

```text
使用 $l1-ai-design-review 评审这个 Figma 页面新增的附言模块。
Use $l1-ai-design-review to review the new note module on this Figma page.
```

```text
使用 $l1-ai-design-review 对比改动前后截图，检查这个筛选条件的交互与状态。
Use $l1-ai-design-review to compare before-and-after screenshots and check this filter's interactions and states.
```

默认会得到结论、P0 / P1 / P2 风险、可执行建议、L2 移交项（如有）和验收清单。信息不足时，Skill 会先索取最小缺失信息；若仍要求继续，只会给出“基于假设的初评”。

By default, you receive a conclusion, P0/P1/P2 risks, actionable recommendations, L2 handoff items when applicable, and an acceptance checklist. If information is incomplete, the skill requests the minimum missing inputs; if you continue without them, it returns only an assumption-based initial review.

## 常见场景 / Common Scenarios

| 场景 / Scenario | 是否使用 / Use It? |
| --- | --- |
| 审批详情页新增一段附言 / Add a note to an approval detail page | 使用 / Yes |
| 首页新增快捷提示词与输入插槽 / Add quick prompts and an input slot on the home page | 使用 / Yes |
| 新增包含表单、列表、配置和权限的完整模块 / Add a complete module with forms, lists, configuration, and permissions | 不直接使用，属于 L2 / Not directly; this is L2 |
| 经营看板、工作台、会员体系等多页面专题 / A multi-page dashboard, workbench, or membership topic | 不使用，属于 L3 / No; this is L3 |
| 只有 PRD，尚未出设计稿 / Only a PRD exists; the design is not ready | 不使用，先做设计前预检 / No; use design preflight first |

## 质量边界 / Quality Boundary

本 Skill 已由两类真实设计后案例验证：审批详情页附言模块、快捷提示词 / 输入插槽。后续会继续用不同类型的 L1 改动校验边界稳定性，但不影响当前日常使用。

This skill has been validated with two types of real post-design cases: an approval-detail note module and quick prompts with an input slot. Further L1 cases will continue to test boundary stability without blocking day-to-day use.
