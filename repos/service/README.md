# {{ projectName }} — Service

FastAPI HTTP service for **{{ projectName }}** on Python 3.13, with typed
boundaries (Pydantic v2) and a pytest suite.

## Layout

- `src/` — routers, schemas, services, persistence
- `tests/` — pytest suite with markers per layer

## Commands

```bash
uv sync
uv run uvicorn src.main:app --reload
uv run pytest
uv run ruff check && uv run mypy src
```

The workspace contract (`repositories/service.md`) lists the build rules and
the quick checks the agent runs before calling a change done.
