# Service workspace: Python FastAPI

This workspace builds **{{ projectName }}**, an HTTP service on FastAPI and Python 3.13
with a pytest suite (see `repositories/service.md`).

## How the agent should navigate this workspace

Read in this order before your first task:

1. `rules/` — mandatory rules: `python.md` (typing, linting, dependencies) and
   `api.md` (endpoint design, errors, versioning). Rules win over conventions when
   they conflict.
2. `conventions/` — naming, testing and commit style.
3. `repositories/service.md` — the repository layout and every build/test command.
   Run the quick check listed there before you call a change done.
4. `business/` — the domain vocabulary (`glossary.md`) and numbered business rules
   (`rules.md`); use these exact terms in code and API contracts.
5. `architecture/components.md` and `architecture/decisions/` — the system shape
   and the ADR log; add an ADR when you change something structural.
6. `technical/constraints/` — pinned versions and runtime limits you may not
   exceed.

When a task teaches you a durable fact about the domain, record it in
`business/glossary.md` or `business/rules.md` — not only in the task paper.
