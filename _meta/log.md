# Wei-Book Wiki 更新日志

## [2026-10-23] ingest | 秦史讨论主题编译

- Source: `_sources/conversations/2026-10/qin-unification-conversation.md`
- Source plan: `_meta/ingest-manifests/qin-unification-2026-10.json`
- Source integrity (pre-compilation snapshot): `sha256:44b439789f43767b86af9a71923a1918eed88c97c8f299422e46d0e3dc8fb949`
- Targets: `_wiki/History/Questions/秦统一与秦朝速亡.md`, `_wiki/SystemsThinking/胜利后的战略转型.md`
- Navigation: `Index.md`, `_wiki/Home.md`, `README.md`
- Retained legacy: `systems-thinking/qin-unification-strategy-transition.md` (unmodified source-style precursor)
- Summary: Compiled two linked and sourced durable knowledge pages; preserved a partial curated conversation excerpt; captured five durable claims and uncertainty boundaries.
- Execution note: GitHub connector writes and readback were used. The canonical Python `wiki_ingest.py plan/process` and `wiki_lint.py` scripts were **not executed** in this environment. Do not treat this entry as a passing script validation.
- Review: PR review required before merge. Other legacy documents remain in the migration backlog; no destructive changes were performed.

## [2026-10-23] legacy compilation | 蜈蚣博弈收益矩阵纠错

- Legacy source: `game-theory/centipede-game.md` (preserved unchanged)
- Target: `_wiki/GameTheory/蜈蚣博弈.md`
- Main correction: legacy node 4 gives B 5 for Take and 6 for Pass, contradicting the claimed Take decision. The compiled page supplies a self-consistent example and explicitly notes that different payoff matrices change the equilibrium.
- References: Rosenthal (1981); McKelvey & Palfrey (1992). Specific experimental termination percentages remain unverified and are not carried into the durable page.
- Navigation: `Index.md`, `_wiki/Home.md`, `README.md`
- Validation: Connector readback and targeted link/model consistency checks; canonical Python scripts not run.
- Follow-up: Further migration should verify legacy claims against primary literature and retain the original source path.

## [2026-10-23] legacy compilation | 格罗斯曼—斯蒂格利茨悖论

- Legacy source: `game-theory/grossman-stiglitz-paradox.md` (preserved unchanged).
- Durable target: `_wiki/GameTheory/格罗斯曼-斯蒂格利茨悖论.md`.
- Correction: The information-acquisition-cost paradox does **not** entail that successful trading destroys the market, that all counterparties disappear, or that capital markets must be replaced by a single allocator.
- References: Grossman and Stiglitz (1980); Fama (1970). The original model's detailed comparative statics remain marked for further verification.
- Navigation: `Index.md`, `_wiki/Home.md`, `README.md`.
- Validation: connector readback and link/provenance checks; canonical Python ingest/lint scripts not run.
