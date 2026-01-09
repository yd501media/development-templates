# Decisions

This document records decisions made during the initial setup of AGENTS.md.

## Testing Policy

- Unit tests are required for all business logic changes.
- Integration tests are required when changes affect external dependencies or system boundaries.
- E2E tests are required only for critical paths.
- Bug fixes must include regression tests.

## Lint/Format Policy

- JavaScript/TypeScript: ESLint + Prettier
- Python: Black + Flake8
- Go: gofmt + golangci-lint
- Linting and formatting are mandatory for all code changes.

## Review Scope by Change Size

- Change size is determined by impact and risk, not only file/line count.
- Small: 1–2 files, localized change, no external I/O or data model change, no new behavior.
- Medium: 3–10 files, logic changes, impacts multiple features or flows.
- Large: 10+ files, new feature, API/data model changes, or design/architecture changes.
- Escalate size by one level if the change touches critical domains, external dependencies, or backward compatibility.

## Architecture Boundaries

- Layers: Interface/API, Application, Domain, Infrastructure.
- Dependencies flow inward only.
- Domain must not depend on Infrastructure, frameworks, or external services.

## Dependency Review Criteria

- Necessity, maintenance, security, impact, compatibility, rollback.

## Exception Handling

- Exceptions require explicit documentation of reason, scope/impact, alternative verification, approver, and expiration.
- Exceptions must be documented in the PR description (and linked issue if applicable).
