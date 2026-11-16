# obsidian-agent-export

Obsidian 知识库的**公开只读导出**，供外部 Agent / 数字员工（豆包工作伙伴 Mark、Koa、Claude Code、Codex 等）直接读取。由本机每天自动同步，**不要在这个仓里 PR 或改文件**。

## 目录

| 路径 | 内容 |
|---|---|
| `index.md` | 总索引（页数、最近更新） |
| `concepts/` | 概念笔记。命名铁律 `主题N-标题.md`，编号 = 当前最大编号 + 1 |
| `docs/` | 方法论与说明（`docs/外部Agent读法.md` 是完整读法） |
| `builders/` | 人 / 组织相关笔记 |
| `AI培训/`、`AI工具与框架/` | 培训材料与工具笔记 |
| `assets/` | 图片 |
| `SCHEMA.md` | 库结构与写作规范 |

单篇结构固定四段：`## Compiled Truth` / `## 关键要点` / `## 关联主题` / `## Timeline`。

## 怎么读

1. 先读 `index.md` 定位主题，再按需读单篇，不要整库 dump（100+ 篇）。
2. 单文件原文：`https://raw.githubusercontent.com/kitsiu1211-stack/obsidian-agent-export/main/<path>`
3. 列目录 / 批量：`https://api.github.com/repos/kitsiu1211-stack/obsidian-agent-export/contents/<dir>`（未认证 60 次/小时）
4. 内容是每日快照，回答里注明依据的文件路径与该文件 `updated` 字段。

## 边界

- 本仓**不含**客户档案（`clients/`）、周复盘（`reviews/`）、原始记录（`raw/`），这些留在私有主库；正文里出现的客户名已做匿名化（某 + 行业 + 企业）。
- 只读：不要 push、不要建 PR、不要建分支。
- 需要沉淀新内容：交给本机 Agent「浪子 / Mark 42」，或开 issue 说明要点，由主库侧合并后再同步。
