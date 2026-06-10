# Title Framework (标题框架)

How the **3 candidate titles** per invocation are generated. The workflow's system is **12 named title styles × 6 sentence structures × a 4-dimension keyword matrix**, cross-referenced by account type and content type.

> Sourced from 小红书工作流 V2 Sections K / H / G / L.

## Output contract: 3 候选组合

> 3 版标题 × 1 条封面文字 ＝ 3 个候选组合，发群里让同事盲选。

Each invocation produces **3 组合**. Each 组合:

```
标题   —— 15-20 字，偏正式·客观，带搜索关键词（给正文/搜索）
主文字 —— ≤10 字，偏情绪·网感（封面最大的字）
副文字 —— ≤12 字，一个具体回报点/关键词
```

**标题 15-20 字是硬指标** — 小红书官方"优质笔记"奖励门槛 (Section 02 / C). Below 15 characters misses the algorithmic weighting.

The three must be **genuinely different angles** — not three rewordings of one idea. That's the whole point of 盲选. Vary the title style across the three.

## The 3-layer stacking order (K → H → G)

标题的正解是三层叠加，**按这个顺序**走：

1. **先定风格 (K · 12种语气调性)** — 这一篇用什么口气说。
2. **再选句式 (H · 6类结构)** — 倒进哪种语法模子。
3. **最后填关键词 (G · 4维矩阵)** — 把搜索词嵌进去。

Outer wrapper: **L 权重路由** — 先看账号类型，再看内容类型 — 决定 K 里优先挑哪 3-4 种风格。

## 素材蒸馏（写标题前的内容侧准备）

Compress source material into this matrix before going to K/H/G:

| 维度 | 问什么 | 例（Vapor SL 长测） |
| --- | --- | --- |
| 主体 (who/what) | 产品/人/场景的核心名词 | Vapor SL / 电助力 |
| 动作 (verb) | 核心动词 | 长测 / 通勤 / 爬坡 |
| 数字 (number) | 一个具体可信的数 | 3千公里 / 一年 / 18% 坡 |
| 情绪 (feeling) | 真实的那一下感受 | 没进过店 / 不喘了 / 戒断地铁 |

Each title must bite ≥2 dimensions. Cover text must bite 情绪 + (主体 or 数字).

## K · 12 种标题风格（语气调性）

| # | 风格 | 特征 | 适合场景 |
| --- | --- | --- | --- |
| 1 | 犀利吐槽风 | 反问/质疑，自带情绪 | 质疑现象、表达不满 |
| 2 | 情绪定性风 | 直接定调子 | 明确态度、不绕弯 |
| 3 | 悬念代价风 | 留半句话，钩子在后面 | 埋悬念让人点开 |
| 4 | 沙雕吐槽风 | 夸张 + 自嘲 + 有梗 | 降距离、让人笑 |
| 5 | 冷知识揭秘风 | 像在分享内幕/反常识 | 专业内容、揭秘话题 |
| 6 | 强反转风 | 前后反差强烈 | 内容本身有意外感 |
| 7 | 热点黑话风 | 蹭流行词/圈内话 | 贴热点、找圈内人 |
| 8 | 趣味夸张风 | 戏剧化但不油 | 娱乐性、氛围感强 |
| 9 | 闺蜜咆哮风 | 高浓度情绪 + 口语 | 强情绪分享 |
| 10 | 对话提问风 | 向读者发问 | 要互动率/评论 |
| 11 | 数字焦虑风 | 用具体数字制造紧迫感 | 限时/限量信息 |
| 12 | 独体句风 | 短句并列、节奏感强 | 信息简单、克制风格 |

Every style must pass `cover-text.md`'s 平视感 and 违禁词 checks. A lecturing tone or absolute claim will kill an otherwise good angle.

## H · 6 类标题句式

| 句式 | 特点 |
| --- | --- |
| 一句话 + 冒号 | 直接铺垫，下文跟答案 |
| 一句话 + 省略号 | 留白，引人想继续看 |
| 一句话 + 句号/感叹号 | 直陈观点/情绪 |
| 如果你想……一定要记住…… | 条件型，针对特定人群 |
| 第 N 期/第 N 天 系列 | 系列化连载，建立追读 |
| 字数极少（7 字内） | 图不出彩时用，标题字尽量少 |

K selects *what angle*; H selects *grammar mold*. Same style (K) can pour into multiple sentence structures (H).

## G · 标题 4 维关键词矩阵

写标题前先填这 4 列：

| 维度 | 内容 |
| --- | --- |
| 通用句式模板 | 套进去就能用的框架 |
| 吸睛核心词 | 这个垂类的爆款关键词 |
| 放标题开头的词 | 【建议收藏】【小白避坑】等 |
| 放标题结尾的词 | ……让人想看下去 |

## L · 权重路由

### L.1 按账号类型的基础调性

| 账号类型 | 基础调性 | 风格倾向 |
| --- | --- | --- |
| 品牌主账号 | 克制 / editorial / 长期主义 | 偏 独体句、悬念代价、冷知识揭秘、情绪定性 |
| 创始人个人号 | 松弛 / 强人格感 / 可吐槽 | 全开放，但避免过度营销感 |
| 车队号/职人号 | 真实 / 实操 / 圈内感 | 偏 数字焦虑、对话提问、冷知识揭秘 |
| 活动账号 | 当下感 / 转化感 / 时效性 | 偏 数字焦虑、热点黑话、悬念代价 |

### L.2 按内容类型的风格权重

| 内容类型 | 优先用 ★★★ | 也能用 ★★ | 默认封面范式 |
| --- | --- | --- | --- |
| 新品发布 | 悬念代价、冷知识揭秘、强反转 | 情绪定性、独体句 | 极简摄影 / 经典图文 / 大字报 |
| 产品测评/长测 | 冷知识揭秘、对话提问、情绪定性 | 强反转、犀利吐槽 | 极简摄影 / 经典图文 |
| 赛事 Recap/成绩 | 数字焦虑、强反转、情绪定性 | 独体句、闺蜜咆哮（轻度） | 经典图文 / 多图拼贴 |
| 教程/科普 | 冷知识揭秘、对话提问、独体句 | 情绪定性、悬念代价 | 大字报 / 推荐集锦 |
| Vlog/出行日记 | 强反转、数字焦虑、对话提问 | 沙雕吐槽、趣味夸张、热点黑话 | 多图拼贴 / 经典图文 |
| 车主/用户故事 | 情绪定性、独体句、强反转 | 闺蜜咆哮、沙雕吐槽 | 人像抠图 / 经典图文 |
| 品牌价值观/创始人输出 | 独体句、情绪定性、冷知识揭秘 | 强反转、悬念代价 | 大字报 / 留白排版 |
| 活动招募/带货预热 | 数字焦虑、对话提问、悬念代价 | 情绪定性、热点黑话 | 大字报 / 经典图文 |

### L.3 使用顺序

先定账号类型（基础值）→ 再定内容类型（决定优先选哪 3-4 种风格）→ 在"优先用"里挑 1-2 种试跑，"也能用"作为备选。表是脑暴卡住时翻的，熟了就成肌肉记忆。**默认账号 = 品牌主账号 (Cosmosworks)**，除非用户另说。

## Do / Don't

- **Do** use L.2 to pick 3-4 styles, then assign a **different** style to each of the 3 候选 — real 盲选 requires real variety.
- **Do** keep titles formal/objective; let 封面文字 carry the emotion. Guard the 15-20字 hard limit.
- **Don't** write a title that, shortened, *is* the cover text. See 封面≠标题 rule in `cover-text.md`.
- **Don't** default to the same style for all 3 候选.
