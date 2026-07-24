---
name: Pull a transaction / order-status report
description: Request transaction, order-status, disputes and processing-account reports from Tribe's Gateway Reports API, delivered via callback.
api: openapi/tribe-payments-trb-report-api-merchant-api-report-v3.json
operations: [posttransactions, postorder-status, postdisputes, postprocessing-accounts]
---

# Pull a transaction / order-status report (Tribe Gateway Reports API v3)

Operating instructions for reconciliation reporting. Every step maps to a real operationId in `openapi/tribe-payments-trb-report-api-merchant-api-report-v3.json`.

## Authentication
Send the reporting credential pair as headers: `apiKey` and `apiPassword` (apiKey security schemes).

## Conventions to respect
- **Asynchronous delivery.** Each report request returns `202 Accepted`; the generated report is delivered to your registered report callback address (see `asyncapi/tribe-payments-webhooks.yml`, Reports callback family — `order-status`, `disputes`, `transactions`, `processing-accounts`).
- **Rate limiting.** The Reports API returns `429 Too Many Requests` when you exceed the access threshold; back off and retry. `422` indicates an unprocessable (semantically invalid) request.

## Steps
1. **Request a transactions report** — `posttransactions` (`POST /transactions`) with the date range / filter criteria.
2. **Request order-status** — `postorder-status` (`POST /order-status`) to report on the status of specific orders.
3. **Request disputes** — `postdisputes` (`POST /disputes`) for chargeback / dispute data.
4. **Request processing accounts** — `postprocessing-accounts` (`POST /processing-accounts`).
5. **Receive the report** — handle the POST to your registered report callback address; correlate to the originating request.

## Notes
- Reports are pull-then-callback, not synchronous downloads — do not poll the request endpoint expecting the payload inline.
