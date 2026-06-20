# Contributing

Thanks for your interest in improving **Open Source Project Polish**! This project is an agent skill, so most contributions are edits to a single Markdown file: [`SKILL.md`](SKILL.md).

## Ways to contribute

- **Improve the procedure** — clearer steps, better boundaries, new edge cases.
- **Refine triggering** — tweak the `description` so the skill activates on the right intents (and not the wrong ones).
- **Docs** — fix typos, clarify usage, improve the README pair.
- **Report issues** — see [SUPPORT.md](SUPPORT.md) for where to ask questions.

## Project layout

```text
open-source-project-polish/
├── SKILL.md          # the skill itself (procedure + frontmatter) — the "source"
├── README.md         # English docs
├── README.zh-CN.md   # Chinese docs
└── ...               # community & metadata files
```

## Editing the skill

`SKILL.md` has two parts:

1. **Frontmatter** (`name`, `description`, `argument-hint`) — keep `description` action-oriented and packed with realistic trigger phrases. This is what an agent matches against.
2. **Body** — the goal, hard boundaries, inputs to clarify, and the step-by-step procedure.

Guidelines:

- Keep the **Hard Boundaries** section authoritative; the skill's value is that it never touches source code.
- Prefer **incremental** instructions over rewrites; many agents will read this verbatim.
- Avoid machine-specific paths and untruthful claims in examples.

## Pull requests

1. Fork and create a topic branch (e.g. `improve-secrets-check`).
2. Make focused changes with a clear commit message.
3. Open a PR describing **what** changed and **why**; reference any related issue.
4. Be ready to iterate in review.

There is no build step or test suite. If you change triggering behavior, please describe in the PR how you validated it (example prompts that should and should not activate the skill).

## Code of Conduct

By participating you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md).
