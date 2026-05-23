# AI 协作约定

本仓库可能由人类作者与多个 AI 工具共同维护。为便于回溯来源，所有 AI 参与的改动应遵守以下约定。

## Commit message

提交信息使用前缀标明主要执行者：

- `chatgpt:`：由 ChatGPT 在对话中直接写入或主要生成。
- `chatgpt-auto:`：由 ChatGPT 按长期约定自行选择题目并定时添加。
- `codex:`：由 Codex 执行或主要生成。
- `copilot:`：由 GitHub Copilot 执行或主要生成。
- `manual:`：由人类作者手动完成。

示例：

```text
chatgpt: add pages notes index
chatgpt: clarify source and published notes
chatgpt-auto: add note on loops and repair
codex: refactor pages navigation
manual: revise homepage wording
```

## 目录约定

- `docs/`：GitHub Pages 发布目录，面向网页阅读。
- `docs/notes/`：用户明确要求添加或确认过的公开笔记。
- `docs/autonomous/`：ChatGPT 定时自行添加的公开笔记。
- `source-notes/`：仓库侧原始笔记与工作材料，不作为网页入口。
- `source-notes/autonomous/`：ChatGPT 自主笔记的草稿与工作材料。

## 审核原则

- 用户明确要求的内容型改动，应先给出拟写内容，经过人类作者确认后再写入。
- `docs/autonomous/` 下的自主笔记不要求逐篇预先确认，但应保持小步提交，并使用 `chatgpt-auto:` 前缀。
- 结构型改动应优先保持小步提交，避免一次性引入复杂框架。

## 归属说明

GitHub commit 的 author/committer 可能显示为仓库所有者；实际来源以 commit message 前缀和本文件约定为准。
