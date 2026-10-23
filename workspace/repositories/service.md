# Repository: service

| | |
| --- | --- |
| Name | `service` |
| Stack | Python 3.13, FastAPI, Pydantic v2, SQLAlchemy 2 (async) with asyncpg, PostgreSQL 16 |
| Dependency manager | uv (`pyproject.toml` plus committed `uv.lock`) |

## Layout

```
service/
  src/service/
    api/             FastAPI app, routers (v1/), error handlers, dependencies
    domain/          business logic, pure Python where possible
    infrastructure/  SQLAlchemy models, repositories, outbound clients
    config.py        pydantic-settings configuration
  alembic/           database migrations
  tests/
    unit/
    integration/
```

## Commands

| Task | Command |
| --- | --- |
| Install dependencies | `uv sync` |
| Run the API locally (http://localhost:8000) | `uv run uvicorn service.api.main:app --reload` |
| Full test suite | `uv run pytest` |
| Fast unit tests only | `uv run pytest tests/unit` |
| Lint and format check | `uv run ruff check . && uv run ruff format --check .` |
| Type check | `uv run mypy src` |
| Create a migration | `uv run alembic revision --autogenerate -m "<name>"` |
| Apply migrations | `uv run alembic upgrade head` |

Quick check before pushing:
`uv run ruff check . && uv run mypy src && uv run pytest`.
