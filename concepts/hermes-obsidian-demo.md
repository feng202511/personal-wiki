---
title: 演示页 - Hermes ⟷ Obsidian
created: 2026-07-07
updated: 2026-07-07
type: summary
tags: [book, methodology]
sources: []
rating: ⭐⭐⭐⭐⭐
status: finished
---

# 演示：Hermes 和 Obsidian 如何协同

## 这是什么？

这个页面演示 **Hermes Agent**（本 AI）和 **Obsidian** 之间的协作关系。

## 双向链接示例

- [[原子习惯]] — 当这个页面存在时，Obsidian 图谱会显示连接
- [[刻意练习]] — 同上
- [[心流状态]] — 同上
- [[SCHEMA]] — 链接到规则文件

## 在 Obsidian 中看到的画面

1. **左侧**：文件浏览器显示 wiki 的完整目录结构
2. **右侧**：打开此页面，`[[原子习惯]]` 显示为可点击的蓝色链接
3. **图谱视图**（Ctrl+G）：显示所有页面之间的连线网络

## Hermes 做什么

- 摄入文章 → 生成结构化笔记
- 自动创建 [[wikilinks]] 交叉引用
- 更新 index.md 和 log.md
- 提交 Git 版本

## 你做什么

- 在 Obsidian 中浏览、编辑
- 添加手写感悟、画 Excalidraw 思维导图
- 用 Dataview 查询

```dataview
TABLE tags, rating FROM "entities" WHERE contains(tags, "book")
```

