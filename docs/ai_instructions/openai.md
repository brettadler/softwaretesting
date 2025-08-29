# Using OpenAI for Software Development

## Use ChatGPT to...
- draft components
- explain code
- refactor
- write tests
- create API stubs
- generate docs/ADR templates
- write CI YAML
- produce sample data.

## Create AGENTS.md
Create a AGENTS.md file to inform Codex how to navigate your codebase, which commands to run for testing, and how best to adhere to your project's standard practices. Like human developers, Codex agents perform best when provided with configured dev environments, reliable testing setups, and clear documentation.

[https://openai.com/index/introducing-codex](https://openai.com/index/introducing-codex)

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
