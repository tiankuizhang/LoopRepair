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

## 选题来源约定

公开笔记应区分“谁生成内容”和“谁选择题目”。

- `author` 表示公开署名。AI 生成或主要整理的公开笔记使用 `LoopRepair AI Writer`。
- `generator` 表示实际生成工具或模型名，例如 `ChatGPT`、`Gemini`、`Claude`、`Codex`、`Copilot`。
- `origin` 表示内容来源机制，例如 `conversation` 或 `autonomous`。
- `selection` 表示选题方式：
  - `user-directed`：用户明确提出、确认或由用户问题链触发；
  - `ai-autonomous`：AI 自主选择题目；
  - `manual`：人类作者手动选题与写作。

用户触发的公开笔记默认使用：

```yaml
author: LoopRepair AI Writer
origin: conversation
selection: user-directed
```

自主笔记默认使用：

```yaml
author: LoopRepair Autonomous Writer
origin: autonomous
selection: ai-autonomous
```

## 公共事件笔记

涉及新闻、时政、社会争议、公共事件、平台舆论与食品安全等话题时，默认写入 `docs/notes/`，类型使用 `public-event-note`。

公共事件笔记不追求新闻快照，而追求可回看的结构观察。写作时应优先保存：

- 事件如何被命名；
- 舆论如何分裂；
- 责任如何流动；
- 哪些表达、话术或句子反复出现；
- 这件事几年后仍值得回看的原因。

公共事件笔记不应写入 `docs/autonomous/`，除非它不是回应当前用户话题，而是 autonomous writer 独立选择的题目。

## 信息来源约定

涉及公共事件、新闻、社会争议与时政话题时，应区分：

- 事实来源：官方通报、原始报道、一手采访、权威媒体报道；
- 舆论来源：社交媒体、评论区、热搜、短视频平台讨论；
- 作者观察：笔记作者或生成工具的分析、归纳与判断；
- 未确认信息：传言、二手截图、营销号转述、尚无权威确认的说法。

不得将舆论、猜测或未确认信息直接写成事实。
不得用单一低可信来源支撑强结论。
如果事件仍在发展中，应明确写出“据当时公开报道与讨论”或类似限定。

公共事件笔记的目标不是形成最终真相，而是保证后续可回溯。

## 公共事件笔记格式

公共事件笔记建议包含以下结构：

```md
---
title: <标题>
date: YYYY-MM-DD
type: public-event-note
status: published
author: LoopRepair AI Writer
generator: <实际生成工具或模型名>
origin: conversation
selection: user-directed
source_state: public-reporting-and-discourse
tags:
  - <tag1>
  - <tag2>
  - <tag3>
---

# <标题>

> **日期**：YYYY-MM-DD  
> **类型**：public-event-note  
> **作者**：LoopRepair AI Writer  
> **生成工具**：<实际生成工具或模型名>  
> **来源**：conversation  
> **选题方式**：user-directed  
> **信息状态**：public-reporting-and-discourse  
> **标签**：tag1 / tag2 / tag3

## 事件

## 命名

## 舆论

## 责任结构

## 可保存的句子

## 回看

## 来源

### 事实来源

### 舆论样本

### 说明
```

## 归属说明

GitHub commit 的 author/committer 可能显示为仓库所有者；实际来源以 commit message 前缀和本文件约定为准。
