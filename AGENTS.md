# AI 协作约定

本仓库可能由人类作者与多个 AI 工具共同维护。为便于回溯来源，所有 AI 参与的改动应遵守以下约定。

## Commit message

提交信息使用前缀标明主要执行者：

- `chatgpt:`：由 ChatGPT 在对话中直接写入或主要生成。
- `codex:`：由 Codex 执行或主要生成。
- `copilot:`：由 GitHub Copilot 执行或主要生成。
- `manual:`：由人类作者手动完成。

示例：

```text
chatgpt: add pages notes index
chatgpt: clarify source and published notes
codex: refactor pages navigation
manual: revise homepage wording
```

## 审核原则

- 内容型改动应先给出拟写内容，经过人类作者确认后再写入。
- 结构型改动应优先保持小步提交，避免一次性引入复杂框架。
- GitHub Pages 展示内容放在 `docs/` 下。
- 仓库侧原始笔记与工作材料放在 `source-notes/` 下。

## 归属说明

GitHub commit 的 author/committer 可能显示为仓库所有者；实际来源以 commit message 前缀和本文件约定为准。
