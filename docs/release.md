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

- Use signed tags (GPG).
- Install GPG with Homebrew on macOS:

```
brew install gpg
```

Note: this command is macOS-specific. On Linux/Windows, install GPG using your OS package manager or the official releases.
- Limit tag creation to release owners if your platform supports it.

Example (signed with multi-line message):

```
git tag -s v1.1.1 -m "Release v1.1.1" -m "" \
  -m "Fix" \
  -m "- resolve validation error in checkout flow" \
  -m "- correct rounding in totals" \
  -m "- align client and server error messages" \
  -m "" \
  -m "Docs" \
  -m "- add release and tagging guide" \
  -m "" \
  -m "Chore" \
  -m "- update lint rules" \
  -m "- tighten type guards" \
  -m "- clean unused assets" \
  -m "" \
  -m "Dependencies/CI" \
  -m "- bump actions/setup-node to v4" \
  -m "- bump actions/checkout to v4" \
  -m "- bump actions/upload-artifact to v4" \
  -m "- update eslint and related plugins"
git push origin v1.2.3
```

## Release Notes

- Link tags to release notes (for example, GitHub Releases).
- Summarize changes by type: Breaking / Feature / Fix.

## Tag Message Source

- Use Git local history only when creating tag messages.
- Start the tag message with "Release vX.Y.Z".
- Append multi-line entries after the title to summarize changes.
- Do not require PR metadata or external APIs.

## Rollback

- If a tag is incorrect, delete it and create a new tag with a new version.
- Avoid reusing the same tag name to preserve auditability.
