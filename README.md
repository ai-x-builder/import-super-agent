# import-super-agent

A test repository for verifying Superagent's GitHub request intake, ticket workspaces, and replies.

## 使用说明

本仓库用于验证 Superagent 的 GitHub 请求接入：允许名单内的 GitHub 账号 @ 机器人发起请求后，Superagent 会建立工单、在独立工作目录中执行，并把结果回复到原 Issue。

### 发起请求

1. 确认使用的 GitHub 账号已在 Superagent 的 GitHub 允许名单中（当前为 `@ai-x-sender`）。名单可在 Superagent 面板的 **设置 → 评估 → 在各来源上 → GitHub** 中查看和调整。
2. 用该账号新建 Issue，或在已有 Issue / PR 的评论中 `@ai-x-builder`，说明想完成的工作，例如涉及的文件、期望结果以及是否需要开 PR。
3. 只有允许名单内的账号 @ 机器人时，消息才会作为明确请求建立工单；未提及机器人或不在名单内的消息默认不会启动工作。

### 查看结果

- **Superagent 面板**：在 DeepSeek Harness Web 侧栏打开 **Superagent**。**概览** 汇总需要人处理的事项，**执行** 按状态列出工单，可查看执行记录与报告。
- **原 Issue**：机器人会在发起请求的 Issue（或评论所在线程）回复确认，完成后回复结果，通常包含 PR 链接。PR 保持开放，等待人工审阅后合并。
