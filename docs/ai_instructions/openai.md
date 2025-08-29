# Using OpenAI for Software Development

[https://openai.com/index/introducing-codex](https://openai.com/index/introducing-codex)

[https://chatgpt.com/codex](https://chatgpt.com/codex)

[https://openai.com/codex/](https://openai.com/codex/)

## Use ChatGPT directly to...
- draft components
- explain code
- refactor
- write tests
- create API stubs
- generate docs/ADR templates
- write CI YAML
- produce sample data.

## Use OpenAI Codex in Visual Studio Code
Codex is OpenAI’s coding agent, capable of reading, modifying, and running code. It helps you build faster, squash bugs, and understand unfamiliar code. With the Codex VS Code extension you can use Codex side-by-side in your IDE, or delegate tasks to the cloud.

Add Codex as a panel in VS Code to chat, edit, and preview changes seamlessly. With context from opened files and selected code, you can write shorter prompts and get faster, more relevant results.

[https://developers.openai.com/codex/ide](https://developers.openai.com/codex/ide)

## Use OpenAI Codex in your Terminal
OpenAI Codex CLI is an coding agent that can read, modify, and run code on your local machine to help you build features faster, squash bugs, and understand unfamiliar code. It’s open source, and rapidly improving at the openai/codex repo in GitHub.

Codex runs in an interactive terminal UI. You can ask Codex to do anything, and it will read your codebase, make edits and run commands. It’s easy to guide Codex as it works with prompts, including image inputs.

[https://developers.openai.com/codex/cli](https://developers.openai.com/codex/cli)

## Use OpenAI Codex for Code Reviews on GitHub
* Codex can review code directly within GitHub. This is great for finding bugs and improving code quality.
* After you have enabled Code on your repository, you can start using it by tagging `@codex` or `@codex review` in a comment on a pull request.
* Bring your standards: Add a repo instructions file at AGENTS.md so Codex’s review follows your style, security, and testing rules.
* Keep a human in the loop: Treat Codex as a powerful first pass—validate its comments and changes for correctness, security, and maintainability.

[https://developers.openai.com/codex/cloud/code-review](https://developers.openai.com/codex/cloud/code-review)

## Create AGENTS.md
Create an AGENTS.md file to inform Codex how to navigate your codebase, which commands to run for testing, and how best to adhere to your project's standard practices. Like human developers, Codex agents perform best when provided with configured dev environments, reliable testing setups, and clear documentation.

### Template for AGENTS.md

```md
# AGENTS.md

## How to run things
- Install: `pip install -e .`
- Tests: `pytest -q`
- Lint/format: `ruff check . && black .`

## Style & conventions
- Use type hints and docstrings.
- Follow our module layout in `/src/app/`.

## PR message
- Start with a one-line summary.
- Include “Test plan” and “Risk” sections.
```
