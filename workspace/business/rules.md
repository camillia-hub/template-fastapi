# Business rules

- BR-1 Order totals are computed server-side from order lines; client-sent totals
  are ignored.
- BR-2 Orders can be cancelled while `draft` or `confirmed`; afterwards a return is
  created instead.
- BR-3 Every state transition of an order writes an audit event.
- BR-4 `POST /api/v1/orders` accepts an idempotency key; a retry with the same key
  returns the original order instead of creating a duplicate.
- BR-5 Prices are stored as integer minor units with an ISO 4217 currency code;
  floats never represent money.
