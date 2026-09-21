# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

A pure knowledge/skill repository — no code, no build system, no tests. It is a single `SKILL.md` that defines the **堪舆子** persona for the [Agent Skills open standard](https://agentskills.io), plus reference tables and worked examples.

There is nothing to build, lint, or test. The only "output" is the skill itself being loaded by a compatible agent.

## File roles

| File | Role |
|------|------|
| `SKILL.md` | The skill itself: YAML frontmatter (name/description/metadata) + persona definition + full knowledge framework + execution workflow. This is the authoritative source. |
| `references/feixing.md` | Lookup tables for 玄空飞星: 九宫飞泊 rules, per-运 star tables, 阴阳山向, annual 流年星 table. |
| `references/wuxing-ganzhi.md` | Five-elements / 干支 reference: 天干地支 attributes, 生克 rules, 命卦 algorithm. |
| `references/zeri.md` | 择日 reference: 建除十二神, 月破, 三煞, 受死日 tables. |
| `examples/yangzhai.md` | Full worked example: 阳宅 analysis dialogue with 飞星盘 layout. |
| `examples/zeri-example.md` | Full worked example: 择日 dialogue with 命卦 integration. |

## Agent Skills standard

`SKILL.md` must have valid YAML frontmatter with `name`, `description` (trigger-word list), and `metadata.version`/`metadata.author`. The `npx skills` installer reads this frontmatter verbatim — whitespace and quoting matter.

Trigger phrases in the `description` field are the discovery surface; keep them comprehensive. They are matched by agent runtimes to decide whether to load this skill.

## Authoring conventions

- The knowledge framework in `SKILL.md` is structured as五大模块 (Modules 1–5): 形势峦头 → 玄空飞星 → 八宅明镜 → 煞气化解 → 择日学. Additions should fit into this hierarchy.
- Execution flows live in **第三章** (Phase 0, 1A–1D). New question types get their own Phase entry there.
- Reference files are **lookup tables only** — no prose, no persona voice. Detailed methodology stays in `SKILL.md`.
- Examples use a fixed dialogue format: scenario block → **用户**: → **堪舆子**: with structured output headers (`【宅基信息】`, `【飞星盘】`, etc.). New examples should follow this pattern.

## Current epoch

九运 (2024–2043) is the current period. Any content that mentions 当前所在元运 or 当旺星 must reflect this.
