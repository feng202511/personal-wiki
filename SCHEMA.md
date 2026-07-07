# Wiki Schema

## 领域
个人成长与读书笔记 — 涵盖书籍精读、概念提炼、习惯养成、思维模型、人物传记、课程笔记等

## 规范
- 文件名：小写英文 + 连字符（如 tomic-habits-notes.md），中文主题用拼音或英文
- 每页以 YAML frontmatter 开头（见模板）
- 使用 [[wikilinks]] 连接相关页面（每页至少 2 个出链）
- 更新页面时更新 updated 日期
- 新建页面必须加入 index.md 对应章节
- 每次操作必须追加到 log.md
- **来源标记：** 综合 3 个以上来源的页面，在段落末尾用 ^[raw/articles/来源文件.md] 标记具体出处

## Frontmatter 模板

`yaml
---
title: 原子习惯
created: 2026-07-07
updated: 2026-07-07
type: entity | concept | comparison | query | summary
tags: [来自下面的分类法]
sources: [raw/articles/atomic-habits.md]
rating: ⭐⭐⭐⭐⭐        # 对书籍/课程的个人评分
status: reading | finished | archived  # 阅读状态
confidence: high | medium | low
---
`

### raw/ 素材的 Frontmatter

`yaml
---
source_url: https://example.com/article
ingested: 2026-07-07
sha256: <正文的 SHA256 哈希>
---
`

## 标签分类法

- **书籍：** book, reading, summary, review
- **知识领域：** psychology, productivity, philosophy, science, biography, business, communication, health, finance, creativity
- **能力：** skill, habit, thinking-model, decision-making, learning, writing, speaking
- **方法：** methodology, framework, system, tool
- **状态：** reading, finished, archived, wishlist
- **元标签：** comparison, timeline, quote, action-plan

规则：每页的 tags 必须来自此分类法。需要新标签时先加入此表再用。

## 页面创建阈值

- **创建独立页面：** 当一本书、一个概念、一个人物在 2 个以上来源中出现，或是一个来源的核心主题
- **补充已有页面：** 新来源提到已有实体/概念时，更新现有页面而非新建
- **不创建页面：** 轻微提及、边角料、与本领域无关的内容
- **拆分页面：** 超过 200 行时拆分为子主题，用 [[wikilinks]] 连接
- **归档页面：** 内容完全被取代时移到 _archive/，从 index 移除

## 各类页面结构

### 📖 书籍笔记（entities/）
- 书籍基础信息（作者、出版年份、页数）
- 一句话总结
- 核心论点 / 框架
- 金句摘录（用 >  引用块）
- 个人感悟与批判
- 行动清单（读完后做了什么改变）
- 与其他书籍的 [[关联]]

### 🧠 概念卡片（concepts/）
- 定义
- 来源
- 相关概念（[[wikilinks]]）
- 个人理解 / 例子
- 反直觉之处

### ↔️ 对比分析（comparisons/）
- 对比什么、为什么
- 对比维度（表格形式）
- 综合判断
- 来源

## 更新策略

新旧信息冲突时：
1. 检查日期 — 新来源一般优于旧来源
2. 如果确实矛盾，两边都保留并标注日期和来源
3. 在 frontmatter 标注 contradictions: [page-name]
4. 在 Lint 报告中标记给用户审查

## Obsidian 配置建议

- **附件文件夹：** aw/assets/
- **启用 Wikilinks**
- **推荐插件：** Dataview、Templater、Graph View、Excalidraw（画思维导图）
