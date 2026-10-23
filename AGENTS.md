# Wei-Book Agent Guide

This repository is maintained as a persistent LLM Wiki. The canonical workflow is **`XiaoWeiKIN/oh-my-skill/skills/llm-wiki-maintainer/SKILL.md`**, together with its referenced ingest, schema, navigation, and lint rules. Read the current canonical skill before maintaining knowledge. This repository does **not** vend a copy of the skill.

## Structure and write boundaries

- `_sources/`: provenance and immutable conversation/article/paper evidence. **Never silently rewrite captured source content.** Only change ingestion lifecycle metadata through the ingest workflow.
- `_wiki/`: synthesized, reusable topic, concept, comparison and question pages, each with `type`, `updated`, provenance and durable inbound links.
- `_meta/`: ingest manifests, migration backlog, audit log and lint reports.
- `Index.md` and `_wiki/Home.md`: durable navigation entry points.
- `game-theory/`, `systems-thinking/`: existing **legacy** notes. Preserve them and their GitHub links until explicitly reviewed and compiled. Do not rename or delete them just to satisfy the new structure.
- `presentations/` and `templates/`: artifacts/templates; do not ingest them as knowledge pages by default.

## Before writing knowledge

1. Read `Index.md`, `_wiki/Home.md`, the nearest existing concept page, and relevant source material.
2. Identify 3–7 durable claims, uncertainties, contradictions and impact targets.
3. Prefer updating an existing page; add a new page only for a stable reusable concept or question.
4. For ingestion, create or preserve the source under `_sources/inbox/YYYY-MM/`; run canonical `wiki_ingest.py plan` and record the source hash, impact manifest and targets before editing.
5. Update all affected pages with local provenance and inbound navigation. Run canonical `wiki_ingest.py process` (dry run first if needed) and scoped `wiki_lint.py` with profiles `wiki` and `sources`.
6. Append meaningful changes to `_meta/log.md`. Keep human conclusions distinct from source claims and inferred hypotheses.
7. If the runtime cannot execute the canonical scripts, document the limitation and the checks actually performed. **Never claim the scripts ran when they did not.**
8. Require human review of disputed or sensitive claims, destructive moves, or any ingest affecting more than three durable Wiki pages.

## Link compatibility

- Use unambiguous Obsidian wiki links, such as `[[_wiki/SystemsThinking/胜利后的战略转型]]`, for knowledge graph provenance and inbound navigation.
- Where Github browsing matters, include a regular relative Markdown link as well.
- Do not introduce dangling links or citations to source material that has not been captured.

## Review priorities

Use `_meta/migration-plan.md` for subsequent compilation of older notes. Each batch should preserve its original input and avoid duplicated, diverging conclusions. A large-scale move belongs in a separate reviewable PR.
