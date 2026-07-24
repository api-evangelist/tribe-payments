# Tribe Payments (tribe-payments)

Tribe Payments is a London, United Kingdom-based payments technology company and issuer/acquirer processor that gives banks, acquirers, and fintechs a modular, API-driven platform to launch card and payment products without building core processing in-house. Built around its ISAAC processing engine, Tribe spans card issuing (issuer processing), merchant acquiring and a payment gateway, POS/SoftPOS terminal management, tokenization, fraud and risk monitoring, 3D Secure, digital wallets, Open Banking (PSD2 account-to-account payment initiation and account information), and Bank Connect / Banking-as-a-Service.

Tribe is developer-led and publishes an extensive public API reference at **[doc.tribepayments.com](https://doc.tribepayments.com/)**; sandbox access is granted on request via the contact form rather than through fully open self-service signup. Its home market is the United Kingdom, where PSD2/Open Banking and the Faster Payments and Bacs rails operated by Pay.UK anchor a dense cluster of API-native payment providers.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/tribe-payments/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/tribe-payments/refs/heads/main/apis.yml)

## Tags

- Payments
- United Kingdom
- Issuer Processor
- Card Issuing
- Acquiring
- Payment Gateway
- Open Banking
- Banking-as-a-Service
- Fraud
- Point of Sale

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## APIs

Fifteen verbatim OpenAPI 3.0 documents were harvested from the Tribe developer portal's public content API, across eight documented products. Several core issuer-processor and acquiring APIs are documented in the portal but publish no downloadable OpenAPI in their current version.

### Spec-backed APIs (OpenAPI harvested)

- **Payment Gateway - Credit Card API** — REST card processing (sale, auth, capture, refund, void) + callbacks. [Docs](https://doc.tribepayments.com/docs/trb-gateway--credit-card-api--v3)
- **Payment Gateway - Hosted Payments API (HPP)** — Tribe-hosted checkout + webhooks. [Docs](https://doc.tribepayments.com/docs/trb-gateway--hosted-payments-api--v3)
- **Payment Gateway - Credit Card Token API** — card tokenization + token webhooks. [Docs](https://doc.tribepayments.com/docs/trb-gateway--credit-card-token-api--v3)
- **Payment Gateway - Reports API** — transaction reporting + report callbacks. [Docs](https://doc.tribepayments.com/docs/trb-gateway--report-api--v3)
- **Point of Sale - Device Directory API** — terminal/SoftPOS device management. [Docs](https://doc.tribepayments.com/docs/point-of-sale--device-directory-api--v3)
- **Risk Monitor - Client API** — real-time fraud/risk monitoring + webhooks. [Docs](https://doc.tribepayments.com/)
- **Open Banking - Bank API** — ASPSP-side AIS/PIS + bank webhooks. [Docs](https://doc.tribepayments.com/)
- **Open Banking - Third-Party Providers API (TPP)** — PIS/AIS payment initiation + payment webhooks. [Docs](https://doc.tribepayments.com/)

### Documented APIs (no downloadable OpenAPI in current version)

- **Issuer Processor - Program Manager API (PM API)** — [Docs](https://doc.tribepayments.com/docs/issuing--program-manager-api--v1.2)
- **Issuer Processor - Transaction Authorization Interface (TAI API)** — [Docs](https://doc.tribepayments.com/docs/issuing--transaction-authorization-interface--v1.2)
- **Acquiring Processor - Acquirer API (ACAPI)** — [Docs](https://doc.tribepayments.com/docs/acquiring--acquirer-api--v1)
- **Acquiring Processor - Merchant API (MAPI)** — [Docs](https://doc.tribepayments.com/docs/acquiring--merchant-api--v1)
- **Acquiring Processor - Terminal API (TAPI)** — [Docs](https://doc.tribepayments.com/docs/acquiring--terminal-api--v2)
- **Acquiring Processor - Tokenization API (TOKAPI)** — [Docs](https://doc.tribepayments.com/docs/acquiring--tokenization-api--v1)
- **Bank Connect - Payment Services API** — [Docs](https://doc.tribepayments.com/docs/bank-connect--payment-services-api--v1)

## Authentication

API-key style header credentials, defined per product: Gateway Credit Card / HPP / Token APIs use `x-auth-account-id` + `x-auth-account-password`; Reports API uses `x-auth-report-api-key` + `x-auth-report-api-password`; Open Banking TPP API uses an HTTP bearer token + `X-Client-ID`; Risk Monitor uses a bearer / `X-AUTH-TOKEN` header. No OAuth2 flows are declared in the harvested specs.

## Common Properties

- [Website](https://www.tribepayments.com/)
- [Developer Portal](https://doc.tribepayments.com/)
- [Change Log / Product Updates](https://www.tribepayments.com/product-updates)
- [Blog / News](https://www.tribepayments.com/news)
- [Status Page](https://status.tribepayments.com/)
- [Support / Contact](https://www.tribepayments.com/contact-us)
- [Knowledge Hub](https://www.tribepayments.com/knowledge-hub)
- [Privacy Policy](https://www.tribepayments.com/privacy-policy)
- [LinkedIn](https://www.linkedin.com/company/tribepayments/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
