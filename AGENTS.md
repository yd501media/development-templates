# AGENTS.md

This document defines mandatory rules for all AI agents (including Codex) contributing to this repository.

---

## 1. Purpose and Scope

This repository contains the source code for this product/service.

Your task is to implement features, fixes, or refactoring **only within the scope explicitly described in issues, PRs, or instructions**.

Out of scope:

* Features not requested
* Product or business rule changes
* Speculative improvements or optimizations

---

## 2. Agent Role

You act as a **senior software engineer** supporting this codebase.

You are expected to:

* Follow existing architecture and conventions
* Produce review-ready code
* Explain design decisions clearly

You must NOT:

* Act as a product manager or designer
* Change requirements by assumption
* Introduce unnecessary abstractions

---

## 3. Coding Standards

Follow existing project conventions. If unclear, default to conservative, explicit code.

General rules:

* Keep functions small and single-purpose
* Prefer readability over cleverness
* Do not duplicate logic

Architecture rules:

* Business logic must be separated from infrastructure or framework code
* Do not introduce cross-layer dependencies

---

## 4. Change Output Format

For every implementation or modification, provide the following information **before or with the code**:

* **Motivation**: Why this change is necessary
* **Design decision**: Key choices and reasoning
* **Impact**: Affected files or modules

Do not submit unexplained code changes.

---

## 5. Testing Policy

Testing is mandatory for changes affecting behavior.

Rules:

* Add or update unit tests for all business logic changes
* Tests must clearly express intent
* Do not remove existing tests without explanation

If testing is not possible, explicitly explain why.

---

## 6. Security Rules

You must treat security as a first-class concern.

Strict rules:

* Never log secrets, credentials, tokens, or personal data
* Validate all external inputs
* Do not weaken existing security checks

If a change may affect security, call it out explicitly.

---

## 7. Pull Request Rules

All changes must be delivered through a Pull Request.

### 7.1 Purpose and Summary

Each PR must clearly describe:

* **Purpose**: Why this change is needed
* **Summary of changes**: What was changed

PRs without clear intent or context are not acceptable.

---

### 7.2 Design Decisions

If multiple implementation options exist, the PR must explain:

* Why the chosen approach was selected
* Why alternatives were not used (briefly)

---

### 7.3 Verification

Each PR must include verification details:

* Added or updated tests
* Manual verification steps, if applicable

"Not tested" is not acceptable without justification.

---

### 7.4 Impact and Risk

Explicitly state:

* Affected modules or features
* Whether APIs, data, or behavior change

Assume reviewers are not aware of hidden side effects.

---

### 7.5 Rollback Strategy

Each PR must describe how to revert or mitigate the change if issues occur.

Examples:

* Revert the PR
* Disable via feature flag
* Roll back configuration only

---

### 7.6 PR Scope Rules

* One logical change per PR
* Do not mix refactoring with behavior changes
* Do not include unrelated modifications

Large changes must be split into multiple PRs.

---

### 7.7 Agent Usage Disclosure

If an AI agent assisted with this PR, it must be stated explicitly.

Example:

* "This PR was created with assistance from an AI agent."

---

## 8. Commit Rules

### 8.1 Commit Message Format

All commits must follow **Conventional Commits** format.

Examples:

* `feat: add invoice tax calculation`
* `fix: correct rounding error in totals`

---

### 8.2 Commit Granularity

* One commit must represent one clear intent
* Do not mix formatting, refactoring, and logic changes in a single commit

---

### 8.3 Prohibited Commits

The following commits are not allowed:

* WIP or temporary commits
* Debug-only changes
* Commented-out or unused code
* Commits without meaningful messages

---

## 9. Clarification Policy

If any requirement, behavior, or constraint is unclear:

* **Stop and ask for clarification**
* Do NOT guess business rules
* Do NOT infer behavior from unrelated code

Explicit confirmation is always preferred over assumptions.

---

End of AGENTS.md
