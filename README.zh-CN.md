[English](README.md) | 简体中文

# Open Source Project Polish（开源项目润色）

> 一个 AI 智能体技能（skill），把任意项目文件夹变成可直接发布的高质量开源仓库——**且不改动你的源代码**。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Skill](https://img.shields.io/badge/type-agent%20skill-blue.svg)](SKILL.md)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

## 它能做什么

`open-source-project-polish` 是一个面向 AI 编码智能体（Claude Code 及兼容框架）的[技能](SKILL.md)。把它指向一个项目文件夹，它会**只**新增和完善面向项目的元数据与文档，让仓库达到开源标准：

- 清晰、美观的 **README**（可选英文/中文双语版本）。
- 社区健康文件：**LICENSE**（默认 MIT）、`CONTRIBUTING`、`CODE_OF_CONDUCT`、`SECURITY`、`SUPPORT`、`CHANGELOG`、`CITATION`。
- GitHub 脚手架：issue/PR 模板、徽章、`.gitignore`、`.gitattributes`、`.editorconfig`。
- **Git/GitHub 配置**：缺失时初始化 git、执行密钥检查、创建公开远程仓库，并推送「仅文档」改动。

它刻意保持保守：只润色项目的「外在」，「内在」保持你写的样子。

## 它不会做什么

- 修改产品/源代码、测试、notebook、资源文件或运行时行为（除非你明确要求）。
- 把机器本地路径（例如 `/home/<user>/...`）泄漏进公开文档。
- 编造发布历史、虚构命令或不真实的徽章。
- 在密钥/隐私数据检查未通过时推送到远程。

完整约束见 [SKILL.md](SKILL.md#hard-boundaries)。

## 安装

该技能是一个自包含的文件夹（`SKILL.md`）。把它安装到你的智能体技能目录即可。

**方式 A —— `npx skills`（推荐）：**

```bash
npx skills add OpenGHz/open-source-project-polish
```

**方式 B —— 手动：**

```bash
# 克隆后，把技能文件夹复制到你的技能目录
git clone https://github.com/OpenGHz/open-source-project-polish.git
cp -r open-source-project-polish "$HOME/.claude/skills/open-source-project-polish"
```

不同框架的技能目录可能不同（例如 `~/.claude/skills/`）。放置时确保智能体能发现 `SKILL.md`。

## 使用

安装后，用自然语言描述目标即可。该技能会在如下意图时触发：

- 「让这个项目可以开源」
- 「润色 README，加上 LICENSE / CONTRIBUTING / CODE_OF_CONDUCT」
- 「准备把这个仓库公开发布」
- 「为这个文件夹创建一个公开的 GitHub 仓库」

你还可以选择性地传入**项目文件夹路径**以及 **GitHub `owner/repo` 覆盖值**。

### 示例

```text
你：把 ./my-cli 整理成可开源的，并以 acme/my-cli 发布
智能体：
  1. 审计文件夹、git 状态与密钥风险
  2. 规划文档/元数据新增项（不改源代码）
  3. 写 README（+ 可选 README.zh-CN）、LICENSE、社区文件
  4. 初始化 git、做密钥检查、创建公开远程、推送
  5. 报告改了什么、以及刻意保持不动的内容
```

## 工作原理

完整流程见 [SKILL.md](SKILL.md)。简要来说：

1. **审计** —— 文件夹结构、现有文档、git/远程状态、密钥风险。
2. **规划** —— 仅新增非代码内容。
3. **README** —— 简洁、真实、可复制粘贴；可选中文镜像。
4. **社区文件** —— license、contributing、conduct、security、changelog、support。
5. **仓库整洁** —— ignore/attributes/editorconfig、模板。
6. **Git 与远程** —— 初始化、密钥检查、公开仓库、推送。
7. **质量检查** —— 无本地路径、链接可达、源代码未动。

## 贡献

欢迎提 issue 和 PR —— 见 [CONTRIBUTING.md](CONTRIBUTING.md) 与[行为准则](CODE_OF_CONDUCT.md)。因为本项目本身**就是**一个润色开源项目的技能，所以它努力践行自己的建议。

## 许可证

[MIT](LICENSE) © OpenGHz
