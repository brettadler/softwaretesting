# Using Google Gemini for Software Development

## What Gemini Can Do for You
- **Build features from descriptions**: Describe your feature in plain English. Gemini (via the Gemini Developer API or Vertex AI) generates a plan, writes code, and iterates based on feedback.
- **Debug and fix issues**: Paste a failing test, error message, or stack trace. Gemini analyzes the context and suggests fixes with explanations.
- **Navigate and understand codebases**: Ask questions about specific files or architecture. IDE integrations with VS Code, JetBrains, or Cloud Shell make it context-aware.
- **Automate routine tasks**: Generate tests, refactor code, create documentation, build migration scripts, or draft release notes. Automate these in CI or via the API.

[https://ai.google.dev](https://ai.google.dev)

## Why Developers Love Google Gemini (and Gemini Code Assist)
- **Works in your IDE**: Official support in VS Code, JetBrains, Cloud Shell Editor, Cloud Workstations, Android Studio, and more.
- **Safe, actionable suggestions**: Applies inline diffs, interactive edits, and context-aware code advice. Agent Mode elevates multi-step tasks into collaborative plans.
- **Broad integration and enterprise-ready**: Use via Google AI SDK, Vertex AI, Gemini API, and Firebase. Enterprise features include private model tuning, audit, and Cloud integration.
- **Free for individual use**: Solo developers get access to Gemini Code Assist for free, with generous completions per month (e.g., 180K code completions)

[https://codeassist.google](https://codeassist.google)

["Google Gemini’s AI coding tool is now free for individual users" - The Verge](https://www.theverge.com/news/618839/google-gemini-ai-code-assist-free-individuals-availability)

## Use Gemini Code Assist with Visual Studio Code or Android Studio
Gemini Code Assist integrates into your IDE with chat, code suggestions, reviews, and diffs.
Gemini Code Assist brings the power of Gemini 2.5 to your IDE, with a chat interface that is aware of your code, completes code as you write, and can generation or transformation full functions and files on demand.

- [Setup Gemini Code Assist for Individuals](https://developers.google.com/gemini-code-assist/docs/set-up-gemini)
- [Add Gemini to Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=Google.geminicodeassist)
- [Add Gemini to Android Studio](https://developer.android.com/studio/gemini/overview)

<!-- ## Use Gemini from XXXXXX -->

## Use Gemini from Terminal / Scripts / CLI
Gemini Code Assist gives you access to Gemini CLI, an open source AI agent that brings the power of Gemini directly into your terminal. Gemini CLI provides powerful AI capabilities, from code understanding and file manipulation to command execution and dynamic troubleshooting, offering a fundamental update to your command line experience.

- About Gemini CLI - [https://google-gemini.github.io/gemini-cli/](https://google-gemini.github.io/gemini-cli/)
- Gemini CLI Repo - [https://github.com/google-gemini/gemini-cli](https://github.com/google-gemini/gemini-cli)

## Use Gemini CLI with GitHub Actions
Using Gemini CLI with GitHub Actions is a no-cost, powerful AI coding teammate for your repository. It acts both as an autonomous agent for critical routine coding tasks, and an on-demand collaborator you can quickly delegate work to.

Use it to perform GitHub pull request reviews, triage issues, perform code analysis and modification, and more using Gemini conversationally (e.g., @gemini-cli fix this issue) directly inside your GitHub repositories.

- GitHub Actions - https://github.com/google-github-actions/run-gemini-cli
- [https://blog.google/technology/developers/introducing-gemini-cli-github-actions](https://blog.google/technology/developers/introducing-gemini-cli-github-actions)

## Use Gemini for Code Reviews on GitHub
Bring the power of Gemini directly to GitHub, providing AI-powered code reviews on your pull requests, with automatic pull request summaries, ready-to-commit code suggestions and the ability to invoke Gemini for assistance at any point on the PR.

[https://github.com/marketplace/gemini-code-assist](https://github.com/marketplace/gemini-code-assist)

## Use Gemini Code Assist's Agent Mode
Agent Mode allows project-wide planning, then applies diffs only once you approve them.

Introducting Agent Mode....
- [https://developers.googleblog.com/en/new-in-gemini-code-assist](https://developers.googleblog.com/en/new-in-gemini-code-assist).
- [https://blog.google/technology/developers/gemini-code-assist-updates-july-2025/](https://blog.google/technology/developers/gemini-code-assist-updates-july-2025/)

Also meet Jules, an experimental coding agent that helps you fix bugs, add documentation, and build new features.

- [https://jules.google.com/task](https://jules.google.com/task)
- [https://jules.google/docs](https://jules.google/docs)

## Create `GEMINI.md`
Gemini CLI uses a file named `GEMINI.md` by default for project-level customization. This functions similarly to Claude’s `claude.md` and GitHub Copilot's `copilot-instructions.md`, allowing you to embed system instructions, style guides, workflows, and project context that Gemini will automatically incorporate.

You can place multiple `GEMINI.md` files in your repo (e.g., root, subfolders) for granular control—ideal for monorepos or multi-component projects.

### Template for `GEMINI.md`
```md
## Commands
- `npm run dev` – start dev server
- `npm run build` – compile for production
- `npm run lint` – run linter
- `npm run format` – run Prettier
- `npm run test` – run tests in watch mode
```

### Template for `GEMINI.md`
```md
# Bash commands
- npm run build: Builds the project
- npm run typecheck: Runs typechecker

# Code style
- Use ES modules (`import/export`)
- Destructure imports: `import { foo } from 'bar'`

# Workflow
- Typecheck after each change
- Run targeted tests locally—not full suite
```

### Template for `GEMINI.md`
```md
# Gemini Project Config

## Project Overview
**Name**: TaskFlow – Personal Productivity App
**Stack**: React, TypeScript, Node.js, PostgreSQL
**Goal**: Team collaboration task manager

## Architecture & Standards
- TypeScript across the stack; avoid `any`
- React functional components with hooks and custom hooks
- Server state via React Query, client via Zustand
- REST endpoints under `/api/v1/*` with consistent error formats
- Prisma ORM; snake_case columns; UUID primary keys; `created_at`, `updated_at` timestamps
```

## Testing Workflow with Gemini (TDD)
- Ask Gemini to write tests (no implementation).
- Run tests to confirm they fail.
- Request code to make tests pass, preserving tests.
- Iterate. Ask Gemini for edge case checks.
- Once green, ask for commit messages and changelog summary.
