# CLAUDE.md

What this repo is, layout, local-only rules: [`README.md`](README.md).
How-to for crawling/chunking: [km-pipeline](https://github.com/lisapaige/km-pipeline)'s
stage READMEs.

## Code Standards

Pre-commit hooks enforce these — write code that passes them on the first try:

- **ruff** — follow ruff linting and formatting rules. No `# noqa` unless genuinely necessary.
- **pyright** — all code must pass strict type checking. Explicit type annotations on function signatures; `X | None` not `Optional[X]`.
- **vulture** — don't leave dead code. If you remove a function's callers, remove the function.
- **No bare exceptions** — never `except:` or `except Exception:` without re-raising or specific recovery.
- **Branch naming** — `feature/`, `bugfix/`, `chore/`, `refactor/`, etc. prefixes (enforced by brack).
