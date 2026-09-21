# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

A multi-skill knowledge repository for Chinese metaphysics and divination, structured for the [Agent Skills open standard](https://agentskills.io). Each skill lives under `skills/<name>/` and is self-contained.

There is no top-level build system. Individual skills may include Python scripts (run directly with `python3`). The only "output" is each `SKILL.md` being loaded by a compatible agent.

## Skills inventory

| Skill directory | Name | Description |
|-----------------|------|-------------|
| `skills/fengshui-master/` | `fengshui-master` | 传统堪舆风水顾问 — 三元玄空飞星、八宅明镜、形势峦头、择日、八字配合风水 |
| `skills/bazi/` | `bazi` | 四柱八字命理分析 — script-driven排盘 (`pai_pan.py`), interactive info collection, classical-text analysis |
| `skills/ziwei-doushu/` | `ziwei-doushu` | 紫微斗数专业排盘与解盘 — 十二宫、四化、大限流年 |
| `skills/qimen-dunjia/` | `qimen-dunjia` | 奇门遁甲排盘与择吉 — script-driven (`qimen_cli.py`), requires Python 3.11+, lunar_python, tzdata |
| `skills/yinyuan/` | `yinyuan` | 姻缘测算 — 八字合婚、紫微夫妻宫、生肖配对、姻缘签诗、桃花运势 |
| `skills/tarot/` | `tarot` | 塔罗占卜 — scripted random draws, upright/reversed, agency-first advice |

## Skill structure (per skill)

Each skill directory follows this layout:

```
skills/<name>/
  SKILL.md          # Authoritative: YAML frontmatter + persona + workflow
  README.md         # Human-readable overview (optional)
  references/       # Lookup tables only — no prose, no persona voice
  examples/         # Worked dialogue examples (fengshui-master only)
  scripts/          # Python scripts (排盘/random draws: bazi, qimen-dunjia, tarot; verification helper: ziwei-doushu)
```

## Agent Skills standard

Each `SKILL.md` must have valid YAML frontmatter with `name`, `description` (trigger-word list), and optionally `metadata.version`/`metadata.author`. The `npx skills` installer reads this frontmatter verbatim — whitespace and quoting matter.

Trigger phrases in `description` are the discovery surface; keep them comprehensive. They are matched by agent runtimes to decide whether to load the skill.

## Authoring conventions

- Reference files are **lookup tables only** — no prose, no persona voice. Detailed methodology stays in `SKILL.md`.
- Skills whose 排盘 is script-driven (bazi, qimen-dunjia) and tarot: the script stdout is authoritative for all fixed calculations. AI must not override script results. (ziwei-doushu 排盘 is table-driven via `references/calculation.md`; its `scripts/ziwei_verify.py` is a verification helper only.)
- **fengshui-master**: Knowledge framework is structured as 五大模块 (Modules 1–5): 形势峦头 → 玄空飞星 → 八宅明镜 → 煞气化解 → 择日学. Execution flows live in **第三章**. Examples use dialogue format: **用户**: / **堪舆子**: with structured headers (`【宅基信息】`, `【飞星盘】`, etc.).
- **bazi**: `scripts/pai_pan.py` must run before analysis.禁止口算. See skill for full CLI reference.
- **qimen-dunjia**: `scripts/qimen_cli.py` handles all排盘. Requires `lunar_python` and `tzdata`.

## Current epoch

九运 (2024–2043) is the current period. Any content that mentions 当前所在元运 or 当旺星 must reflect this.
