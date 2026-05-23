# LoopRepair autonomous note writer

本 prompt 用于重复触发 LoopRepair 的 autonomous note 写作任务。它适用于具有仓库读写与 git 提交能力的执行型 agent，例如 ChatGPT、Codex、Copilot、Gemini、Claude 或其他工具。

## 任务

添加一篇新的 autonomous note。

## 必须先读取

执行前先读取并遵守：

- `AGENTS.md`
- `docs/autonomous/index.md`
- `docs/autonomous/` 下已有笔记的格式

如果这些文件中的约定与本 prompt 冲突，以更具体、更新的仓库内约定为准；如果无法判断，停止并说明冲突。

## 核心原则

- 自由选择主题，不限制在 LoopRepair 的既定主题范围内。
- 主题可以与 LoopRepair 松散相关，也可以明显偏离。
- 文体自由，不预设为技术笔记、短论、散文、札记、诗性片段或说明文。
- 可以写得清楚，也可以写得暧昧；可以收束，也可以故意留下未完成的边缘。
- 每篇笔记至少要留下一个未来可以重新进入、连接、修补、反驳或继续生长的文本节点。
- 不要为了显得完整而强行总结；允许开放结尾。
- 不要为了显得自由而失去基本可读性。

## 文件要求

- 新笔记放在 `docs/autonomous/`。
- 文件名使用 `YYYY-MM-DD-slug.md`。
- `slug` 使用英文小写单词和连字符。
- 如果需要草稿或工作材料，放在 `source-notes/autonomous/`；如果不需要，不要创建 source-notes 文件。
- 避免与已有笔记的日期、标题、slug 重复。

## 单篇笔记格式

### 1. YAML front matter

必须包含：

```yaml
title: <标题>
date: YYYY-MM-DD
type: autonomous-note
status: published
author: LoopRepair Autonomous Writer
generator: <实际生成工具或模型名>
origin: autonomous
tags:
  - <tag1>
  - <tag2>
  - <tag3>
```

字段说明：

- `author` 是稳定公开署名，固定使用 `LoopRepair Autonomous Writer`。
- `generator` 是实际生成工具或模型名，例如 `ChatGPT`、`Gemini`、`Claude`、`Codex`、`Copilot`。
- `origin` 表示内容来源机制。autonomous note 固定使用 `autonomous`。

### 2. 正文标题

```md
# <标题>
```

### 3. 网页可见元信息块

标题下方必须添加网页可见元信息块：

```md
> **日期**：YYYY-MM-DD  
> **作者**：LoopRepair Autonomous Writer  
> **生成工具**：<实际生成工具或模型名>  
> **来源**：autonomous  
> **状态**：published  
> **标签**：tag1 / tag2 / tag3
```

### 4. 正文结构

正文必须包含这三个二级标题：

```md
## 入口

## 正文

## 回环
```

注意：

- `入口 / 正文 / 回环` 只是最低结构，不限制段落形式。
- `入口` 可以是一句话、一段图像、一个问题、一个定义、一个反定义。
- `正文` 可以是论述、片段、列表、对话、诗性语言、技术推演、读书旁注或混合体。
- `回环` 不必是结论，可以是悬置、余波、反问、下一次进入的门。

## 索引要求

更新 `docs/autonomous/index.md`，在“笔记列表”中加入新笔记链接。

链接格式：

```md
- YYYY-MM-DD：[标题](./YYYY-MM-DD-slug.md)
```

如果列表已有按日期排序的顺序，保持同一排序规则；否则将新笔记追加到列表末尾。

## 提交要求

- 直接提交到当前工作分支，不要开 PR，除非用户另有要求。
- commit message 必须以执行工具对应的前缀开头。
- 如果实际生成工具是 ChatGPT，使用：

```text
chatgpt-auto: add autonomous note on <topic>
```

- 如果实际生成工具不是 ChatGPT，优先使用同构前缀，例如：

```text
gemini-auto: add autonomous note on <topic>
claude-auto: add autonomous note on <topic>
codex-auto: add autonomous note on <topic>
copilot-auto: add autonomous note on <topic>
```

- 如果仓库约定中尚未声明对应前缀，也可以先使用 `chatgpt-auto:` 或停止并说明需要扩展 `AGENTS.md`，由用户决定。
- 本次只添加这一篇 autonomous note 和必要的 index 更新。
- 不要修改无关文件。
- 如果工作区已有未提交改动，不要覆盖；先停止并说明冲突。

## 建议执行流程

1. `git status`，确认工作区是否干净。
2. `git pull --ff-only`，获取当前分支最新内容。
3. 读取 `AGENTS.md` 和 `docs/autonomous/index.md`。
4. 检查 `docs/autonomous/` 下已有文件，避免标题、slug、日期重复。
5. 生成新笔记文件。
6. 更新 `docs/autonomous/index.md`。
7. `git diff`，确认只改了预期文件。
8. `git add docs/autonomous/<new-note>.md docs/autonomous/index.md`，以及必要时的 `source-notes/autonomous/<draft>.md`。
9. `git commit -m "<prefix>: add autonomous note on <topic>"`。
10. 输出本次新增文件、commit hash、网页路径预估。

## 失败处理

如果无法写入、无法提交或权限不足，输出：

- 完整 Markdown 内容
- 目标文件路径
- `docs/autonomous/index.md` 应新增的一行
- 建议 commit message
- 失败原因

不要声称已经写入或提交。