# AI Skill； 传统风水顾问

> 「峦头为体，理气为用；峦头差，理气无用；理气差，峦头吉地亦减分。」

一个遵循 [Agent Skills 开放标准](https://agentskills.io) 的 Skill，以江南三元世家传人的视角，运用玄空飞星、八宅明镜、择日学等传统方法，帮你分析居住环境、择吉日、化煞气。

只是一份 `SKILL.md` + 参考资料，可在 Claude Code、Codex CLI 等 30+ 兼容智能体中直接使用。

**不是玄学算命，不卖摆件，不恐吓煞气。** 基于《沈氏玄空学》《地理五诀》《协纪辨方书》等传统典籍的系统性方法。

---

## 能做什么

- 据房屋朝向与入住时间**排玄空飞星盘**，判旺位凶位
- 据居住者命卦**配八宅游年**，给四吉四凶方布局
- 结合年月神煞**筛选入宅/开业/动土吉日**
- 识别路冲、天斩、壁刀等**外煞**并给化解
- **解读术语与经典原文**，答理论问题

---

## 安装

遵循 Agent Skills 标准，用 [`npx skills`](https://github.com/vercel-labs/skills) 一键安装，或手动 clone：

```bash
# npx skills（推荐，自动检测智能体；--agent 可指定 claude-code / codex / cursor 等；-g 装到全局）
npx skills add techfrenza/fengshui.skill

# 手动 clone（目录名不强制，仅需含 SKILL.md）
git clone https://github.com/techfrenza/fengshui-master ~/.claude/skills/fengshui-master   # Claude Code
git clone https://github.com/techfrenza/fengshui-master ~/.codex/skills/fengshui-master    # Codex CLI
```

---

## 使用方法

安装后用自然语言描述需求即可触发，无需特定指令：

```
我家坐北朝南，2018年入住，最近财运不好，帮我看看风水格局
打算今年6月搬新家，帮我选几个入宅吉日，我是1988年男，门朝东
我家大门正对一条笔直的道路，这算路冲吗？怎么化解？
八宅游年是什么？怎么算命卦？
```

---

## 知识体系

| 流派 | 核心方法 | 用途 |
|------|---------|------|
| **三元玄空飞星** | 九宫飞布、元运、山星向星 | 阳宅旺衰、财运人丁 |
| **八宅明镜** | 东西四宅命、游年变卦 | 卧室书房财位布局 |
| **形势峦头** | 龙穴砂水向、藏风聚气 | 外部环境与煞气 |
| **择日学** | 建除十二神、月破三煞 | 入宅开业动土选日 |
| **八字配风水** | 日主用神、五行方位 | 个人旺方与颜色 |

---

## 文件结构

```
SKILL.md                  # 主 Skill：人物设定 + 知识框架 + 执行流程
references/feixing.md     # 玄空飞星速查（飞布规则、旺衰、流年星、伏吟反吟合十）
references/wuxing-ganzhi.md # 五行干支速查（干支、生克、命卦算法）
references/zeri.md        # 择日神煞速查（建除十二神、月破、三煞、受死日）
examples/yangzhai.md      # 阳宅分析对话示例（含飞星盘）
examples/zeri-example.md  # 择日对话示例（含命卦配合）
```

---

**参考典籍**：《宅经》《葬书》《天玉经》《青囊序》《地理五诀》《玄空秘旨》《沈氏玄空学》《协纪辨方书》。

---

## 免责声明

本项目基于传统堪舆学理论，仅供学习、参考与文化探讨。风水为辅，人为为主。重大决策请结合实际综合考量，勿作唯一依据。
