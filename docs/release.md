# Release and Tagging Guide

This document expands the tagging policy for teams that want a consistent,
auditable release process.

## Goals

- Identify released artifacts and support rollback.
- Keep version history and release notes consistent.
- Prevent tag rewrites that break traceability.

## Versioning

- Use Semantic Versioning: `vMAJOR.MINOR.PATCH` (example: `v1.2.3`).
- Bump MAJOR for breaking changes, MINOR for new features, PATCH for fixes.

## Tag Types

- Release: `vX.Y.Z`
- Release candidate (optional): `vX.Y.Z-rc.N`

## When to Tag

- Tag only release-ready commits on the primary release branch.
- Do not move or rewrite tags after creation.

## Tag Creation

- Prefer signed tags when possible (GPG or Sigstore).
- Limit tag creation to release owners if your platform supports it.

Example (unsigned):

```
git tag v1.2.3
git push origin v1.2.3
```

Example (signed):

```
git tag -s v1.2.3 -m "Release v1.2.3"
git push origin v1.2.3
```

## Release Notes

- Link tags to release notes (for example, GitHub Releases).
- Summarize changes by type: Breaking / Feature / Fix.

## Tag Message Source

- Use Git local history only when creating tag messages.
- Collect commit messages since the previous tag and summarize them.
- Do not require PR metadata or external APIs.

## Rollback

- If a tag is incorrect, delete it and create a new tag with a new version.
- Avoid reusing the same tag name to preserve auditability.
