---
name: vibe-coding-standard
description: Use this skill when creating, initializing, or substantially restructuring a software project so the result is a compact, publishable GitHub repository with clear documentation, tests, CI, and maintainable structure.
metadata:
  short-description: Build compact, publishable repositories
---

# Vibe Coding 规范

当用户要求创建、初始化、脚手架化、重构一个软件项目，或明确提到 “vibe coding” 时，使用本规范。

目标：把项目做成完整、成熟、可维护、可发布的 GitHub 仓库，而不是一次性脚本集合。优先遵循目标技术栈的成熟约定；本规范用于补齐发布质量底线。

## 仓库要求

- 文档默认用英文写。
- 必须有 `README.md`。
- `README.md` 的开头必须是一级标题，紧接着放这段双语说明：

```markdown
# <Title>
> You can use AI to translate or explain this document and the rest of the project's documentation in your preferred language.
>
> 你可以使用 AI 将本文档和本项目的其他文档翻译成你偏好的语言，或为你解读其中的内容。
```

- 因此，仓库中通常不再提供其他语言版本的平行文档。
- 源码放在 `src/` 等专门目录下；根目录不堆零散源码。
- `README.md` 之外的文档放在 `docs/` 下。
- `docs/` 下建议至少包含 `cli.md`、`design.md`、`workflows.md`；如果项目确实不需要某份文档，可以省略，但不要放空壳。
- 不在项目代码、脚本、文档中硬编码绝对路径。
- 必须有 `LICENSE`，默认使用 MIT License。
- 必须有 `.gitignore`，并匹配项目技术栈。
- 必须有单元测试。
- 必须有 GitHub Actions，在 `push` 和 `pull_request` 时自动运行测试。

推荐最小结构：

```text
repo/
├─ src/
├─ tests/
├─ docs/
│  ├─ cli.md
│  ├─ design.md
│  └─ workflows.md
├─ .github/
│  └─ workflows/
├─ README.md
├─ LICENSE
└─ .gitignore
```

## 文档要求

文档应清楚说明：

- 项目用途
- 安装方式
- 使用方法
- 必要示例

如果项目提供 CLI：

- 命令结构应简洁。
- 必须有文档说明。
- 必须支持 `-h` / `--help`。

## README 规范

README 用英文写，风格偏技术说明文：直接、克制、具体，不写宣传文案。

开头先说“这是什么”，再说“怎么用”。推荐三段式：
1. 一句话定义项目。
2. 一两句话说明核心行为。
3. 一句话说明边界或非目标。

开头尽量简短。

术语处理：

- 术语先定义，再使用。
- 如果开头解释术语会影响行文，可单独写简短的 `Terminology` 小节。
- 首次出现的专业术语，应给读者基本落脚点。
- 如果术语有项目内特定含义，要先说明。
- 如果术语较小众，首次出现时可用斜体、超链接和一句简短解释。
- 罕见情况：如果文档用中文书写，那么术语自然是中文的，但是如果中文名不是业界通用的，可以在首次出现时额外加上括号注明英文原文。

可以使用心智模型级别的图示、伪代码和简短结构图，前提是它们确实有助于说明问题。

README 结尾注明：

```markdown
This project was written collaboratively by humans and AI.
```

需要 README 骨架时，可使用 `templates/README.template.md`。

## 设计文档规范

设计文档采取自顶而下的写法：

1. 先说明要解决什么问题。
2. 再说明整体思路。
3. 再说明主要组成部分。
4. 再说明它们如何交互。
5. 最后再进入实现细节。

设计文档通常应覆盖：

- 项目目标
- 非目标
- 核心抽象
- 架构概览
- 数据流或控制流
- 关键接口
- 约束与权衡
- 可扩展点
- 未决问题（如有）

## 执行流程

1. 只确认会阻塞实现的产品或技术栈选择。
2. 建立最小可发布结构。
3. 在源码目录中实现核心行为。
4. 为核心行为和关键边界添加单元测试。
5. 配置 GitHub Actions 运行测试。
6. 编写与实际代码一致的 README 和必要文档。
7. 运行可用的格式化、lint 和测试命令。
8. 交付时说明改了什么、如何验证、还剩哪些缺口。

## 最低标准

项目脱离聊天记录后仍应可维护：

- 结构清楚
- 文档可读
- 行为可测试
- 意图可理解
- 可被他人克隆、运行、测试和继续开发
