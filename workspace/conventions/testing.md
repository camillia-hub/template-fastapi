# Testing conventions — pytest

- pytest with `pytest-asyncio` (strict mode) and `httpx.ASGITransport` for API
  tests; no running server is needed.
- Layout: `tests/unit/` (fast, no I/O) and `tests/integration/` (Testcontainers
  PostgreSQL). `uv run pytest` runs both; use `uv run pytest tests/unit` for the
  fast loop.
- Shared fixtures live in `tests/conftest.py`; factories are plain functions or
  `factory_boy` factories — never a fixture returning another fixture.
- Every endpoint has at least: one happy-path test, one validation-error test
  (422) and one authorization test (401 or 403).
- Coverage is measured with `pytest --cov=src`; the floor is 85% and CI enforces
  it.
- Markers: `@pytest.mark.slow` for tests over one second; the CI fast lane
  deselects them.
