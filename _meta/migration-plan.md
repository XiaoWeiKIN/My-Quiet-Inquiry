# Wei-Book · LLM Wiki 迁移覆盖矩阵

- 更新时间：2026-10-23
- Canonical Skill：[oh-my-skill/llm-wiki-maintainer](https://github.com/XiaoWeiKIN/oh-my-skill/tree/main/skills/llm-wiki-maintainer)
- 迁移范围：**main 原有 9 篇 legacy Markdown**（博弈论 5、系统思维 4）加上**本 PR 第一阶段新建的 1 篇秦史讨论稿**，合计 10 份来源材料
- 编译结果：**10 篇 canonical Wiki 知识页**（`_wiki/Home.md` 是额外的导航页）
- 溯源清单：[`_meta/ingest-manifests/legacy-coverage-2026-10.json`](ingest-manifests/legacy-coverage-2026-10.json)
- 处理策略：**旧文保留、新知识链接、错误明确修正、重复概念归并**。这里的“编译完成”不代表每项史实和类比均已完成学术级证明。

## A. 博弈论与决策：5 份原稿已覆盖

| 原稿 | canonical 目标 | 重点处理 |
| --- | --- | --- |
| `game-theory/centipede-game.md` | [蜈蚣博弈](../_wiki/GameTheory/蜈蚣博弈.md) | 修正终局收益与逆向归纳不自洽 |
| `game-theory/grossman-stiglitz-paradox.md` | [信息效率悖论](../_wiki/GameTheory/格罗斯曼-斯蒂格利茨悖论.md) | 信息成本矛盾不意味着市场必然消亡 |
| `game-theory/greater-fool-theory.md` | [博傻与凯恩斯选美](../_wiki/GameTheory/博傻与凯恩斯选美博弈.md) | 区分转售预期、高阶信念；过滤郁金香与牛顿轶事 |
| `game-theory/utility-vs-speculation.md` | [效用与投机决策](../_wiki/GameTheory/效用与投机决策.md) | 避免把止损点和跌价当作普遍证伪条件 |
| `game-theory/reflexivity-theory.md` | [反身性与反馈回路](../_wiki/SystemsThinking/反身性与反馈回路.md) | 与系统思维反身性文章共编译，避免双 canonical 来源 |

## B. 系统思维：5 份原稿已覆盖

| 原稿 | canonical 目标 | 重点处理 |
| --- | --- | --- |
| `systems-thinking/reflexivity-causality-and-destiny.md` | [反身性](../_wiki/SystemsThinking/反身性与反馈回路.md)、[受约束能动性](../_wiki/SystemsThinking/命运与受约束能动性.md)、[思想比较](../_wiki/Philosophy/缘起无为与控制哲学比较.md) | 将金融反馈、生活路径与哲学类比分离 |
| `systems-thinking/destiny-as-dynamic-systems.md` | [受约束能动性](../_wiki/SystemsThinking/命运与受约束能动性.md)、[反身性](../_wiki/SystemsThinking/反身性与反馈回路.md) | 从长文提炼状态、行动、环境、随机扰动 |
| `systems-thinking/buddhism-daoism-reflexivity.md` | [思想比较](../_wiki/Philosophy/缘起无为与控制哲学比较.md)、[控制边界](../_wiki/SystemsThinking/控制边界与最小必要干预.md) | 哲学原义与现代控制隐喻分离 |
| `systems-thinking/action-and-control-in-complex-systems.md` | [控制边界](../_wiki/SystemsThinking/控制边界与最小必要干预.md)、[思想比较](../_wiki/Philosophy/缘起无为与控制哲学比较.md) | 将 BAFL 定位为个人行动清单，而非验证过的学术算法 |
| `systems-thinking/qin-unification-strategy-transition.md` | [秦统一问答](../_wiki/History/Questions/秦统一与秦朝速亡.md)、[战略转型](../_wiki/SystemsThinking/胜利后的战略转型.md) | 从历史事实中提炼可复用的阶段目标变化模型 |

## C. 不纳入知识编译的目录（已分类）

| 原目录 | 分类结论 | 处理 |
| --- | --- | --- |
| `presentations/scholarship-defense/` | Word/PowerPoint 办公附件 | 保留原文件，**不摄取内容** |
| `templates/book-note-template.md` | 旧版写作模板 | 保留，作为写作模板而非证据或 Wiki 判断 |

## 已识别并修正的主要风险

1. **数学不一致**：蜈蚣博弈终局 `Pass` 更优时，不能再倒推出终局 `Take`。
2. **定理过度外推**：信息效率悖论不意味着市场终结或“无限套利资金虹吸”。
3. **金融史轶事**：郁金香全国恐慌、牛顿语录、精确跌幅等需逐条核对，未直接纳入 durable 判断。
4. **泛化的交易规则**：投资和投机的风控手段取决于资金期限、策略和风险承受能力，止损不能机械化。
5. **概念等同**：不能把佛教“业”、道家“无为”、斯多葛伦理问题等同于现代状态模型。
6. **模型与实证混淆**：状态转移方程与 BAFL 是概念化框架，不是已拟合、验证的预测公式。

## 完成状态与后续维护

- ✅ main 原有 9 篇 legacy 笔记均保留了原路径；本 PR 新增的秦史讨论稿也予以保留，并链接到至少一张 canonical Wiki 页面。
- ✅ 每张正式知识页拥有 `type`/`updated`、相关出处与来自 `Index.md`、`_wiki/Home.md` 的入站导航。
- ✅ 旧结论和新综合分离；图表、模型和概念重复项已整理。
- ✅ 划分办公附件、写作模板与知识材料。
- ⚠️ 尚须人工审阅这次**超过三张** durable Wiki 页面的大范围变更。
- ⚠️ 通过 GitHub connector 完成内容回读与静态检查；由于当前环境无法解析 GitHub 域名，原 Skill 的 Python `wiki_ingest.py`、`wiki_lint.py` 并未直接运行。结果见 [lint 报告](lint-reports/2026-10-23-wiki-migration.md)。
- ⚠️ 不等于原始论文、古代经典、市场历史材料的逐条全面校勘。新资料进入仓库时按源笔记重新验证有争议的具体论断即可；**遗留文章迁移清单已无未覆盖项**。

## 后续新资料的标准流程

1. 先保存来源于 `_sources/inbox/YYYY-MM/`，注明来源版本与获取时间。
2. 运行 Skill 的 `wiki_ingest.py plan`，记录原文哈希、待影响页面、3–7 条核心主张。
3. 更新或创建少量 Wiki 页面，保留证据差异与判断边界。
4. 通过 `wiki_ingest.py process` 与 Wiki/Sources 双 profile lint。
5. 更新导航、维护日志；超过三张知识页或涉及争议需人工 PR 审阅。
