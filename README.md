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

This template ships with local githooks for:
- blocking commits to `main`
- blocking direct pushes to `main`
- enforcing Conventional Commits
- preventing accidental commits of dependencies/build outputs and large files
- running minimal lint/test checks before push when available
