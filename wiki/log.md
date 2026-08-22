---
title: 操作日志 (Log)
type: log
updated: 2026-08-22
---

# 操作日志（Log）

> 仅追加的 chronological 记录。grep 用法：`grep "^## \[" log.md | tail -5`
> 前缀约定：`INIT` 初始化 / `INGEST` 摄入 / `QUERY` 查询 / `LINT` 体检 / `UPDATE` 更新 / `REMOTE` 远端

## [2026-08-22] INIT | 创建个人知识库
基于 Karpathy LLM Wiki 模式，在桌面初始化三层架构：raw/（原始资料）、wiki/（LLM 维护）、WIKI-SCHEMA.md（模式定义）。建立 index.md 与 log.md。等待第一份资料摄入。

## [2026-08-22] MOVE | 迁移至 iCloud 云盘
桌面空间不适合长期承载知识库（易 clutter、无跨设备访问）。经评估，本机已启用 iCloud 云盘（工作区即位于 CloudDocs 下），故将整个知识库迁移至 iCloud 云盘根目录：`~/Library/Mobile Documents/com~apple~CloudDocs/个人知识库/`（Finder 显示为「iCloud 云盘 / 个人知识库」）。理由：自动同步 iPhone/iPad、Obsidian 移动端可直接读取、免备份运维。git 仓库一并迁移保留。注意：iCloud + git 在单写端（仅本 Mac 提交、移动端只读）风险可控；若后续多设备同时写入出现冲突，应移除 git 或改用云盘原生版本历史。

## [2026-08-22] UPDATE | 确立两层架构与手机摄入工作流
与使用者对齐核心目标：(1) 长期稳定、专属、可累积、可链接到 WorkBuddy 及任意系统；(2) 手机随手捕获资料。据此在 WIKI-SCHEMA.md 固化两层存储架构——iCloud 云盘为实时同步层（手机捕获 + 多设备读取），git 远端（GitHub 等）为耐久与可移植层（备份 + 版本 + 跨系统链接）。新增 `raw/inbox/` 作为手机投递箱，明确定义「手机只捕获、Mac/WorkBuddy 处理」的分工以规避 iCloud+git 冲突。跨系统链接原则：唯一事实来源 = 开放 Markdown + git 远端；IMA 等仅作单向下游消费。待办：git 远端尚未配置（本机无 gh CLI，需使用者提供 GitHub 仓库或授权）。

## [2026-08-22] REMOTE | GitHub 远端打通（SSH）
git 远端层完成配置。GitHub 账号：Merryfeng123，仓库名：`personal-wiki`（描述：智贤宝库），私有。SSH 密钥：ed25519 专用密钥 `~/.ssh/id_ed25519_wiki`（comment: fengxiaoqing-mac-wiki）已添加至 GitHub SSH keys，标题「冯小青-mac」。远端地址：`git@github.com:Merryfeng123/personal-wiki.git`。4 次本地提交已全部推送至远端，`origin/main` 与 `HEAD` 一致。至此两层存储架构完整落地：iCloud 云盘 = 实时同步层，GitHub = 耐久/可移植层。下一步：首次 ingest（摄入资料）。

## [2026-08-22] INGEST | 首次摄入：龙师闭关感言（佛法经典资料库奠基）
建立「佛法经典」专属存储库：原始资料复制至 `raw/佛法经典/龙师说法/20240608-龙师闭关感言/`（含 77MB 视频 + 60KB 逐字稿 docx）；视频经 `.gitignore` 排除出 git（git 不存大媒体），逐字稿为唯一可检索文本。生成 3 个 wiki 页：source-summary `wiki/佛法经典/20240608-龙师闭关感言.md`、entity `wiki/人物/龙师.md`、concept `wiki/佛法经典/闭关（实修次第）.md`；更新 `index.md`（新增佛法经典类目）与 `WIKI-SCHEMA.md`（注册佛法经典为指定收藏）。桌面原文件保留未删（遵循个人文件安全规范）。

## [2026-08-22] ARCHIVE | 工作资料归档（仅存储，未摄入）
将 `raw/inbox/` 中两份工作资料移入 `raw/工作/项目投标资料/`：① 兴业银行报价清单20260808v1.xlsx（投标报价，224K）；② 深汕高中园（综合高中）项目智能化工程招标文件_V1.0（PDF，318 页，1.4M）。按使用者确认策略「工作/佛法 = 仅归档、自媒体 = 摄入」，本次不做 wiki 提炼。`inbox/` 现已清空。

## [2026-08-22] ARCHIVE | 龙师说法全库归档至佛法经典
将桌面 `龙师说法/` 全集复制至 `raw/佛法经典/龙师说法/`（桌面原件保留未删）。规模：72 个讲座子目录、17GB、168 个视频(.mp4)、73 份逐字稿(.docx)。按已确认策略「佛法 = 仅归档」，视频全格式经 `.gitignore` 排除出 git（仅存 iCloud，Mac/iPhone/Obsidian 可观看，不进 GitHub、不跨非 Apple 系统）；73 份逐字稿（含首次 ingest 已提交之闭关感言 1 份 + 本次新增 72 份）全部进 git/GitHub，可被任意系统检索与链接。提交 `5d4be77` 已推送。注意：毗沙门天王子目录含一份 `副本.docx`（来源重复），未去重。
