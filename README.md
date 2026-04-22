# Vibe Coding 规范 Skill

这是一个通用的 vibe coding 规范 skill，用于指导 coding agent 创建完整、紧凑、可维护、可发布的 GitHub 项目。

它要求项目具备清晰 README、MIT License、`.gitignore`、源码目录、测试、GitHub Actions，以及必要但不臃肿的文档。它不绑定任何特定 agent、编辑器或运行平台。

**非目标：** 提供某个语言或框架的完整脚手架；替代具体技术栈的官方最佳实践；生成大而全的模板仓库。

## 文件

| 路径 | 用途 |
| --- | --- |
| `SKILL.md` | skill 主体说明和触发元数据 |
| `templates/README.template.md` | 生成项目时可复用的 README 模板 |

## 使用

让 coding agent 直接读取本项目的`SKILL.md` 即可。

常见的 coding agent 还支持把本目录作为 skill 目录加载：

1. Codex: 将本项目放置于项目当前目录：`<project>/.codex/skills/`（适合当前 repo 专用）或者个人目录 `~/.codex/skills/`（作为全局配置）。在 Codex CLI 中通过 `$vibe-coding-standard` 使用。

## License

MIT License. See [LICENSE](LICENSE) for details.
