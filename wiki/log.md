---
title: 操作日志 (Log)
type: log
updated: 2026-08-22
---

# 操作日志（Log）

> 仅追加的 chronological 记录。grep 用法：`grep "^## \[" log.md | tail -5`
> 前缀约定：`INIT` 初始化 / `INGEST` 摄入 / `QUERY` 查询 / `LINT` 体检 / `UPDATE` 更新

## [2026-08-22] INIT | 创建个人知识库
基于 Karpathy LLM Wiki 模式，在桌面初始化三层架构：raw/（原始资料）、wiki/（LLM 维护）、WIKI-SCHEMA.md（模式定义）。建立 index.md 与 log.md。等待第一份资料摄入。

## [2026-08-22] MOVE | 迁移至 iCloud 云盘
桌面空间不适合长期承载知识库（易 clutter、无跨设备访问）。经评估，本机已启用 iCloud 云盘（工作区即位于 CloudDocs 下），故将整个知识库迁移至 iCloud 云盘根目录：`~/Library/Mobile Documents/com~apple~CloudDocs/个人知识库/`（Finder 显示为「iCloud 云盘 / 个人知识库」）。理由：自动同步 iPhone/iPad、Obsidian 移动端可直接读取、免备份运维。git 仓库一并迁移保留。注意：iCloud + git 在单写端（仅本 Mac 提交、移动端只读）风险可控；若后续多设备同时写入出现冲突，应移除 git 或改用云盘原生版本历史。
