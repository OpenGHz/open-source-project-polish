# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Changed

- `SKILL.md`: when `gh` is authenticated, the workflow now configures GitHub
  repository features by default — sets description/homepage/topics and enables
  Discussions (via `gh api ... -F has_discussions=true`) so the generated
  `SUPPORT.md` Discussions link resolves. Applies whether the remote was just
  created or already existed; falls back to listing manual commands when `gh`
  is unavailable.

## [0.1.0] - 2026-06-20

### Added

- Open source baseline: README (English + 简体中文), MIT LICENSE, contributing
  guide, code of conduct, security policy, support guide, issue/PR templates,
  and repository hygiene files (`.gitignore`, `.gitattributes`, `.editorconfig`).

### Changed

- `SKILL.md`: the bilingual README step now authors the Chinese mirror directly
  by default and treats the `baoyu-translate` skill as optional — reserved for
  long or terminology-dense docs — instead of mandating it for every README.
