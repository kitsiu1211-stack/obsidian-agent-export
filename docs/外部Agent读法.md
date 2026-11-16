---
title: 外部Agent读法
type: meta
tags: [meta, agent-access]
updated: 2026-11-16
---

# 外部 Agent 读法（本仓只读）

本仓是 Obsidian 主库（`~/Documents/Obsidian Vault`）的 GitHub 镜像，**只读**。任何 Agent（豆包工作伙伴 Mark、Claude Code、Codex、其他数字员工）都可以直接读，不需要设备授权。

## 目录

| 路径 | 内容 |
|---|---|
| `index.md` | 总索引，含页数与最近更新 |
| `concepts/` | 概念笔记。**命名铁律：`主题N-标题.md`，编号 = 当前最大编号 + 1** |
| `docs/` | 方法论与说明 |
| `builders/` | 人/组织相关笔记 |
| `clients/` | 客户档案 |
| `reviews/` | 周复盘 |
| `raw/` | 原始记录（会议/文章摘录） |
| `assets/` | 图片 |
| `SCHEMA.md` / `log.md` | 库结构与变更日志 |

单篇笔记结构固定四段：`## Compiled Truth` / `## 关键要点` / `## 关联主题` / `## Timeline`。`[[wikilink]]` 是库内交叉引用，按文件名匹配。

## 怎么读

1. 先取 `index.md` 定位主题，再按需读单篇——不要整库 dump（`concepts/_weekly-reads.md` 25KB+，全库 100+ 篇）。
2. 单文件原文：`https://raw.githubusercontent.com/kitsiu1211-stack/obsidian-project-hub/main/<path>`
3. 列目录 / 批量取：`https://api.github.com/repos/kitsiu1211-stack/obsidian-project-hub/contents/<dir>`（未认证限 60 次/小时）
4. 仓库是 git 快照，主库更新后（通常每天）才变。回答里要注明依据的文件路径与该文件 `updated` 字段。

## 怎么不读 / 不写

- **只读**：不要 push、不要建 PR、不要改文件、不要建分支。
- 要沉淀新内容：发到群里交给「浪子 / Mark 42」，或开 issue 说明要点，由主库侧合并后再同步。
- `clients/`、`reviews/`、`raw/` 含客户信息与内部复盘：引用时按「某 + 行业 + 企业」匿名化，不外发原文与全文摘录。
