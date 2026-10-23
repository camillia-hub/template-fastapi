# Commit and pull-request conventions

- Conventional Commits: `feat:`, `fix:`, `chore:`, `refactor:`, `test:`, `docs:`,
  `perf:`, optionally scoped — `feat(orders): add bulk cancel`.
- One logical change per commit; the message explains why, not what.
- PRs stay under roughly 400 changed lines; migrations and generated files are
  called out in the description.
- Every PR links its task and states the checks the author ran (`uv run pytest`,
  `uv run mypy src`, `uv run ruff check .`).
- Squash-merge to `main`.
