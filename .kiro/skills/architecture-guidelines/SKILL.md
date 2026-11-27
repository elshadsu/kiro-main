---
name: "architecture-guidelines"
description: "Review Python code against the team's accepted architecture decisions."
---

# Architecture Guidelines

## Layered Architecture — ADR-001

- Entrypoints must only parse input and format output.
- Business logic must reside in service modules.
- Entrypoints must not access data directly.

## Configuration Management — ADR-002

- Load configuration and secrets from environment variables or a central configuration module.
- Do not hardcode configuration values, API keys, tokens, or passwords.
- Do not access `os.environ` directly outside the configuration module.

## Repository Pattern — ADR-003

- Services must access data exclusively through repositories.
- Services must not directly import or reference `ApiClient`.
- Services must not directly access HTTP clients, databases, or ORMs.

## Dependency Injection — ADR-004

- Inject dependencies through constructors or function parameters.
- Do not use global singletons or the ServiceLocator pattern.

## Review Requirements

- Report only violations supported by the provided code.
- Cite the corresponding ADR for each architecture finding.
- Do not invent architecture rules.
- If no violations are found, explicitly report that the architecture review passed.