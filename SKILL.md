---
name: cosmos-rednote-skill
description: Generate Rednote/Xiaohongshu post titles (标题) and cover image text (主文字 + 副文字) from any input — article, script, product notes, subtitles, or photos. Grounded in the Cosmosworks e-bike 小红书工作流 V2 Step 02. Use when the user asks for 小红书封面文字, 爆款标题, Rednote/Xiaohongshu cover text or titles, 封面文案, 候选组合, or any variation thereof.
---

# Cosmos Rednote Skill · 标题 + 封面文字

Generate the **post title** and the **text that goes on the cover image** for a Rednote/Xiaohongshu post. This is **Step 02「标题+封面文字」** of the 小红书工作流 V2 (5 stages: 01 需求确认 → **02 标题+封面文字** → 03 图片制作 → 04 正文撰写 → 05 标签发布).

Default brand voice: **Cosmosworks** (editorial e-bike / electric-assist). See `references/brand.md`.

## What To Produce

Per invocation: **5 候选组合**, each with **5 variants**. Each 组合 is one distinct angle on the same content. Each variant within a 组合 is a complete set:

```
标题   —— 15-20 字，偏正式·客观·带搜索关键词（不上封面，给正文/搜索）
主文字 —— ≤10 字，偏情绪·网感·口语（封面最大的字）
副文字 —— ≤12 字，一个具体回报点 / 搜索关键词（封面次要的字）
```

5 组合角度必须真正不同。同一组合内的 5 个 variant 走同一角度、不同措辞——让盲选有真实宽度。

## Core Rule

> **封面 ＝ 标题，但不重复** —— 同一件事，透露不同信息点。

标题陈述事实（formal, objective, searchable）。封面文字对这件事做出反应（emotional, 网感, 口语），回答"为什么我要点开"。封面文字如果只是标题缩短版，就是失败。

**Canonical example (from the workflow doc):**

```
标题：骑了一年 Vapor SL：3千公里真实长测
封面主文字：谁懂啊
封面副文字：3千公里没进过店
```

## Required References

- `references/cover-text.md` — **the heart of the skill.** 封面≠标题, 主+副 structure, char limits (≤10/≤12), SEO keyword = hook, 平视感 tone, emoji is 过气, 违禁词 list, 真实感＞精美感, 货架感 shelf test, 9 cover paradigms, self-check checklist.
- `references/title-framework.md` — 3-候选 contract, **标题 15-20字 门槛**, K (12 风格) → H (6 句式) → G (4维矩阵) stacking order, L 权重路由 (账号类型 × 内容类型).
- `references/brand.md` — Cosmosworks voice + four cosmos themes (dark / sport / clean / green).

## Workflow

### 1. Intake

Size the intake to the job:

- **日更（30 秒答 3 题）**：给谁看 / 要什么结果（种草·加微信·活动报名·品牌曝光，选**一个**主目标）/ 必出现什么（产品名·活动信息·关键数据，挑 1-2 项）。3 题答不齐就别动笔。
- **重点项目（8 项完整任务卡）**：给谁看 · 要什么结果（一个主目标）· 在哪个节奏里（单篇/系列、关联节点、预热/引爆/收尾）· **产品事实底料**（哪款 Vapor SL/Oi!/Nomad/Model R/Vapor AL、哪些参数/价格可公开、哪些不能透露）· 活动事实底料 · 资源清单 · **红线**（友商能否点名、供应链内部信息、违禁词）· 参考内容（要链接）。

If enough context is present, proceed with reasonable assumptions and note what you assumed. If the content involves live product specs, prices, or performance claims, flag rather than state unverified numbers.

Determine from the input:
- **Content type** — 新品发布 / 长测 / 赛事 Recap / 教程 / Vlog / 车主故事 / 观点 … routes 风格 via `title-framework.md` L.2.
- **Account type** — default 品牌主账号 (Cosmosworks) unless user says otherwise. Feeds L.1.
- Whether the user has a **cover photo** (affects which 范式 to recommend).

### 2. Distill The Source

Compress any input into the **素材蒸馏 matrix**:

| 维度 | 问什么 |
| --- | --- |
| 主体 (who/what) | 产品/人/场景的核心名词 |
| 动作 (verb) | 核心动词 |
| 数字 (number) | 一个具体可信的数字 |
| 情绪 (feeling) | 真实的那一下感受 |

Pull the one real number and the one real feeling — those anchor both the title and the cover text. Each 标题 must bite ≥2 dimensions; each 封面 must bite 情绪 + (主体 or 数字).

### 3. Write 5 候选组合 × 5 Variants Each

**Generate freely first.** Write all 5 候选角度 from instinct based on the distilled source material — follow the emotional angle that feels truest, not a framework slot. The goal is 5 genuinely different perspectives on the same fact.

After settling the 5 angles, **cross-reference** `title-framework.md` K styles and L routing as a *check*, not a template: verify the 5 are actually different, and use the K list to spot an angle you missed or to sharpen tone. You are not required to match a K style — only to ensure real variety.

For each 组合, write **5 variants** — same underlying angle, different phrasing, different level of bluntness or warmth. Variants within a 组合 should feel like 5 people saying the same thing in their own voice, not 5 copies of the same sentence with one word swapped.

For each variant:

1. **标题** — formal/objective, **15-20 字** (优质笔记门槛), ≥2 蒸馏维度, 带搜索关键词. H sentence structures and G keyword matrix in `title-framework.md` are available as tools, not mandatory molds.
2. **主文字** — ≤10 字, emotional hook. Different sentence from the title, same fact. Largest text on cover.
3. **副文字** — ≤12 字, one specific payoff or searchable detail. Smaller text, near 主文字. Size contrast between 主 and 副 is what makes it read as a poster not a caption.
4. Fold the searchable keyword into the hook — don't bolt it on separately.

Then run every line through the **self-check** in `references/cover-text.md`:
- 可逆性测试: 遮一边都想点, 两条是补充非复读
- 封面 ≠ 标题
- Char limits: 标题 15-20字 / 主 ≤10字 / 副 ≤12字
- Keyword present in cover text
- Peer tone (no 我来教你)
- ≤1 emoji (prefer 0)
- No 违禁词 (最/第一/唯一/…)

### 4. Deliver + Downstream Handoff

Show the user:

1. **5 候选组合**, each labeled 组合 A–E, each with 5 variants labeled v1–v5. Format each 组合 as a table:

   | | 标题 | 主文字 | 副文字 |
   |---|---|---|---|
   | v1 | … | … | … |
   | v2 | … | … | … |
   | v3 | … | … | … |
   | v4 | … | … | … |
   | v5 | … | … | … |

2. One line of rationale per 组合: what angle it takes and what makes it distinct from the others.
3. Brief instruction: "发群里让同事盲选，遮住一边仍然想点就合格。"
4. **下游 handoff（简短）：**
   - → **04 正文**：开头 2 行复述封面钩子（复用主文字）再落到具体场景。Draft these 2 lines based on the winning 组合.
   - → **05 标签**：输出一组 6 维关键词种子（人群/场景/产品/功效/类目/竞品），产品/场景词与封面里的搜索关键词同词，供 tag 直接抄。提醒用精准话题，避大词（如不用 #骑行，用 #城市通勤电助力 / #公路车新手）。

## Non-Negotiables

- **封面 ≠ 标题.** Same fact, different sentence, different info point. 合格判据：遮住封面只看标题、遮住标题只看封面，**两边都想点**；两条是"补充"不是"复读"。
- **标题 15-20 字** (小红书官方优质笔记奖励门槛). 主文字 ≤10 字, 副文字 ≤12 字. Cut, don't shrink.
- One searchable keyword inside the cover text; make it the same word as the emotional hook.
- **平视感**: peer voice, never "我来教你".
- **0 emoji** preferred, max 1.
- No **违禁词** — 最 / 第一 / 唯一 / 国家级 / 顶级 / 首个 and any absolute or unverified claim. Replace superlatives with concrete numbers.
- The 5 候选 must be genuinely different angles for real 盲选. Variants within a 组合 vary phrasing, not angle.
- If content involves live product specs or claims, verify or flag — don't state unverified numbers (also a 红线/违禁词 risk).
