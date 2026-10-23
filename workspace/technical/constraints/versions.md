# Version constraints

| Component | Pinned version | Notes |
| --- | --- | --- |
| Python | 3.13 | `.python-version`; `pyproject.toml` sets `requires-python = ">=3.13,<3.14"`. |
| FastAPI | 0.115+ | Pinned in `pyproject.toml`; upgraded as a chore, not mid-feature. |
| Pydantic | 2.x | v1 compatibility shims are forbidden. |
| SQLAlchemy | 2.x, async only | With asyncpg. |
| PostgreSQL | 16 | Same major version in dev (Testcontainers) and production. |
| uv | latest | CI installs with `uv sync --frozen`. |

Dependency upgrades land as dedicated chore PRs with the full suite green.
