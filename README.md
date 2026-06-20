English | [简体中文](README.zh-CN.md)

# Open Source Project Polish

> An agent skill that turns any project folder into a polished, publish-ready open source repository — **without touching your source code**.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Skill](https://img.shields.io/badge/type-agent%20skill-blue.svg)](SKILL.md)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

## What it does

`open-source-project-polish` is a [skill](SKILL.md) for AI coding agents (Claude Code and compatible harnesses). Point it at a project folder and it brings the repository up to open source standards by adding and improving **only** project-facing metadata and documentation:

- A clear, attractive **README** (with an optional bilingual English/Chinese pair).
- Community health files: **LICENSE** (MIT by default), `CONTRIBUTING`, `CODE_OF_CONDUCT`, `SECURITY`, `SUPPORT`, `CHANGELOG`, `CITATION`.
- GitHub scaffolding: issue/PR templates, badges, `.gitignore`, `.gitattributes`, `.editorconfig`.
- **Git/GitHub setup**: initialize git if missing, run a secrets check, create a public remote, and push the documentation-only changes.

It is deliberately conservative: it polishes the *outside* of your project and leaves the *inside* exactly as you wrote it.

## What it will not do

- Modify product/source code, tests, notebooks, assets, or runtime behavior (unless you explicitly ask).
- Leak machine-specific local paths (e.g. `/home/<user>/...`) into public docs.
- Invent release history, fake commands, or untruthful badges.
- Push to a remote when a secrets/private-data check fails.

See the full contract in [SKILL.md](SKILL.md#hard-boundaries).

## Installation

This skill is a single self-contained folder (`SKILL.md`). Install it into your agent's skills directory.

**Option A — `npx skills` (recommended):**

```bash
npx skills add OpenGHz/open-source-project-polish
```

**Option B — manual:**

```bash
# Clone, then copy the skill folder into your skills directory
git clone https://github.com/OpenGHz/open-source-project-polish.git
cp -r open-source-project-polish "$HOME/.claude/skills/open-source-project-polish"
```

Your skills directory may differ by harness (for example `~/.claude/skills/`). Place the folder so that the agent can discover `SKILL.md`.

## Usage

Once installed, just describe the goal in natural language. The skill triggers on intents such as:

- "Make this project open source ready"
- "Polish the README and add a LICENSE / CONTRIBUTING / CODE_OF_CONDUCT"
- "Prepare this repository for public release"
- "Create a public GitHub repo for this folder"

You can optionally pass a **project folder path** and a **GitHub `owner/repo` override**.

### Example

```text
You: Make ./my-cli open source ready and publish it as acme/my-cli
Agent:
  1. Audits the folder, git state, and secrets risk
  2. Plans the docs/metadata additions (no source changes)
  3. Writes README (+ optional README.zh-CN), LICENSE, community files
  4. Inits git, runs a secrets check, creates the public remote, pushes
  5. Reports exactly what changed and what was intentionally left untouched
```

## How it works

The procedure is fully specified in [SKILL.md](SKILL.md). In short:

1. **Audit** — folder structure, existing docs, git/remote state, secrets risk.
2. **Plan** — non-code additions only.
3. **README** — concise, truthful, copy-pastable; optional Chinese mirror.
4. **Community files** — license, contributing, conduct, security, changelog, support.
5. **Repository hygiene** — ignore/attributes/editorconfig, templates.
6. **Git & remote** — init, secrets check, public repo, push.
7. **Quality checks** — no local paths, links resolve, source untouched.

## Contributing

Issues and PRs are welcome — see [CONTRIBUTING.md](CONTRIBUTING.md) and our [Code of Conduct](CODE_OF_CONDUCT.md). Because this project *is* a skill that polishes open source projects, it tries to follow its own advice.

## License

[MIT](LICENSE) © OpenGHz
