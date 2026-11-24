# import-super-agent

A test repository for verifying Superagent's GitHub request intake, ticket workspaces, and replies.

## 使用说明

本仓库用于验证 Superagent 如何接收 GitHub 请求、在独立工作目录中执行工单，以及将处理结果发回原讨论。

### 发起请求

1. 确认使用的 GitHub 账号已在 Superagent 的 GitHub 允许名单中（当前为 `@ai-x-sender`）。名单可在 Superagent 面板的 **设置 → 评估 → 在各来源上 → GitHub** 中查看和调整。
2. 用该账号在新建 Issue 的正文或已有 Issue / PR 的新评论中 `@ai-x-builder`，说明想完成的工作，例如涉及的文件、期望结果以及是否需要开 PR。
3. Superagent 会评估明确请求，决定是否新建工单或交给已有工单。已有工单的跟进可以直接发到原讨论。当前使用「仅观察」模式，推断出的候选任务只会记录评估结果。

### 查看结果

- 在 DeepSeek Harness Web 侧栏打开 **Superagent**。**概览** 汇总需要人处理的事项，**执行** 按状态列出工单。打开工单可查看状态和关联讨论，并进入执行器 Session 查看执行记录。
- 在原 Issue 或 PR 的讨论中查看受理确认和处理结果。任务生成 PR 时，可从回复打开链接，由人工审阅并决定是否合并。
