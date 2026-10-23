# Lint Report · Wei-Book legacy → LLM Wiki

- Date: 2026-10-23
- Scope: `Index.md`, `_wiki/Home.md`, 10 canonical durable `_wiki/` notes; 9 pre-existing main-branch legacy notes plus one Qin draft created earlier in this PR; coverage tracked by `_meta/ingest-manifests/legacy-coverage-2026-10.json`.
- Mode: GitHub connector **readback and JavaScript static validation** with canonical `wiki_lint.py`-style rules.
- Environment: `git ls-remote https://github.com/XiaoWeiKIN/Wei-Book.git HEAD` failed with `Could not resolve host: github.com` in the local shell. Therefore `wiki_ingest.py` and `wiki_lint.py` were **not run**. Never represent this result as a passing canonical script run.

## Results

| Check | Result | Evidence |
| --- | --- | --- |
| Canonical pages | PASS (static) | 10 knowledge pages, excluding `_wiki/Home.md` |
| Obsidian wikilinks | PASS (static) | `[[...]]` targets parsed for Index and every `_wiki/` page; no unresolved targets |
| Relative Markdown links | PASS (static) | Local `[...](...)` links resolved against known repository paths; no broken page links |
| Durable inbound navigation | PASS (static) | All 10 knowledge pages linked from `Index.md` or another durable page |
| Required YAML fields | PASS (static) | All 10 pages have `type` and `updated` |
| Provenance heading | PASS (static) | Synthesis, query and comparison pages have recognized `资料与证据`/`来源` heading |
| Original legacy files preserved | PASS (connector compare) | 9 main-branch legacy paths remain unmodified; the additional Qin draft was introduced earlier in this PR and also preserved for provenance |
| Reusable topic deduplication | PASS (semantic spot check) | Reflexivity, agency, philosophy comparison and control methods have differentiated scopes |
| Canonical `wiki_lint.py --profile wiki` | NOT RUN | No checkout via working container |
| Canonical `wiki_lint.py --profile sources` | NOT RUN | No checkout via working container |
| Canonical `wiki_ingest.py plan/process` | NOT RUN for legacy migration | Legacy preserved in place; record is a `legacy-compile-1` manifest, not a synthetic inbox ingest |
| Original studies and historical anecdotes fully fact-checked | PARTIAL | Original papers referenced; some historical/philosophical source readings are future editorial refinements |

## Semantic corrections recorded

1. **蜈蚣博弈**：修正终局收益与逆向归纳相矛盾的旧模型。
2. **信息效率悖论**：去除“持续战胜市场必然导致交易市场消亡”的过度推论。
3. **博傻**：区别 Keynes 的高阶预期机制与简单接盘动机；郁金香、南海泡沫和人物轶事不按流行故事直接当成事实。
4. **效用/投机**：购买用途与价格风险分开；不将硬止损或“跌价意味着证伪”当成普适原则。
5. **反身性**：确认价格/预期改变基本面的因果通道才做强判断。
6. **命运/哲学**：状态方程、BAFL 是现代类比；佛教“业”、道家“无为”、斯多葛控制边界各有独立思想背景。

## Repairs performed in PR

- 建立可检索的十篇知识页与单一知识地图，并从旧目录链接回原始内容。
- 修复了新增页面的 Obsidian 链接别名，补齐 `Index.md`、Home 和 README。
- 新建 `_meta/ingest-manifests/legacy-coverage-2026-10.json`：Git blob SHA、原文路径、多对多编译目标和人工复核要求。
- 更新迁移台账，使十份原稿的覆盖状态可逐项核对。

## Human review gate

此 PR 涉及 **超过三张 durable Wiki 页面**，需要依 Skill 的规则由仓库维护者审阅，不建议无审查地自动合并。人工审阅应尤其关注哲学原义的跨传统类比、反身性模型的适用条件和金融史轶事处理。

## Reproducible canonical validation (on a networked checkout)

```bash
python3 -B /path/to/oh-my-skill/skills/llm-wiki-maintainer/scripts/wiki_lint.py --vault . --profile wiki --fail-on P1
python3 -B /path/to/oh-my-skill/skills/llm-wiki-maintainer/scripts/wiki_lint.py --vault . --profile sources
```

若上述命令报告新的问题，以实际运行结果为准；使用新 PR 修复，切勿把本次静态检查当作 CI 的替代品。
