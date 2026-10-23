# FastAPI Service — Camillia workspace template

A Camillia Community Hub workspace template for teams building a Python HTTP
service on FastAPI with typed boundaries and a pytest suite.

## What's inside

The `workspace/` directory is the template's `.workspace` contract tree:

```
workspace/
  README.md                     workspace overview and agent navigation guide
  rules/
    python.md                   typing, Pydantic v2, Ruff, mypy, uv
    api.md                      FastAPI router design, errors, versioning
  conventions/
    naming.md                   modules, schemas, fixtures, branches
    testing.md                  pytest layout, markers, coverage floor
    commits.md                  conventional commits and PR rules
  repositories/
    service.md                  repo descriptor: layout, uv commands
  business/
    glossary.md                 domain vocabulary skeleton
    rules.md                    numbered business rules skeleton
  architecture/
    components.md               system components and responsibilities
    decisions/README.md         ADR format and decision log
  technical/constraints/
    versions.md                 pinned toolchain versions
    runtime.md                  container, server and config constraints
```

## How to use

Install from the Camillia Community Hub, then create a workspace from this
template. Camillia installs the `workspace/` tree as the new workspace's
`.workspace` contract: the agent reads these rules, conventions, repository
descriptors and docs skeletons before every task. After installation, replace the
`<Service>` placeholders, point the repository descriptor at your real repo and
adjust the pinned versions to your stack.

## License

MIT — see [LICENSE](LICENSE).
