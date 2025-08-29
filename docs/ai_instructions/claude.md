# Instructions for Claude

## Using Claude for software development

- Ask Claude to write tests based on expected input/output pairs. Be explicit about the fact that you’re doing test-driven development so that it avoids creating mock implementations, even for functionality that doesn’t exist yet in the codebase.
- Tell Claude to run the tests and confirm they fail. Explicitly telling it not to write any implementation code at this stage is often helpful.
- Ask Claude to commit the tests when you’re satisfied with them.
- Ask Claude to write code that passes the tests, instructing it not to modify the tests. Tell Claude to keep going until all tests pass. It will usually take a few iterations for Claude to write code, run the tests, adjust the code, and run the tests again.
- At this stage, it can help to ask it to verify with independent subagents that the implementation isn’t overfitting to the tests
- Ask Claude to commit the code once you’re satisfied with the changes.
- Claude performs best when it has a clear target to iterate against—a visual mock, a test case, or another kind of output. By providing expected outputs like tests, Claude can make changes, evaluate results, and incrementally improve until it succeeds.

[https://www.anthropic.com/claude-code](https://www.anthropic.com/claude-code)

[https://www.anthropic.com/engineering/claude-code-best-practices](https://www.anthropic.com/engineering/claude-code-best-practices)

## Create CLAUDE.md

CLAUDE.md is a special file that Claude automatically pulls into context when starting a conversation. This makes it an ideal place for documenting:

* Common bash commands
* Core files and utility functions
* Code style guidelines
* Testing instructions
* Repository etiquette (e.g., branch naming, merge vs. rebase, etc.)
* Developer environment setup (e.g., pyenv use, which compilers work)
* Any unexpected behaviors or warnings particular to the project
* Other information you want Claude to remember

### Template for CLAUDE.md
There’s no required format for CLAUDE.md files. They recommend keeping them concise and human-readable. For example:

```md
# Bash commands
- npm run build: Build the project
- npm run typecheck: Run the typechecker

# Code style
- Use ES modules (import/export) syntax, not CommonJS (require)
- Destructure imports when possible (eg. import { foo } from 'bar')

# Workflow
- Be sure to typecheck when you’re done making a series of code changes
- Prefer running single tests, and not the whole test suite, for performance
```
### Sample Claude Instructions File

```md
# Development Guidelines

## Commands
- `npm run dev` - Run development server
- `npm run build` - Build for production (runs tests first)
- `npm run lint` - Run ESLint
- `npm run format` - Format code with Prettier
- `npm run test` - Run Jest tests in watch mode
- `npm test -- -t "test name"` - Run specific test
- `npm run test:build` - Run all tests once (CI mode)
- `npm run cypress` - Run Cypress E2E tests

## Code Style
- **TypeScript**: Use strong typing, avoid `any` when possible
- **Imports**: Group by: 1) React/Next, 2) Components, 3) Utilities, 4) Types
- **Components**: Use functional components with hooks
- **Naming**: PascalCase for components, camelCase for functions/variables
- **Formatting**:
  - Single quotes, tab indentation (width: 2), semicolons
  - Max line length: 100 characters
- **Error Handling**: Use try/catch blocks with proper user feedback (toast)
- **State Management**: Use React hooks, context for global state
- **Tailwind**: Use Tailwind classes for styling

## Architecture
- NextJS for frontend and API routes
- Prisma ORM with MySQL database
- Jest for unit tests, Cypress for E2E tests
```

### Sample Claude Instructions File

```md
# Claude Project Configuration

## Project Overview
**Project Name**: TaskFlow - Personal Productivity App
**Tech Stack**: React, TypeScript, Node.js, PostgreSQL
**Goal**: Build a modern task management application with team collaboration features

## Coding Standards & Preferences

### General Guidelines
- Use TypeScript for all new code
- Follow functional programming patterns when possible
- Prioritize readability and maintainability over cleverness
- Write self-documenting code with clear variable and function names

### Code Style
- Use ESLint and Prettier configurations from `.eslintrc.js` and `.prettierrc`
- Prefer `const` over `let`, avoid `var`
- Use arrow functions for inline callbacks
- Maximum line length: 100 characters
- Use trailing commas in multi-line objects and arrays

### React Patterns
- Use functional components with hooks (no class components)
- Prefer custom hooks for complex state logic
- Use React Query for API state management
- Component naming: PascalCase for components, camelCase for functions
- Keep components small and focused (< 200 lines when possible)

## Architecture Decisions

### State Management
- React Query for server state
- Zustand for client-side global state
- Local component state for UI-only state

### API Design
- RESTful endpoints following `/api/v1/resource` pattern
- Use HTTP status codes correctly
- Return consistent error response format
- Include request IDs for debugging

### Database
- Use Prisma ORM for database operations
- Follow `snake_case` for database columns
- Always include `created_at` and `updated_at` timestamps
- Use UUIDs for primary keys

## Claude Instructions

### When Writing Code
1. **Always include error handling**: Use try-catch blocks and proper error boundaries
2. **Add TypeScript types**: Define interfaces for all data structures
3. **Include comments**: Explain complex business logic and non-obvious implementations
4. **Consider accessibility**: Add ARIA labels and semantic HTML
5. **Write tests**: Include unit tests for utilities and integration tests for components

### Code Review Focus Areas
- Security vulnerabilities (SQL injection, XSS, etc.)
- Performance implications
- Code maintainability and readability
- Consistency with existing patterns
- Error handling completeness

### Documentation Preferences
- Use JSDoc comments for public functions
- Include usage examples in complex utilities
- Document API endpoints with request/response examples
- Keep README files up-to-date with setup instructions

## Project Context

### Current Phase
# We are in the MVP development phase, focusing on core task management features:
- User authentication and profiles
- Task creation, editing, and deletion
- Basic team collaboration
- Simple project organization

### Known Technical Debt
- Need to refactor user authentication to use NextAuth.js
- Database queries need optimization (N+1 query issues)
- Frontend bundle size is larger than desired
- Missing comprehensive error logging

### Recent Decisions
- Switched from Redux to Zustand for simpler state management
- Adopted React Query to reduce boilerplate API code
- Decided to use Tailwind CSS for styling consistency
- Implementing dark mode support across all components

## Environment Setup

### Required Tools
- Node.js 18+
- PostgreSQL 14+
- Docker (for local development database)
- VS Code with recommended extensions

### Getting Started

# Clone and setup
git clone [repo-url]
cd taskflow
npm install

# Database setup
docker-compose up -d postgres
npm run db:migrate
npm run db:seed

# Development server
npm run dev
```
