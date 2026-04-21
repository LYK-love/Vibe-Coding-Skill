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

把本目录作为一个 skill 包发布或复制到支持 skill 的运行环境中，并保持 `SKILL.md` 位于目录根部。

显式调用：

```text
$vibe-coding-standard
```

支持自动触发的运行环境可在用户要求创建、初始化、脚手架化或重构软件项目时加载本 skill。

常见 coding agent 用法：

- Codex：把本目录放入 skills 目录，或在任务中要求读取 `SKILL.md`。
- Claude Code：把 `SKILL.md` 作为项目规则、自定义命令或任务前置说明使用。
- Kimi：把本目录作为 skill 目录加载，或在对话开始时引用 `SKILL.md`。

## 发布到 GitHub

```bash
git init
git add .
git commit -m "Publish vibe coding standard skill"
git branch -M main
git remote add origin <repo-url>
git push -u origin main
```

当前目录已经可以作为仓库根目录发布。首次发布时只需要添加远程仓库并提交推送。

## 发布到 Skills 平台

将本目录作为包根目录发布。平台需要读取的入口文件是 `SKILL.md`；`templates/` 是可选资源目录。

## License

MIT License. See [LICENSE](LICENSE) for details.
