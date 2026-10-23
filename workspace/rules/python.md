# Python rules

Mandatory for every change in the `service` repository.

- Python 3.13 only; full type hints on every public function and method
  (`from __future__ import annotations` is allowed).
- Pydantic v2 models define every boundary payload: requests, responses,
  configuration, queue messages. Plain dicts never cross a module boundary.
- Ruff is the single linter and formatter (`ruff check` and `ruff format`); its
  configuration lives in `pyproject.toml` and is not overridden per file.
- mypy runs in strict mode on `src/`; new code may not add `# type: ignore`
  without a comment explaining why.
- Dependencies are managed with uv; `uv.lock` is committed. Adding a dependency
  requires a justification in the PR description.
- No `print` in `src/`; use the configured `structlog` logger.
