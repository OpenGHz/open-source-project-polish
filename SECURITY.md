# Security Policy

## Supported Versions

This project is a single self-contained skill distributed from the `main`
branch. Security-relevant fixes are applied to the latest version.

| Version | Supported |
| ------- | --------- |
| latest (`main`) | ✅ |

## What counts as a security issue

Because this skill instructs an agent to perform Git/GitHub actions and write
files, the most relevant concerns are:

- Guidance that could cause an agent to **leak secrets** (e.g. committing `.env`,
  tokens, or private data) during the publish step.
- Guidance that could expose **machine-specific local paths** or private notes in
  public documentation.
- Instructions that could lead to pushing to an unintended remote.

If you find a way the skill's procedure could cause any of the above, please
report it.

## Reporting a Vulnerability

Please report vulnerabilities privately rather than opening a public issue:

- Use GitHub's **"Report a vulnerability"** (Security Advisories) on the
  repository, **or**
- Open a minimal issue asking for a private contact channel without disclosing
  details.

Please include a description, the affected section of `SKILL.md`, and a
reproduction or scenario. We aim to acknowledge reports within a few days and
will coordinate a fix and disclosure timeline with you.
