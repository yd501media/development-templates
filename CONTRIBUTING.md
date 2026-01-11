# Contributing

Thank you for your interest in contributing. This document describes the expected
workflow, standards, and checks for this repository.

## Scope and Intent
- Only implement changes explicitly described in issues, PRs, or instructions.
- Avoid speculative features, optimizations, or requirement changes.

## Workflow
1. Create a feature branch; direct commits to `main` are prohibited.
2. Implement changes with review-ready quality.
3. Open a Pull Request and follow the PR template for required sections.

## Coding Standards
- Follow existing architecture and conventions.
- Keep functions small, readable, and single-purpose.
- Separate business logic from infrastructure and avoid cross-layer shortcuts.

## Linting and Formatting
- Use repository lint/format configs as the source of truth.
- Ensure all lint/format checks pass before requesting review.

## Development Environment (TBD)
Replace this section with required tools and versions once the stack is decided.

## Local Development Commands (TBD)
Replace this section with the expected local run commands (e.g., `make`, `npm`, `go`).

## Test Commands (TBD)
Replace this section with the standard test commands for the project.

## Code Style Examples (TBD)
Replace this section with concrete style/formatting examples once established.

## Testing
- Add or update tests for behavior changes.
- Bug fixes require regression tests.
- If testing is not possible, explain why and how you verified the change.

## Pull Requests
- One logical change per PR; avoid mixing refactors with behavior changes.
- Include motivation, design decisions, impact, verification, and rollback plan.
- PRs are required for all changes, including documentation and tooling updates.
- Disclose AI assistance when used.

## Commit Messages
- Use Conventional Commits (e.g., `feat: add feature`, `fix: correct bug`).
- Keep commits focused on a single intent.

## Local Git Hooks
This repository includes optional local Git hooks under `.githooks`.
To enable them:

```
git config core.hooksPath .githooks
```

Enabled hooks enforce:
- No direct commits/pushes to `main`
- Conventional Commits format
- Guardrails for large files, secrets, and build outputs
- Minimal lint/test runs before push when available

## Security
- Never log secrets, credentials, tokens, or personal data.
- Validate external inputs and keep existing security checks intact.
- For reporting vulnerabilities, see `.github/SECURITY.md`.

## Questions
If anything is unclear, ask for clarification before proceeding.
