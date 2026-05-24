# LoopRepair public event note writer

本 prompt 用于把用户明确提出的新闻、公共事件、社会争议、时政舆论或食品安全事件整理为 LoopRepair 的公开笔记。

## 任务

添加一篇新的 public event note。

## 必须先读取

执行前先读取并遵守：

- `AGENTS.md`
- `docs/notes/index.md`（如果存在）
- `docs/notes/` 下已有笔记的格式（如果存在）

如果仓库内约定与本 prompt 冲突，以更具体、更新的仓库内约定为准。

## 写作目标

公共事件笔记不追求新闻快照，而追求可回看的结构观察。

应优先记录：

- 事件如何被命名；
- 舆论如何分裂；
- 责任如何流动；
- 哪些公共话术反复出现；
- 哪些句子值得保存；
- 这件事几年后为什么仍值得回看。

不要把笔记写成新闻报道、情绪宣泄、立场檄文或资料堆砌。

## 信息来源规则

涉及事实、数据、时间线、官方表态、媒体报道时，必须尽量引用可信来源。

写作时应区分：

- 事实来源：官方通报、原始报道、一手采访、权威媒体报道；
- 舆论来源：社交媒体、评论区、热搜、短视频平台讨论；
- 作者观察：笔记作者或生成工具的分析、归纳与判断；
- 未确认信息：传言、二手截图、营销号转述、尚无权威确认的说法。

不得将舆论、猜测或未确认信息直接写成事实。  
不得用单一低可信来源支撑强结论。  
如果事件仍在发展中，应明确写出“据当时公开报道与讨论”或类似限定。

## 文件要求

- 新笔记放在 `docs/notes/`。
- 文件名使用 `YYYY-MM-DD-slug.md`。
- 日期必须按北京时间计算，即 `Asia/Shanghai` / UTC+08:00。
- `slug` 使用英文小写单词和连字符。
- 避免与已有笔记的日期、标题、slug 重复。

## 单篇笔记格式

必须包含 YAML front matter：

```yaml
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
```

正文格式：

```md
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

简要说明发生了什么。只写必要事实，不追求新闻全集。

## 命名

分析事件名称、关键词、传播标签和情绪压缩方式。

## 舆论

记录主要舆论分歧。区分媒体报道、社交平台声音和作者观察。

## 责任结构

分析责任如何在不同主体之间流动，例如生产者、平台、媒体、监管、消费者、旁观者。

## 可保存的句子

保存具有代表性的公共表达、话术或反问。不要大量复制原文。

## 回看

说明这件事几年后仍值得回看的原因。

## 来源

### 事实来源

- 来源名称：《标题》，日期，链接或可检索说明。

### 舆论样本

- 平台或讨论场域，日期，简要说明。

### 说明

本文主要记录公共事件中的舆论结构与责任流动，不构成事实终审。
```

## 索引要求

如果 `docs/notes/index.md` 存在，更新其中的笔记列表：

```md
- YYYY-MM-DD：[标题](./YYYY-MM-DD-slug.md)
```

如果不存在，创建 `docs/notes/index.md`：

```md
# 笔记目录

这里保存由用户明确提出、确认或触发的公开笔记。

不同于 `docs/autonomous/`，本目录中的内容通常来自具体对话、问题链或人工选题。

## 类型

- `conversation-note`：由对话整理出的普通笔记。
- `public-event-note`：围绕新闻、公共事件、社会争议或舆论结构整理的笔记。

## 笔记列表
```

## 提交要求

- 直接提交到当前工作分支，不开 PR，除非用户另有要求。
- commit message 使用：

```text
chatgpt: add public event note on <topic>
```

如果只是新增或修改 prompt，使用：

```text
chatgpt: add public event note prompt
```

## 失败处理

如果无法写入、无法提交或权限不足，输出：

- 完整 Markdown 内容；
- 目标文件路径；
- index 应新增的一行；
- 建议 commit message；
- 失败原因。
