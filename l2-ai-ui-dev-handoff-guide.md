# L2 × AI 设计交付 / 开发沟通

> **调用名 / Invocation:** `$ai-ui-dev-handoff`
> **技术标识 / Technical identifier:** `ai-ui-dev-handoff`

面向全链路产品设计师的 L2 交付 Skill：把已完成的中型功能设计转化为设计、产品、开发和测试共用的可执行交付包。

An L2 delivery Skill for end-to-end product designers. It turns a completed medium-sized feature design into an actionable handoff package shared by design, product, engineering, and QA.

## 为什么这样命名？ / Why This Naming?

展示名使用「L2 × AI 设计交付 / 开发沟通」，保留方法论矩阵中的功能量级和协作目标；调用名使用 `ai-ui-dev-handoff`，符合 Codex 对小写连字符标识的约定，便于在终端、目录、链接和英文环境中稳定使用。

The display name, “L2 × AI 设计交付 / 开发沟通,” preserves the method’s scope and collaboration goal. The invocation name, `ai-ui-dev-handoff`, follows Codex’s lowercase hyphenated convention and remains reliable in terminals, paths, links, and English-language contexts.

## 30 秒适配判断 / 30-Second Fit Check

同时满足以下条件时使用本 Skill：有完成设计稿或可评审原型；范围是一个完整功能、独立模块或 1–3 个紧密相关页面；能说明入口、关键操作和结果；并且涉及字段规则、异步/异常、角色/生命周期、动态操作、响应式中的至少两项。

Use this Skill when all of the following are true: a completed design or reviewable prototype exists; the scope is one complete feature, an independent module, or 1–3 related screens; the entry, key actions, and outcomes are known; and at least two of these are involved: field rules, asynchronous/error states, roles/lifecycle, dynamic actions, or responsive behavior.

不要用于只有 PRD 或想法的设计前阶段、单点视觉微调，或跨多个模块的 L3 专题。前者先做需求校准，后两者分别降级为 L1 或升级为 L3。

Do not use it for pre-design work with only a PRD or an idea, a one-off visual tweak, or a cross-module L3 topic. Use design preflight for the first case, L1 for the second, and L3 for the last.

## 核心功能 / Core Capabilities

| 功能 / Capability | 产出 / Output |
| --- | --- |
| 交付准入与风险分级 / Readiness and risk triage | 判断是否属于 L2，并将缺失项标为 P0/P1/P2 / Confirms L2 fit and classifies gaps as P0/P1/P2 |
| 事实台账 / Evidence ledger | 分离设计、PRD、代码中的事实与假设 / Separates sourced facts from assumptions |
| 规格转译 / Specification translation | 任务路径、组件契约、字段规则、提交映射 / Task paths, component contracts, field rules, and submission mappings |
| 权限与状态覆盖 / Permissions and state coverage | 角色 × 生命周期 × 行为、加载/空/错/成功/弱网/重复操作 / Role × lifecycle × behavior plus loading, empty, error, success, weak-network, and repeat-action states |
| 动态动作控制 / Dynamic action control | 配置来源、权限、节点资格、动态字段、草稿切换与恢复 / Configuration source, permissions, eligibility, dynamic fields, draft switching, and recovery |
| 联调与验收 / Handoff and acceptance | 可追溯待确认项与可测试验收矩阵 / Traceable open questions and a testable acceptance matrix |

## 典型场景 / Typical Scenarios

| 场景 / Scenario | 重点补齐 / What the Skill clarifies |
| --- | --- |
| 表单、新建、编辑、保存 / Form, create, edit, save | 必填、格式、默认值、失败保留、重复提交 / Required fields, formats, defaults, draft retention, duplicate submission |
| 搜索、筛选、配置、结果列表 / Search, filters, configuration, result list | 查询条件、空结果、加载/失败、分页、刷新一致性 / Query rules, empty results, loading/error, pagination, refresh consistency |
| 审批详情与可写历史 / Approval detail and writable history | 权限、生命周期、附件、提交后刷新、审计待确认项 / Permissions, lifecycle, attachments, post-submit refresh, audit gaps |
| 操作栏与动态表单 / Action bar and dynamic form | 动作来源、权限/节点资格、字段切换、幂等与失败恢复 / Action source, permission/eligibility, field switching, idempotency, recovery |
| 跨端交付 / Cross-platform handoff | 断点、信息优先级、固定操作区、键盘、长内容 / Breakpoints, priority, sticky actions, keyboard, long content |

## 最小输入 / Minimum Input

- 完成设计稿、原型或可运行实现，并附页面上下文；
- 目标用户、业务目标与完成标准；
- 入口 → 关键操作 → 成功/失败/退出路径；
- 已知字段、权限、生命周期与平台约束；
- 动态操作区另附动作列表、展示/可执行条件及动态字段。

- A completed design, prototype, or runnable implementation with page context;
- Target users, business goal, and completion criteria;
- Entry → key actions → success/failure/exit paths;
- Known fields, permissions, lifecycle, and platform constraints;
- For dynamic action areas: an action list, display/execution conditions, and dynamic fields.

## 使用方法 / How to Use

安装时保留 `ai-ui-dev-handoff` 文件夹的完整结构：

Keep the complete `ai-ui-dev-handoff` folder structure when installing:

```bash
mkdir -p ~/.codex/skills
cp -R ai-ui-dev-handoff ~/.codex/skills/
```

重启 Codex 桌面端或新开会话后，使用以下调用并粘贴你的设计和规则材料：

Restart Codex Desktop or open a new conversation, then invoke the Skill and provide your design and rules:

```text
使用 $ai-ui-dev-handoff，将这个已完成设计稿的中型功能整理为可开发、可测试的交付包。
Use $ai-ui-dev-handoff to turn this completed medium-sized feature design into a buildable, testable handoff package.
```

## 你会得到什么 / What You Receive

1. 交付就绪结论：可进入开发、可并行开发但有 P1，或 P0 阻塞。
2. 输入完整性、事实/假设、待确认项、责任方和确认时点。
3. 任务路径、组件契约、字段规则和提交映射。
4. 角色 × 生命周期 × 行为，以及状态、异常、响应式和可达性说明。
5. 动作配置矩阵（适用于动态操作区）。
6. 开发联调清单和可直接转为测试场景的验收矩阵。

1. A readiness verdict: ready for development, parallel development with P1 items, or P0 blocked.
2. Input completeness, facts/assumptions, open questions, owners, and deadlines.
3. Task paths, component contracts, field rules, and submission mappings.
4. Role × lifecycle × behavior, plus state, exception, responsive, and accessibility requirements.
5. An action configuration matrix for dynamic action areas.
6. Development handoff items and an acceptance matrix that QA can turn into test scenarios.

## 关键边界 / Critical Boundaries

Skill 不会猜测接口、错误码、服务端权限、附件限制、幂等、审计、通知、埋点、安全或性能方案。设计稿能证明视觉和部分交互，不能证明服务端资格；动作出现在 UI 中，也不代表当前用户和节点可以执行它。动态动作切换时，草稿应保留、清空还是阻止切换，必须被明确规定。

The Skill does not guess APIs, error codes, server permissions, attachment limits, idempotency, audit, notifications, analytics, security, or performance solutions. A design can prove visual behavior, not server-side eligibility. An action appearing in the UI does not mean the current user and workflow node can execute it. Draft retention, clearing, or blocking during dynamic action switches must be explicitly defined.


