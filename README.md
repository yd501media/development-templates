# development-templates

## Template Setup

When creating a new repository from this template, enable GitHub's Dependency graph
in repository settings so the security workflow can run dependency review checks.

Replace the CODEOWNERS placeholder with actual GitHub users or teams so review
assignment works as expected.

If you use ecosystems beyond npm, add them to `.github/dependabot.yml` so updates
are tracked.

## Git Hooks

Enable local Git hooks so direct commits/pushes to `main` are blocked and changes
flow through PRs:

```
git config core.hooksPath .githooks
```

This template ships with local Git hooks for:
- blocking commits to `main`
- blocking direct pushes to `main`
- enforcing Conventional Commits
- preventing accidental commits of dependencies/build outputs and large files
- running minimal lint/test checks before push when available

The pre-commit hook requires gitleaks. Install it with:

```
brew install gitleaks
```

Note: this command is macOS-specific. On Linux/Windows, install gitleaks using your OS package manager or the official releases.

## Tagging Policy

This template recommends a minimal, general-purpose tagging policy that works
across project types.

For more detail, see `docs/release.md`.

### Purpose

- Identify release artifacts and make rollbacks easy.
- Keep release notes and version history consistent.

### Naming

- Release tags use SemVer: `vX.Y.Z` (example: `v1.2.3`).
- Release candidates (optional): `vX.Y.Z-rc.N`.

### When to Tag

- Tag only release-ready commits on the primary release branch.
- Do not move tags once created.

### Signing and Permissions

- Prefer signed tags (GPG or Sigstore) when possible.
- Limit tag creation to release owners if your platform supports it.

### Release Notes

- Link tags to release notes (e.g., GitHub Releases).
- Describe changes by type (Breaking/Feature/Fix).

### Rollback

- If a tag is incorrect, delete it and create a new tag.
- Avoid retagging the same name to preserve auditability.

## AI Agent Guidance

This repository uses `AGENTS.md` as the source of truth for AI agent behavior,
scope, and constraints. If you use an AI agent to assist with changes, ensure
it follows the rules in `AGENTS.md` and disclose AI assistance in the PR.
