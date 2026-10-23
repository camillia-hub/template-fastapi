# Business glossary

Use these terms in code, API contracts and conversations. Add a row when the domain
gains a concept; never invent synonyms.

| Term | Definition |
| --- | --- |
| Customer | A person or organization that places orders. |
| Order | A customer's request for products; the central aggregate. |
| Order line | One product, quantity and agreed price inside an order. |
| Fulfillment | The delivery process of an order, tracked as a state machine. |
| Shipment | A physical dispatch linked to one order. |
| Idempotency key | A client-supplied token that makes retried writes safe. |
