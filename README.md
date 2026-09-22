# Design Workflow Skills

面向产品设计师的 Codex Skills，覆盖局部 UI 评审、功能交付、复杂专题评审和视觉方向探索。根据设计阶段与任务范围选择技能，并保留各技能的人类决策边界。

Codex skills for product designers: local UI review, feature handoff, complex design review, and visual direction exploration.

## 技能目录 / Skills

| 技能 | 适用任务 | 使用入口 | 当前形态 |
| --- | --- | --- | --- |
| L1 × AI 设计评审 | 已完成的单页、局部 UI 小型迭代 | [使用指南](l1-ai-design-review-guide.md) · `$l1-ai-design-review` | [技能目录](l1-ai-design-review/SKILL.md) |
| L2 × AI 设计交付 / 开发沟通 | 已完成的中型功能，整理开发与测试交付包 | [使用指南](l2-ai-ui-dev-handoff-guide.md) · `$ai-ui-dev-handoff` | [技能目录](ai-ui-dev-handoff/SKILL.md) |
| L3 × AI 设计评审：验证与沉淀 | 多角色、多状态的复杂专题，建立可复验证据 | `$l3-ai-design-review`；详见包内 `SKILL.md` | [ZIP 包](l3-ai-design-review.zip) |
| L4 × AI 视觉方向探索 | 0→1 产品的 A/B/C 视觉方向比较与决策 | `$l4-ai-visual-direction-exploration`；详见包内 `SKILL.md` | [ZIP 包](l4-ai-visual-direction-exploration.zip)，**Candidate / 候选版本** |

L1–L3 面向不同规模的已完成设计评审或交付；L4 面向视觉方向探索，不是必须依次执行的四个步骤。L4 的候选状态与升级条件以包内说明为准。

## 安装 / Installation

以下命令适用于 macOS 终端。先下载仓库 ZIP 并解压，或克隆仓库后进入根目录：

```bash
git clone --branch UI-Workflow-skills https://github.com/PaperMoonuu/Design-workflow-skills.git
cd Design-workflow-skills
```

技能默认安装到 `~/.codex/skills`；若配置了 `CODEX_HOME`，则使用该目录下的 `skills`。保留完整技能文件夹，包括 `agents` 和 `references`（如有）。

### L1 / L2：从目录安装

以 L1 为例；安装 L2 时将 `skill` 改为 `ai-ui-dev-handoff`：

```bash
skill=l1-ai-design-review
skills_dir="${CODEX_HOME:-$HOME/.codex}/skills"
mkdir -p "$skills_dir"
if [ -e "$skills_dir/$skill" ]; then
  echo "目标技能已存在，请先比较差异并备份，再手动更新：$skills_dir/$skill"
else
  cp -R "$skill" "$skills_dir/"
fi
```

### L3 / L4：从 ZIP 安装

解压所需 ZIP，找到包含 `SKILL.md` 的同名技能文件夹，再完整复制到上述技能目录。若目标已存在，先比较差异并备份，不要直接合并覆盖。无需复制 ZIP 中的 `__MACOSX` 或 `._*` 文件。

安装后的目录应类似：

```text
skills/
└── l3-ai-design-review/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/evidence-template.md
```

### 验证安装

回到 Codex 发送下一条消息，使用相应的 `$技能名` 并附任务材料；若未识别，再新开会话或重启应用。

```text
使用 $l1-ai-design-review 评审这份已完成的局部 UI 设计稿。
使用 $ai-ui-dev-handoff 将这个中型功能整理为可开发、可测试的交付包。
使用 $l3-ai-design-review 评审这个多角色工作流，并区分设计证据与运行证据。
使用 $l4-ai-visual-direction-exploration 探索这个产品的三套视觉方向。
```

技能提供任务方法；读取 Figma 等外部资源仍需对应工具与访问权限。静态设计稿不能替代真实运行、接口或权限验证。

## 反馈 / Feedback

通过 [Issues](https://github.com/PaperMoonuu/Design-workflow-skills/issues) 报告问题。请提供技能名称、使用场景、预期与实际结果，以及不含敏感信息的最小复现材料。
