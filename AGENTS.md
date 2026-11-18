## Project Context

This repository contains Markdown AI Assistant, a browser-based Markdown editor with an integrated AI writing assistant.

Read `docs/DEVELOPMENT.md` before making changes.

It is the canonical source of project requirements, architecture, convetions and approved technical decisions.

## Development Guidelines

- Follow the approved architecture and project scope.
- Work incrementally.
- Prefer simple an mantainable solutions.
- Avoid unnecessary dependencies and abstractions.
- Keep responsibilities clearly separated.
- Use meaningful TypeScript types.
- Validate external data.
- Handle errors and asynchronous states.
- Never expose or commit secrets.
- Test critical functionality.
- Do not silently change approved acrhitectural decisions.

## Product Rules

- The user owns the document.
- AI suggestions must never be applied automatically.
- Proposed changes must be visible and reviewable.
- Users must be able to accept, reject and refine suggestions.
- Stale suggestions must not overwrite newer document changes.

## Git Workflow

- Keep `main` stable.
- Use feature branches for significant milestones.
- Prefer small, logical commits.
- Review changes before committing.
- Run relevant tests.
- Do not commit secrets.
- Do not merge or push without explicit approval.

## Documentation

- Keep `README.md` accurate and synchronized with the implementation.
- Keep `docs/DEVELOPMENT.md` updated when approved requirements or architecture change.

## Reporting

At the end of each task, report: 

- What changed.
- Files created or modified.
- Tests performed and actual results.
- Known limitations.
- Git status and suggested next steps.