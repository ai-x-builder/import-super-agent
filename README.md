# import-super-agent

用于验证 Superagent 如何在 GitHub 上接收请求、在独立工作区中执行工单，并把结果回复到原讨论的测试仓库。

> A test repository for verifying Superagent's GitHub request intake, ticket workspaces, and replies.

## 仓库说明

本仓库不包含产品代码，只保留本 README，用于走通并观察 Superagent 的完整链路：

- **请求接入**：识别允许名单账号在 Issue / PR 讨论中发出的明确请求。
- **工单执行**：为每个工单创建独立工作区，在其中完成改动和校验。
- **结果回复**：把受理确认、处理结果和 PR 链接发回原讨论，交由人工审阅。

## 工作流程

请求 → 评估与建单 → 独立工作区执行 → 结果回复原讨论 → 人工审阅并合并 PR。

## 使用说明

### 发起请求

1. 确认使用的 GitHub 账号已在 Superagent 的 GitHub 允许名单中（当前为 `@ai-x-sender`）。名单可在 Superagent 面板的 **设置 → 评估 → 在各来源上 → GitHub** 中查看和调整。
2. 用该账号在新建 Issue 的正文或已有 Issue / PR 的新评论中 `@ai-x-builder`，说明想完成的工作，例如涉及的文件、期望结果以及是否需要开 PR。
3. 已有工单的跟进可以直接发到原讨论，无需另开 Issue。

### 查看结果

- **面板**：在 DeepSeek Harness Web 侧栏打开 **Superagent**。**概览** 汇总需要人处理的事项，**执行** 按状态列出工单。打开工单可查看状态和关联讨论，并进入执行器 Session 查看执行记录。
- **原讨论**：在原 Issue 或 PR 中查看受理确认和处理结果。任务生成 PR 时，可从回复打开链接，由人工审阅并决定是否合并。

## 当前限制

- 当前使用「仅观察」模式：推断出的候选任务只记录评估结果。
- PR 由人工审阅后合并。

## 仓库结构

```text
.
└── README.md
```
