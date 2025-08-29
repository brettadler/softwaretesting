# Using GitHub Copilot for Software Development

## Use GitHub Copilot on GitHub.com
* Copilot Chat right in the browser to ask questions about a repo’s code, issues, and PRs.  ￼
* Copilot Code Review can be added as a PR reviewer; it leaves feedback and often proposes ready-to-apply fixes.  ￼
* Copilot Workspace on the web helps plan and prototype larger changes from a prompt (experimental).  ￼ ￼

## Use GitHub Copilot in Visual Studio Code
* Inline completions and Chat panel for explaining code, generating tests, debugging ideas, and more.
* Open Chat from the Copilot menu / shortcut, then reference files or selections for focused help.  ￼

## Use GitHub Copilot with CLI
* Copilot in the CLI (via GitHub CLI) explains commands and suggests CLI or Git/GitHub workflows from your terminal.  ￼
* Install/enable it through the GitHub CLI, then use interactive prompts or one-off queries

## Create copilot-instructions.md

Create a `.github/copilot-instructions.md` file to steer GitHub Copilot's coding behavior. Details can include:

* **Tech stack defaults:** Next.js/React, TypeScript, Tailwind, shadcn/ui, Python (FastAPI/Flask), testing stacks.
* **Code style & conventions:** formatting, lint rules, import order, naming.
* **Testing requirements:** unit first, RTL/Vitest/Jest, pytest; coverage targets per layer; examples of “good” tests.
* **Security & privacy rules:** secrets handling, PII redaction, dependency choices, license constraints.
* **Commit message and PR templates:** structure, checklists, “what to include” in AI-authored PRs.
* **Prompt patterns:** how to ask Copilot/ChatGPT for components, tests, migrations, docs; do/don’t lists; examples.

### Copilot Instructions File Template

```md
# .github/copilot-instructions.md

## Project intent
- This repo is a [brief description: e.g., "FastAPI service + React front end"].
- Priorities (in order): correctness → security → performance → readability.

## How to run & test
- Setup: `uv sync` (or `pip install -e .` / `npm ci` as appropriate)
- Unit tests: `pytest -q` and `npm test --silent`
- Integration tests: `make itests`
- Lint/format: `ruff check . && black .` ; `eslint .` ; `prettier -w .`
- Build: `make build`
- Run dev: `make dev` (starts API on :8000 and web on :5173)
- CI must pass all checks before proposing changes.

## Code style & patterns
- Python: type hints everywhere; prefer `pathlib`, dataclasses/pydantic; no bare `except`.
- JS/TS: prefer functional components + hooks; no default exports; strict TS.
- API: follow OpenAPI schema in `/openapi.yaml`; return structured errors `{code,message}`.
- DB: use migrations in `/migrations`; never raw SQL in handlers.
- Logging: structured (JSON) via helper in `/src/lib/log.ts`.

## Security & quality checklist
- Validate all inputs; sanitize HTML; avoid eval/exec/dangerous shell.
- Add tests for bug fixes and new endpoints; target changed lines ≥ 80% coverage.
- Watch for N+1 queries and unbounded lists; paginate API responses.
- Secrets/config come only from env or `/config/*.yaml` (no secrets in code).

## PR & commit conventions
- Conventional Commits (`feat:`, `fix:`, `docs:`, …).
- PR description includes: Summary, Test Plan, Risk, Rollback.
- Small, focused PRs (< 400 lines changed) preferred.

## Repo layout (monorepo-friendly)
- `/apps/api`, `/apps/web`, `/packages/*` shared libs.
- Cross-package imports via workspace aliases; avoid relative deep imports.

## Preferred libraries
- Python: FastAPI, SQLModel/SQLAlchemy, Pydantic v2, httpx, Ruff, Black, Pytest.
- Web: React 18, Vite, TanStack Query, Zod, ESLint, Prettier, Vitest/RTL.

## Non-goals (avoid)
- Introducing new frameworks without RFC.
- Large refactors mixed with feature work.
- Adding dependencies for trivial tasks.

## Chat & code review guidance
- When reviewing: call out security issues, race conditions, missing tests, perf risks.
- When generating code: include docstrings/JSDoc, minimal examples, and TODOs for follow-ups.
- Prefer incremental diffs with clear rationale in comments.

## Glossary / context cues
- "Service" = API in `/apps/api`; "Portal" = UI in `/apps/web`.
- "Task runner" = `make` targets defined in `Makefile`.
```

### Sample Copilot Instructions File

```md
## Instruction File
* Analyze the tech stack and architecture
* Categorize files by role
* Extract coding patterns and naming conventions
* Document features and domain logic
* Identify the technology stack and major frameworks used
* Mapp out file purposes and categorizing project structure
* Infer architecture and design patterns and document them
* Understand domain concepts and key features
* Generate stylistic and structural guidance for future code contributions

## Overview Section
Explain the purpose of this document:

* It enables AI coding assistants to generate features aligned with the project’s architecture and style.
* It is based on actual, observed patterns from the codebase — not invented practices.

## Feature Scaffold Guide
Define how to plan and implement a new feature. Include:

* How to determine which categories of files to create
* Where to place those files
* How to follow naming and structure conventions
* Example: what files to create for a new component, a hook, or an API integration

This section should refer to actual conventions in the project (e.g., if Storybook is used, include .stories.tsx; if styles are colocated .module.css, mention that).

## Integration Rules
Summarize constraints like:

* "All canvas logic must use useCanvas"
* "Components must use shared tokens from the design-system"
* "API requests go through apiClient.ts pattern"

This prevents LLMs from generating non-compliant or inconsistent files.

## Example Prompt Usage
Show how a user could prompt Copilot with a request like:

> "Create a searchable dropdown that lets users filter by category"

## And have it respond with:
* src/components/SearchableDropdown.tsx
* src/components/SearchableDropdown.module.css
* src/hooks/useSearchableDropdown.ts
* src/components/__tests__/SearchableDropdown.test.tsx
* etc…

Only use categories and file types present in this project.

## Requirements
* Do not include invented best practices
* Do not list categories or conventions that aren’t supported by the codebase
* Do not omit any categories or domains defined in the analysis

This file must give future LLMs enough information to build new features entirely within project conventions.

## More

Tech Stack Analysis:
Determine the type of project and summarize the tech stack. Your summary should include:

* Programming language(s)
* Primary framework
* Any secondary or tertiary frameworks
* State management approach
* Any other relevant technologies or patterns

## File Categorization
Visit every file in the codebase. You may ignore dependency files, for example if it is a js file, you may ignore `node_modules`.

Categorize each file based on its role, such as: react-components, utility-functions, hooks, types, etc.

## Identify User Roles
What type of user roles and interactions does it support?

## Identify Architecture
Determine which architectural domains are present in the project. Consider:
* File structure and naming patterns
* Framework conventions
* Imports and usage patterns
* Configuration files
* Common architectural markers (e.g., components/, routes/, handlers/, services/, cli/, etc.)

## Style
You are a senior software engineer responsible for generating style guides that explain what makes this codebase unique. Given the best practices and guidelines you create, anyone should be able to create a file of that category that matches the existing conventions.

* Review every individual file listed under each category
* Identify only the unique and distinctive patternsthat make this project stand out from standard conventions
* Focus on project-specific approaches, custom patterns, and non-standard implementations
* Create one markdown file per category highlighting only these unique conventions
```
