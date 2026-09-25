# Installing

This repository follows the portable Agent Skills layout.

## Local installation

Copy the repository directory into the skills directory used by your agent, preserving the folder name:

    existing-project-refactoring/
    └── SKILL.md

The folder name and the name field in SKILL.md must both be existing-project-refactoring.

## Use

Invoke the skill explicitly when supported:

    $existing-project-refactoring

Or describe an established codebase and ask the agent to map current behavior, identify coupling, and plan a staged refactoring before editing code.

## Compatibility

The core skill uses only SKILL.md, Markdown references, templates, and standard filesystem paths. It does not require an MCP server, a proprietary SDK, or a specific coding agent.
