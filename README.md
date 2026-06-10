# cosmos-rednote-skill · 小红书标题 + 封面文字生成器

![GitHub stars](https://img.shields.io/github/stars/stanley50z/cosmos-rednote-skill?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)
![Skill](https://img.shields.io/badge/Skill-Agent-111111?style=flat-square)
![Claude Code](https://img.shields.io/badge/Claude%20Code-Supported-6B5B95?style=flat-square)

A Claude Code skill that generates Rednote/Xiaohongshu **post titles (标题)** and **cover image text (主文字 + 副文字)** from any input — article, script, product notes, subtitles, or photos.

Grounded in the **Cosmosworks 小红书工作流 V2, Step 02「标题+封面文字」**.

---

## What it produces

**3 candidate combinations (候选组合)** per run — send them to your group chat for blind selection (盲选). Each combination:

```
标题   —— 15-20 字，偏正式·客观·带搜索关键词（不上封面）
主文字 —— ≤10 字，偏情绪·网感（封面最大的字）
副文字 —— ≤12 字，一个具体回报点 / 搜索关键词
```

Core rule: **封面 ＝ 标题，但不重复** — same fact, different sentence, different info point.

```
标题：骑了一年 Vapor SL：3千公里真实长测
主文字：谁懂啊
副文字：3千公里没进过店
```

---

## Install

The skill lives in one place on disk; both agent harnesses point at it via a junction/symlink.

### Step 1 — clone the repo

**Mac / Linux:**
```bash
git clone https://github.com/stanley50z/cosmos-rednote-skill.git ~/skills/cosmos-rednote-skill
```

**Windows (PowerShell):**
```powershell
git clone https://github.com/stanley50z/cosmos-rednote-skill.git "$env:USERPROFILE\skills\cosmos-rednote-skill"
```

> You can clone anywhere — just replace `~/skills/cosmos-rednote-skill` with your preferred path in the link commands below.

### Step 2 — link into Claude Code (`~/.claude/skills/`)

**Mac / Linux:**
```bash
mkdir -p ~/.claude/skills
ln -s ~/skills/cosmos-rednote-skill ~/.claude/skills/cosmos-rednote-skill
```

**Windows (PowerShell — no admin needed, uses directory junction):**
```powershell
cmd /c mklink /J "$env:USERPROFILE\.claude\skills\cosmos-rednote-skill" "$env:USERPROFILE\skills\cosmos-rednote-skill"
```

### Step 3 — link into the broader agent harness (`~/.agents/skills/`)

**Mac / Linux:**
```bash
mkdir -p ~/.agents/skills
ln -s ~/skills/cosmos-rednote-skill ~/.agents/skills/cosmos-rednote-skill
```

**Windows (PowerShell):**
```powershell
cmd /c mklink /J "$env:USERPROFILE\.agents\skills\cosmos-rednote-skill" "$env:USERPROFILE\skills\cosmos-rednote-skill"
```

### Option — paste this into any agent with shell access

```text
Help me install cosmos-rednote-skill. Please:
1. git clone https://github.com/stanley50z/cosmos-rednote-skill.git ~/skills/cosmos-rednote-skill
2. mkdir -p ~/.claude/skills && ln -s ~/skills/cosmos-rednote-skill ~/.claude/skills/cosmos-rednote-skill
3. mkdir -p ~/.agents/skills && ln -s ~/skills/cosmos-rednote-skill ~/.agents/skills/cosmos-rednote-skill
4. Verify both links resolve to SKILL.md and references/ and tell me when done
```

### Update

```bash
cd ~/skills/cosmos-rednote-skill && git pull
# Both harness links pick up the change automatically — no re-linking needed
```

---

## Usage

After installing, just describe your content to Claude Code:

```text
基于这篇长测给我 3 个候选组合：标题 + 封面主文字 + 副文字。
```

```text
这篇通勤测评，给我 3 版标题 + 封面文字，发群里盲选。
```

```text
我有这个产品发布稿，帮我出封面文字，要情绪感强的。
```

```text
给我 3 组小红书封面文案，骑行通勤主题。
```

```text
新品发布笔记，标题 + 封面主副文字各 3 个方向。
```

The skill is auto-triggered by keywords: 小红书封面文字, 爆款标题, 封面文案, 候选组合, Rednote cover text, 主文字, 副文字.

---

## What's inside

```
cosmos-rednote-skill/
├── SKILL.md                    ← Main skill instruction (Claude reads this)
├── README.md                   ← This file
├── references/
│   ├── cover-text.md           ← 封面文字 rules: 主+副 structure, char limits,
│   │                              SEO hook, 平视感 tone, 9 cover paradigms,
│   │                              emoji/违禁词 checklist
│   ├── title-framework.md      ← 12 styles × 6 structures × 4D keyword matrix,
│   │                              L weight routing by account/content type
│   └── brand.md                ← Cosmosworks voice, product line, visual anchor
└── LICENSE
```

---

## Key constraints enforced

| Rule | Detail |
|------|--------|
| 标题 15-20 字 | 小红书官方"优质笔记"奖励门槛 |
| 主文字 ≤10 字 | Largest text on cover — one hook |
| 副文字 ≤12 字 | One specific payoff or searchable keyword |
| 封面 ≠ 标题 | Same fact, different sentence, different info point |
| 平视感 | Peer voice — never "我来教你" |
| 0 emoji (max 1) | Emoji is 过气 on Rednote |
| No 违禁词 | 最/第一/唯一/国家级/顶级/首个 → replace with concrete numbers |
| 3 genuinely different angles | Real 盲选 requires real variety |

---

## How it fits the full workflow

This skill covers **Step 02** of the 5-step Rednote workflow:

```
01 需求确认  →  02 标题+封面文字  →  03 图片制作  →  04 正文撰写  →  05 标签发布
                      ↑
                 this skill
```

After generating the 3 候选组合, the skill also outputs:
- Downstream handoff to **03**: reminder for ≥5 images, 钩子→展开→细节→收尾 rhythm
- Downstream handoff to **04**: draft opening 2 lines for the post body (rehooks the cover text)
- Downstream handoff to **05**: 6-dimension keyword seeds (人群/场景/产品/功效/类目/竞品) for tags

---

## License

MIT © 2026 stanley50z
