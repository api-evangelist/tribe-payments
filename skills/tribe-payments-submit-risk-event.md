---
name: Submit and act on a fraud-risk event
description: Submit transaction data to Tribe's Risk Monitor for real-time fraud scoring, read the decision, and trigger operator actions.
api: openapi/tribe-payments-trb-risk-monitor-client-api-openapi.json
operations: [subresource_postEventDataCollection, data_get_for_clientEventItem, subresource_postTrigerUserActionsForEventDataItem]
---

# Submit and act on a fraud-risk event (Tribe Risk Monitor Client API v1.1)

Operating instructions for real-time transaction-risk monitoring. Every step maps to a real operationId in `openapi/tribe-payments-trb-risk-monitor-client-api-openapi.json`.

## Authentication
Send a bearer token (`Bearer` / `Token` HTTP security schemes) on each request.

## Conventions to respect
- **Errors.** `400` bad request, `401` unauthorized, `404` unknown event/identifier, `409` conflict (e.g. a user-action already triggered), `415` unsupported media type, `422` unprocessable, `500` server error. See `errors/tribe-payments-problem-types.yml`.
- **Async notifications.** Risk decisions and operator/system/recurring actions are also pushed to your registered webhooks (see `asyncapi/tribe-payments-webhooks.yml`, Risk Monitor family).

## Steps
1. **Submit event data** — `subresource_postEventDataCollection` (`POST /v1/events/{eventId}/data`) to send the transaction/context data for a risk event.
2. **Read the decision** — `data_get_for_clientEventItem` (`GET /v1/events/{eventId}/data/{identifier}`) to retrieve the scored data item / risk decision.
3. **Update an item if needed** — `subresource_patchEventDataItem` (`PATCH /v1/events/{eventId}/data/{identifier}`) to amend event data.
4. **Trigger an operator action** — `subresource_postTrigerUserActionsForEventDataItem` (`POST /v1/events/{eventId}/data/{identifier}/trigger-user-actions/{actionId}`) to enact a review decision. Expect `409` if the action was already applied.

## Notes
- Use `postHealthCheckCollection` (`POST /v1/health-check`) to verify connectivity before a batch run.
