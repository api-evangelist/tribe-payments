# Tribe Payments (tribe-payments)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
