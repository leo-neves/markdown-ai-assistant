# Development Guide - Markdown AI Assistant

## 1. Project Objective

Build a browser-based Markdown editor with an integrated AI writing assistant.

The application allows users to write and edit Markdown documents while collaborating with AI to improve clarity, tone, structure and wording.

AI-generated modifications must be presented as reviewable suggestions.

The user remains in control of the document at all times.

This project is being developed as part of the Chiri Engineering Assessment.

## 2. Core Requirements

The initial product scope includes:

- Markdown editing.
- Text selection.
- AI assisted editing.
- Document-level improvement requests.
- Visible diffs between original and proposed content.
- Accept and reject actions.
- Iterative suggestion refinement.
- Protection against stale suggestions.
- Clear loading and error states.

The primary workflow is:

1. The user writes or opens a Markdown document.
2. The user selects text or requests a document-level change.
3. The user provides an instruction.
4. The AI generates a proposed modification.
5. The application validates the response.
6. The aplpication displys the proposed changes.
7. The user accepts, rejects or refines the suggestion.

## 3. Initial Technology Stack

The preferred initial stack is:

### Frontend

- Angular.
- TypeScript.
- Angular Standalone Components.
- Angular Signals.
- RxJs.
- CodeMirror 6.
- SCSS.

### Supporting Libraries

- A lightweight text diff library.
- Testing tools comparible with the selected Angular version.

The final dependency selection must be confirmed during architecture design.

Do not introduce additional libraries without a clear technical justification.

## 4. Architecture Principles

### 4.1 Separation of Responsibilities

The application must clearly separate:

- Document state.
- Editor interaction.
- AI communication.
- Suggestion management.
- Diff generation.
- User approval.

The Angular application owns the document state.

The backend handles AI communication, prompt construction and external response validation.

The AI model must never directly modify the document.

### 4.2 Single Source of Truth

Avoid unnecessary duplication of document state.

CodeMirror manages editor interactions and editing transactions, while Angular owns the application-level document state.

The integration must maintain synchronization without recreating the editor on every document change.

### 4.3 Suggestion Lifecycle

An AI suggestion must be independent of the original document state.

The application manages:

- Original content.
- Proposed content.
- Target selection or range.
- Document version.
- Suggestion status.
- Diff generation.
- Accesptance and rejection.

A suggestion must be checked against the document state from which it was generated before being applied.

Stale suggestions must not overwrite newer user changes.

### 4.4 AI Integration

The application communicates with the AI provider through the backend.

API credentials must never be exposed to the frontend.

AI responses must be validated before being used.

The initial implementation should favor non-streaming requests unless architecture review establishesa strong reason otherwise.

The AI integration shoud avoid unnecessary coupling to a specific model.

## 5. Engineering Constraints

The initial implmentation should avoid:

- Authentication.
- Database infrastructure
- Unnecessary cloud infrastructure.
- Multi-user real-time collaboration.
- CRDT or Operational Transformation.
- Multi-agent orchestration.
- Unnecessary state management libraries.
- Complex abstraction layers.
- Features outside the agreed MVP scope.

Prioritize a working, reliable end-to-end workflow over speculative functionality.

## 6. Security and Data Handling

- Keep API keys exclusively on the backend.
- Use environment variables for secrets and configuration.
- Never commit `.env` files.
- Provide `.env.example` without real credentials.
- Validate incoming API requests.
- Validate external AI responses.
- Handle provider errors safely.
- Do not trust model-generated content as validated application state.

## 7. Git and Version Control

### Main Branch

The `main` branch must remain stable and functional.

### Feature Branches

Create feature branches for significant milestones or independent features.

Initial planned branches:

- `feature/project-setup`
- `feature/ai-integration`
- `feature/suggestion-engine`
- `feature/collaborative-ux`
- `feature/testing-delivery`

These branches are a planning proposal, not a requiresment to create every branch regardless of scope.

Small or closely related tasks may share a branch.

### Commits

Use small, logical commits.

Follow Conventional Commits, for example:

- `feat:`
- `fix:`
- `test:`
- `docs:`
- `refactor:`
- `chore:`

Review changes and run relevant tests before committing whenever practical.

### Merges and Remote Operations

Do not merge branches or push to remote repositories without explicit user approval.

Do not force-push or rewrite shared Git history without explicit approval.

At each milestone, report the branch, commits, changed files, test results and remaining work.

## 8. Development Workflow

Work in small, independently verifiable milestones.

For each milestone:

1. Define the expected outcome.
2. Review relevant technical decisions.
3. Agree on the implementation approach.
4. Implement the approved scope.
5. Run relevant tests.
6. Review the resulting changes.
7. Update repository documentation.
8. Review and create logical Git commits after approval.
9. Present results and known limitations.
10. Obtain approval before merging.

Significant architectural decisions must be discussed before implementation.

Do not silently expand project scope.

## 9. Documentation

### README.md

The root README is the primary documentation for reviewers and users.

It must explain:

1. What was built.
2. How to install and run the application.
3. What would be done differently with more development time.

It must contain accurate setup instructions, actual environment variables, implemented features, testing information and known limitations.

Update it throughout development.

### CLAUDE.md

Contains instructions specific to Claude Code.

### AGENTS.md

Contains general instructions for compatible AI development agents.

## 10. Approved Decisions and Open Questions

Only decisions explicitly discussed and approved should be considered final.

The initial technology stack and architecture are starting proposals until reviewed during product discovery and architecture design.

Record significant decisions and unresolved techincal questions in this document as the project evolves.

Distinguish clearly between:

- Proposed 
- Approved.
- Implemented.
- Validated.

Update this guide when approved requirements, architecture or engineering constrints change.