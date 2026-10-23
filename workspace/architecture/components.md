# System components

```
+---------+  HTTPS/JSON  +------------------+  asyncpg  +--------------+
| clients | -----------> | service (FastAPI)| --------> | PostgreSQL 16|
+---------+              +--------+---------+           +--------------+
                                  | outbox
                                  v
                         +---------------+
                         | event broker  |  (order events for consumers)
                         +---------------+
```

| Component | Where | Responsibility |
| --- | --- | --- |
| service | `service` repository | REST API, domain logic, persistence. |
| PostgreSQL | managed service | System of record; owned exclusively by the service. |
| Event broker | managed service | Receives order events through the transactional outbox. |
