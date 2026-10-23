# API rules — FastAPI

- Endpoints live in routers under `src/service/api/v1/`; one router per resource.
- Handlers are thin: parse (Pydantic), authorize, call the domain layer in
  `src/service/domain/`, serialize. No SQL or outbound HTTP in a handler.
- All I/O is async (asyncpg, httpx); synchronous drivers may not appear in `src/`.
- Errors map to RFC 9457 problem-details JSON through the central exception
  handlers in `api/errors.py`; never return ad-hoc error dicts.
- The API is versioned by path prefix (`/api/v1`); breaking changes require
  `/api/v2` and an ADR.
- Every endpoint declares `response_model`; OpenAPI tags and summaries stay
  maintained.
- `GET /health` and `GET /ready` are the only unauthenticated endpoints.
- A change is done when `uv run ruff check .`, `uv run mypy src` and
  `uv run pytest` all pass.
