# Wei-Book · LLM Wiki 渐进式迁移计划

- 记录时间：2026-10-23
- Canonical skill: [llm-wiki-maintainer](https://github.com/XiaoWeiKIN/oh-my-skill/tree/main/skills/llm-wiki-maintainer)
- 当前范围：仅编译“秦统一、博弈论与主要矛盾”讨论；其余已存在的 Markdown 仍视为 legacy。
- 原则：先索引、后核验、再编译；不破坏源文件与链接；摄取影响超过三个 durable 页面时先人工复核。
- 元数据：Wiki 页面需要 `type`、`updated`、来源与入站导航；易过时的判断额外使用 `as_of` / `review_after`。

## 当前已完成的编译

| 来源 | 编译目标 | 状态 |
| --- | --- | --- |
| `_sources/conversations/2026-10/qin-unification-conversation.md` | `_wiki/History/Questions/秦统一与秦朝速亡.md` | 已整理 |
| 同上 | `_wiki/SystemsThinking/胜利后的战略转型.md` | 已整理 |
| `systems-thinking/qin-unification-strategy-transition.md` | 作为原长文保留并从 Wiki 链回 | 原文未删改 |

## 待审阅和迁移的 legacy 主题

| 批次 | 旧文件 | 拟迁移内容与注意事项 |
| --- | --- | --- |
| A | `game-theory/centipede-game.md` | **已编译至 `_wiki/GameTheory/蜈蚣博弈.md`**；修复收益矩阵和逆向归纳不一致，原文保留待后续核验实验数据 |
| A | `game-theory/greater-fool-theory.md`, `game-theory/grossman-stiglitz-paradox.md` | 经济与信息博弈，区分可验证事实与市场解释 |
| A | `game-theory/utility-vs-speculation.md` | 效用、风险与策略；避免将规范性建议当作一般定理 |
| B | `game-theory/reflexivity-theory.md` | 与系统思维下已有反身性笔记交叉；优先合并概念而非复制 |
| B | `systems-thinking/reflexivity-causality-and-destiny.md`, `systems-thinking/destiny-as-dynamic-systems.md` | 反身性、缘起和状态转移存在重叠，计划编译到可复用的反馈概念与综合问答 |
| B | `systems-thinking/buddhism-daoism-reflexivity.md` | 保留思想传统与现代模型的概念边界；避免将类比描述成同一理论 |
| B | `systems-thinking/action-and-control-in-complex-systems.md` | 控制边界、干预和复杂系统；抽取通用概念 |
| C | `presentations/`, `templates/` | 归档和模板，不默认转成 Wiki；单独评估材料来源和文件引用 |

## 迁移阶段

1. **收集来源**：为既有笔记补齐可追溯材料，记录原始路径与内容哈希；不会只凭旧结论再生产“来源”。
2. **概念去重**：优先查已有 Wiki 和别名，确定完整影响范围，再拆分、合并或更新概念。
3. **分批编译**：每批生成 manifest，明确支持/挑战/未知的主张；不超过三个受影响 durable 页的批次可直接进入 PR，超过则单独发起人工审阅。
4. **验证与索引**：执行 Skill 的 `wiki_ingest.py plan/process`、`wiki_lint.py --profile wiki` 和 `--profile sources`；GitHub 无脚本执行环境时，仅把连接器静态检查标为“辅助验证”，不能视为脚本测试通过。
5. **维护反馈**：更新 `_wiki/Home.md`、`Index.md`、`_meta/log.md`，在后续 PR 中记录去重和冲突的处理依据。

## 当前不做的事项

- 不一口气移动/重命名全部旧笔记，避免打断旧的外部链接。
- 不复制同一个综合结论到 `game-theory/` 和 `systems-thinking/` 两套 canonical 页面。
- 不把 ChatGPT 对话总结、史料解读与历史的一手证据混成一种引用。
- 不把 Skill 仓库副本直接复制到本仓库，仍以 oh-my-skill 为 canonical source。
