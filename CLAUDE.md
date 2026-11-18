## Project Overview

Markdown AI assistant is a browser-based Markdown editor with an integrated AI writing assistant.

The project is being developed as part of the Chiri Engineering Assessment.

The product allows users to write Markdown documents and collaborate with AI to improve, rewrite and restructure content through reviewable suggestions.

The user always keeps full control of the document.

## Project Instructions

Before making changes, read:

- `docs/DEVELOPMENT.md`
- `README.md`

`docs/DEVELOPMENT.md` is the canonical source of project requirements, architecture principles, conventions and approved technical decisions.

Do not assume that proposed technical decisions are automatically approved.

## Preferred Technology Stack

The initial preferred stack is:

- Angular
- Typescript
- Angular Standalone Components
- Angular Signals
- RxJs
- CodeMirror 6
- Node.js
- Express
- OpenRouter API
- Zod
- SCSS

Review the approved architecture before introducing dependencies or making significant implementation decisions.

## Engineering Principles

- Prefer simple, maintainable solutions.
- Avoid unnecessary abstractions and dependencies.
- Keep responsibilities clearly separated.
- Use explicit and meaningful TypeScript types.
- Validate external data.
- Handle loading, error and empty states.
- Keep API credentials and secrets out of the frontend and repository.
- Write tests for critical business logic.
- Avoid implementing features outside the agreed scope.
- Prefer understandable code over clever or unnecessarily complex solutions.

## Core Product Rules

- The user owns the document.
- AI suggestions must never be applied automatically.
- All proposed changes must be visible and reviewable.
- Users must be able to accept, reject and refine suggestions.
- Suggestions must not overwrite newer document changes.
- The application, not the AI model, controls document state and suggestion approval.

## Git and Version Control

- Keep `main` stable and functional.
- Use feature branches for significant milestones or independent features.
- Prefer smaller logical commits over large milestone-wide commits.
- Use Conventional Commit messages.
- Inspect Git status and changes before committing.
- Run relevant tests before committing whenever practical.
- Never commit secrets, API keys, credentials or local environment files.
- Never rewrite shared history or force-push without explicit approval.
- Never merge branches or push to remote repositories without explicit approval.
- Do not create unnecessary branches for trivial changes.
- Do not commit unrelated or unreviewed changes.

Before creating a commit:

1. Inspect the modified files.
2. Review the Git diff.
3. Check for secrets and unintended files.
4. Run relevant tests.
5. Suggest an appropriate commit message.

Wait for explicit approval before creating commits.

At the end of each milestone, report:

- Current branch.
- Changes implemented.
- Commits created.
- Tests and actual results.
- Known limitations.
- Suggested next steps.

## Documentation Requirements

### README.md

Keep the root README.md accurate throughout development.

It is a mandatory assessment deliverable and must explain:

1. What was built.
2. How to install and run the application.
3. What would be done differently with more development time.

Include actual, verified commands, environment variables, implemented features and known limitations.

Never invent functionality, test results or setup instructions.

Clearly distinguish implemented features from planned improvements.

Review the README against the actual application before delivery.

### DEVELOPMENT.md

Keep `docs/DEVELOPMENT.md` synchronized with approved project requirements, architecture and engineering conventions.

Do not silently change approved decisions.

## Working Agreement

Work incrementally, one milestone at a time.

Before significant implementation:

1. Understand the task and acceptance criteria.
2. Explain the proposed technical approach.
3. Identify important alternatives and trade-offs.
4. Check consistency with approved architecture.
5. Ask for approval when architectural decisions are involved.

At the end of each milestone:

- Summarize what was implemented.
- Report tests and their actual results.
- Identify known limitations.
- Update relevant repository documentation.
- Report Git changes and suggested commits.
- Recommend the next step.

Do not silently change approved requirements, scope or architecture.

Do not implement an entire milestone without intermediate verification when it contains multiple independent technical tasks.