# Humanize Coding Agents

[English](README.md)

让 Coding Agent 像靠谱的工程师同事一样沟通。

![一个 Coding Agent 站在流动代码前，旁边写着“用直白的语言说清重点”。](assets/readme-hero.jpg)

`humanize-coding-agents` 是一个面向 Coding Agent 的 Skill，适用于实现进度、调试、代码审查、代码解释、注释、提交信息和 PR 描述。它会去掉泛泛而谈、结构僵硬的 AI 腔，但不会隐藏不确定性，也不会为了简短而删掉技术细节。

## Before and after

Before：

> 配置子系统采用了一种复杂的多层解析范式，通过具有优先级感知能力的规范化流程动态协调多个输入源，使上下文相关的值能够在整个应用中无缝传递，同时保留灵活的覆盖语义。

After：

> `resolveConfig()` 先读取用户配置，再读取仓库配置，最后读取命令行参数。每一步都会覆盖前一步中同名的值，所以 `--timeout 30` 的优先级高于两个配置文件。

后一个版本直接说明了配置的优先级，沿着代码说明数据如何流动，并给出了一个具体结果。

## 它会改变什么

- 先回答问题，再解释过程。
- 用代码、行为、证据和后果替代空泛的判断。
- 从实际含义入手重写空洞的对比、戏剧化的收尾和机械对称的句式，而不是简单替换几个“AI 高频词”。
- 证据足够时给出明确建议。
- 区分已验证事实、推断、假设和未知信息。
- 只使用当前回答真正需要的结构。
- 保留重要的失败、风险和未测试部分。
- 检查改写后的内容是否保留原文的事实、置信度、因果关系、范围和精确技术字面量。

这个 Skill 不会用俚语、虚构经历、刻意粗糙的表达或禁用词列表来伪造“人味”。它对自然表达的定义更简单：针对当前读者和当前仓库，做出有依据的判断。

## 安装

### Codex

将仓库克隆到 Codex 的 skills 目录：

```bash
git clone https://github.com/vodkaslime/humanize-coding-agents.git \
  "${CODEX_HOME:-$HOME/.codex}/skills/humanize-coding-agents"
```

### 其他 Agent Skills 客户端

将仓库克隆或复制到客户端配置的 skills 目录中。入口文件是 [`SKILL.md`](SKILL.md)。

## 使用

通过 `$humanize-coding-agents` 显式调用：

```text
使用 $humanize-coding-agents 解释这个队列如何处理重试。
```

```text
使用 $humanize-coding-agents 审查这个 PR，只报告可执行的发现。
```

```text
使用 $humanize-coding-agents 重写这段实现进度说明，但不要丢掉测试结果或风险。
```

## 适用范围

这个 Skill 为以下场景提供了单独的指导：

- 计划、进度更新和完成报告；
- 代码审查和代码解释；
- 提交信息和 PR 描述；
- 注释、文档字符串、TODO 和架构说明。

详细示例见 [`references/examples.md`](references/examples.md)。

## 许可证

本项目采用 [Apache License 2.0](LICENSE) 授权。
