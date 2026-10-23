# Runtime and hosting constraints

- The service runs as a Linux container based on `python:3.13-slim`; the production
  server is gunicorn with `uvicorn.workers.UvicornWorker`.
- It listens on port 8000 behind the ingress, which terminates TLS.
- Configuration comes from environment variables parsed by `config.py`
  (pydantic-settings); the image contains no config files.
- Secrets are injected by the platform secret store as environment variables; they
  are never logged, never returned by an endpoint and never written to disk.
- Cold start stays under 5 seconds; heavy initialization belongs in
  lifespan-managed background tasks, not at import time.
