# CLAUDE.md

Data repo for UNC Greensboro: crawl configs, crawl/chunk snapshots, eval data.
No application code. [km-pipeline](https://github.com/lisapaige/km-pipeline)
produces and consumes this layout; its stage READMEs own the how-to.

## Layout

- `data/crawl/config/<subject>/tree.yaml` — tracked; the scope decisions (whitelist SSOT)
- `data/crawl/` and `data/chunks/` run outputs — untracked
- `prompts/` — chunker failcase ledger, prompt vars

Local only: `.env` (workspace API keys).

## Code Standards

Pre-commit hooks enforce these — write code that passes them on the first try:

- **ruff** — follow ruff linting and formatting rules. No `# noqa` unless genuinely necessary.
- **pyright** — all code must pass strict type checking. Explicit type annotations on function signatures; `X | None` not `Optional[X]`.
- **vulture** — don't leave dead code. If you remove a function's callers, remove the function.
- **No bare exceptions** — never `except:` or `except Exception:` without re-raising or specific recovery.
- **Branch naming** — `feature/`, `bugfix/`, `chore/`, `refactor/`, etc. prefixes (enforced by brack).
