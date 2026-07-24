---
name: Authorize and capture a card payment
description: Use Tribe's Gateway Credit Card API to authorize a card, capture the funds, and refund or cancel if needed.
api: openapi/tribe-payments-trb-cc-api-merchant-api-credit-card-v3.json
operations: [postauthorize, postcapture, postrefund, postcancel]
---

# Authorize and capture a card payment (Tribe Gateway Credit Card API v3)

Operating instructions for driving the delayed-capture card flow. Every step maps to a real operationId in `openapi/tribe-payments-trb-cc-api-merchant-api-credit-card-v3.json`.

## Authentication
Send the merchant account credential pair as headers: `accountId` and `accountPassword` (apiKey security schemes on every operation). Requests are made to the merchant gateway base path (`/v3`, host assigned at onboarding).

## Conventions to respect
- **Asynchronous outcomes.** These operations return `202 Accepted`; the final result is delivered to your registered callback address (see `asyncapi/tribe-payments-webhooks.yml`, Credit Card callback family). Treat the 202 as "accepted", not "settled".
- **Errors.** `400` validation (with `violationObject`), `401` bad credentials, `403` forbidden. See `errors/tribe-payments-problem-types.yml`.

## Steps
1. **Authorize the card** — `postauthorize` (`POST /authorize`). Submit the transaction, card and customer objects. This reserves funds without moving them.
2. **Capture the funds** — `postcapture` (`POST /capture`). Reference the authorized transaction to capture (settle) the reserved amount. For an immediate sale instead of two-step, use `postsale` (`POST /sale`).
3. **Refund if required** — `postrefund` (`POST /refund`) to return funds on a captured transaction.
4. **Cancel/void if not yet captured** — `postcancel` (`POST /cancel`) to void an authorization before capture.

## Notes
- For 3D Secure step-up, use `post3DS-submit` in the credit-card flow.
- Do not retry a 202'd transaction blindly; reconcile via the callback or the Reports API (see the report-pull skill) before re-submitting.
