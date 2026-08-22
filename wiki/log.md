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

## [2026-08-22] UPDATE | 确立两层架构与手机摄入工作流
与使用者对齐核心目标：(1) 长期稳定、专属、可累积、可链接到 WorkBuddy 及任意系统；(2) 手机随手捕获资料。据此在 WIKI-SCHEMA.md 固化两层存储架构——iCloud 云盘为实时同步层（手机捕获 + 多设备读取），git 远端（GitHub 等）为耐久与可移植层（备份 + 版本 + 跨系统链接）。新增 `raw/inbox/` 作为手机投递箱，明确定义「手机只捕获、Mac/WorkBuddy 处理」的分工以规避 iCloud+git 冲突。跨系统链接原则：唯一事实来源 = 开放 Markdown + git 远端；IMA 等仅作单向下游消费。待办：git 远端尚未配置（本机无 gh CLI，需使用者提供 GitHub 仓库或授权）。
