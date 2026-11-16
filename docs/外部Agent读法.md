---
title: 外部Agent读法
type: meta
tags: [meta, agent-access]
updated: 2026-11-16
---

# 外部 Agent 读法

本库对外有两个出口，**读之前先看自己在哪条路上**：

| 仓 | 可见性 | 内容 | 谁能读 |
|---|---|---|---|
| `kitsiu1211-stack/obsidian-project-hub` | **private** | 全量主库（concepts / docs / builders / clients / reviews / raw / AI场景 / Projects） | 袁鑫杰、Hermes（浪子）、Koa 等被授权的身份 |
| `kitsiu1211-stack/obsidian-agent-export` | **public** | 只有 `index.md` + `concepts/` + `docs/` + `builders/` + `SCHEMA.md` | 任何人，含 Mark 等云端 Agent |

两个仓都是**只读快照**，主库改了不会实时变：公开导出仓每天 08:00 同步一次（`~/.hermes/scripts/agent_export_sync.sh`），私有主库随手动 push 更新。

## 公开导出仓怎么读（Mark 走这条）

1. 先取 `README.md` 看白名单与规则，再取 `index.md` 定位主题，最后按需读单篇 —— **不要整库 dump**。
2. 单文件原文：`https://raw.githubusercontent.com/kitsiu1211-stack/obsidian-agent-export/main/<path>`
3. 列目录 / 批量取：`https://api.github.com/repos/kitsiu1211-stack/obsidian-agent-export/contents/<dir>`（未认证限 60 次/小时）
4. 导出时客户/企业名按 `~/.hermes/scripts/export_anonymize.tsv` 替换成「某 + 行业 + 企业」，所以你看到的不是真名；引用时保留这个匿名说法。

## 私有主库怎么读（Koa / 有授权的身份）

私有仓不能用 `raw.githubusercontent.com` 匿名拉，必须带 token：

```
curl -H "Authorization: Bearer $GITHUB_TOKEN" \
     -H "Accept: application/vnd.github.raw" \
     https://api.github.com/repos/kitsiu1211-stack/obsidian-project-hub/contents/<path>
```

读法同上：先 `index.md`，再按需读单篇。`clients/`、`reviews/`、`raw/` 含客户信息与内部复盘，引用一律匿名化，原文不外发。

## 命名与结构铁律

- `concepts/主题N-标题.md`，**N = 当前最大编号 + 1**，不复用旧号。
- 单篇固定四段：`## Compiled Truth` / `## 关键要点` / `## 关联主题` / `## Timeline`。
- `[[wikilink]]` 是库内交叉引用，按文件名匹配。

## 不写

- **只读**：不 push、不建 PR、不改文件、不建分支。
- 要沉淀新内容：发到群里交给「浪子 / Mark 42」，或按 `_inbox/README.md` 的约定投进 `_inbox/`（只有主库侧能写），由主库合并后下次同步才出现在公开仓。
