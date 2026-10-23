# Naming conventions

- Modules, functions and variables: `snake_case`; classes: `PascalCase`; constants:
  `UPPER_SNAKE_CASE`.
- Router files are named after the resource (`orders.py`); Pydantic schemas after
  their role (`OrderCreate`, `OrderRead`, `OrderUpdate`).
- Domain services are named after what they do (`pricing.py` provides
  `calculate_total`).
- Test files mirror the source tree: `tests/unit/api/test_orders.py` covers
  `src/service/api/v1/orders.py`.
- Fixtures are named after what they build (`order_factory`, `tenant_headers`).
- Branches: `<type>/<task-id>-<slug>`; commits follow Conventional Commits (see
  `conventions/commits.md`).
