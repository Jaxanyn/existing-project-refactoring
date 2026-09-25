---
name: existing-project-refactoring
description: Analyze an existing codebase and plan behavior-preserving, staged architectural refactoring. Use when a project has oversized modules, unclear boundaries, tangled dependencies, or needs a safe migration without breaking current behavior.
---

# Existing Project Refactoring

Turn an existing codebase into a concrete, reversible refactoring plan before editing implementation files.

## Scope

Use this skill for established projects with current users, data, integrations, or behavior to preserve. Do not treat an existing project as a blank slate. Do not use this workflow for a new project with no implementation history.

## Workflow

1. Read repository rules, README, configuration, design documents, issue history, and current status.
2. Map the current structure: entry points, modules, data flow, external dependencies, build and runtime surfaces.
3. Trace the requested behavior through callers, state, persistence, integrations, and tests or manual checks.
4. Separate business rules, application orchestration, interface adapters, framework code, and rebuildable cache.
5. Record behavior that must remain unchanged, including error handling, data shape, ordering, timing, and fallback behavior.
6. Identify coupling and choose the smallest target boundary that removes it. Use deep modules and seams that support a real migration or test.
7. Define a migration path in independently usable phases. Each phase must name affected files or modules, preserved behavior, verification, and rollback.
8. Define a regression matrix covering happy paths, edge cases, failures, data compatibility, concurrency, and UI or device behavior where relevant.
9. Produce the plan and stop. Do not modify implementation files until the user explicitly approves it.

## Output

Return these sections:

- Current state
- Behavior and data that must remain stable
- Coupling and root causes
- Target architecture
- Migration seams and interfaces
- Phased refactoring plan
- Regression matrix
- Rollback and failure handling
- Risks, assumptions, and open decisions

## Design rules

- Preserve observable behavior unless the user explicitly changes the product requirement.
- Migrate one behavior or seam at a time; keep the project usable after every phase.
- Do not move code only to make files smaller. Move it when ownership, change reason, or dependency direction improves.
- Keep domain rules independent from UI, storage, frameworks, and external SDKs.
- Treat route results, search results, and other rebuildable data differently from durable user data.
- Do not introduce a new framework, runtime, service, or dependency without a measured benefit and rollback plan.
- Use an ADR only for a hard-to-reverse, surprising, real trade-off.

## Optional adapters

For high-risk data or public behavior, add executable specifications before editing. For UI, device, or external-service changes, add targeted visual, runtime, or integration verification after each phase.

## Completion

The skill is complete when another engineer can execute the first migration phase without re-deciding the target boundary, preserved behavior, or verification method.
