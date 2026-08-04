# Isometric (isometric-co)

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

Isometric is a London- and New York-based carbon removal registry and AI-native certification platform for the industrial economy, founded in 2022 by Eamon Jubbawy (founder of Onfido). It operates the Isometric Registry — a public registry of high-durability carbon dioxide removal (CDR) credits — and Isometric Certify, the supplier-facing platform for project design, lifecycle assessment, measurement reporting and verification (MRV), and GHG statement submission. Isometric publishes scientific protocols across 14 CDR pathways including direct air capture, enhanced rock weathering, biochar, biomass carbon removal and storage (BiCRS), reforestation, mangrove restoration, wastewater alkalinity enhancement, and subsurface biomass storage, with modular sub-components for capture, feedstocks, LCA, and storage. Two public REST APIs are documented and versioned at /v0 — the Certify Data Ingestion API (53 paths, 170 schemas) for supplier MRV workflows, and the Registry API (38 paths, 79 schemas) for credit balances, issuances, transfers, retirements, deliveries, orders, and Stripe checkout. Both speak OpenAPI 3.1.0, share bearer + x-client-secret authentication, run separate sandbox and production environments, and use Relay-style cursor pagination. No official SDKs are published; clients are expected to generate from the OpenAPI specs. An MCP server is available for AI assistant integration. Data providers including CDR.fyi, MSCI, Sylvera, and CEEZER consume the Registry API for real-time CDR market data.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/isometric-co/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/isometric-co/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Provider
- **Access:** 3rd-Party

## Tags

- Carbon Removal
- Carbon Dioxide Removal
- CDR
- Carbon Credits
- Carbon Registry
- Certification
- MRV
- Measurement Reporting Verification
- Climate
- Sustainability
- Net Zero
- Direct Air Capture
- Enhanced Weathering
- Biochar
- BiCRS
- Reforestation
- Lifecycle Assessment
- GHG Statements
- Carbon Markets
- Climate Tech

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### Isometric Certify Data Ingestion API

The Certify API (MRV API) is the supplier-facing data ingestion surface for carbon removal projects. It covers sources and evidence uploads, datapoints, components and component blueprints, removals and removal templates, GHG statements, project storage units and locations, monitoring submissions, measurement locations and samples, sensors and time-series data uploads, feedstock types and batches, production batches, and biochar applications. Operates against /mrv/v0 on both sandbox and production environments using bearer + x-client-secret authentication. Includes 53 paths and 170 schemas.

- **Human URL:** [https://docs.isometric.com/api-reference/certify/certify-introduction](https://docs.isometric.com/api-reference/certify/certify-introduction)
- **Base URL:** `https://api.isometric.com/mrv/v0`

#### Tags

- Certify
- MRV
- Carbon Removal
- Lifecycle Assessment
- GHG Statements
- Datapoints
- Components
- Removals
- Sources
- Sensors
- Monitoring
- Storage
- Biochar
- Feedstocks

#### Properties

- [Documentation](https://docs.isometric.com/api-reference/certify/certify-introduction)
- [Documentation](https://docs.isometric.com/api-reference/introduction)
- [Documentation](https://docs.isometric.com/api-reference/standards)
- [Authentication](https://docs.isometric.com/api-reference/authentication)
- [Sandbox](https://api.sandbox.isometric.com/mrv/v0)
- [Production](https://api.isometric.com/mrv/v0)
- [OpenAPI](openapi/isometric-certify-api-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/isometric-certify-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/isometric-certify-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [OpenAPI](https://api.isometric.com/mrv/v0/mrv.openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Changelog](https://docs.isometric.com/api-reference/certify/changelog)

### Isometric Registry API

The Registry API exposes Isometric's public carbon removal registry — issuances, credit batches, organization credit balances, transfers, retirements, refunds, orders, deliveries, projects, suppliers, and project documents — alongside transactional operations to create transfers, retirements (including retire-from-oldest-credits), deliveries, beneficiaries, and Stripe checkout sessions. Operates against /registry/v0 on both sandbox and production environments using bearer + x-client-secret authentication. Includes 38 paths and 79 schemas. Already consumed by CDR.fyi, MSCI, Sylvera, and CEEZER for real-time CDR market data.

- **Human URL:** [https://docs.isometric.com/api-reference/registry/registry-introduction](https://docs.isometric.com/api-reference/registry/registry-introduction)
- **Base URL:** `https://api.isometric.com/registry/v0`

#### Tags

- Registry
- Carbon Credits
- Issuances
- Retirements
- Transfers
- Deliveries
- Orders
- Suppliers
- Projects
- Beneficiaries
- Stripe

#### Properties

- [Documentation](https://docs.isometric.com/api-reference/registry/registry-introduction)
- [Documentation](https://docs.isometric.com/api-reference/introduction)
- [Documentation](https://docs.isometric.com/api-reference/standards)
- [Authentication](https://docs.isometric.com/api-reference/authentication)
- [Sandbox](https://api.sandbox.isometric.com/registry/v0)
- [Production](https://api.isometric.com/registry/v0)
- [OpenAPI](openapi/isometric-registry-api-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/isometric-registry-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/isometric-registry-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [OpenAPI](https://api.isometric.com/registry/v0/openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Changelog](https://docs.isometric.com/api-reference/registry/changelog)
- [Article](https://isometric.com/writing-articles/increasing-transparency-in-carbon-markets-with-isometrics-api)

## Common Properties

- [Website](https://isometric.com)
- [Registry](https://registry.isometric.com)
- [Registry](https://isometric.com/registry)
- [Portal](https://docs.isometric.com)
- [Getting Started](https://docs.isometric.com/getting-started)
- [Documentation](https://docs.isometric.com/api-reference/introduction)
- [Documentation](https://docs.isometric.com/api-reference/standards)
- [Authentication](https://docs.isometric.com/api-reference/authentication)
- [OpenAPI](https://api.isometric.com/mrv/v0/mrv.openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI](https://api.isometric.com/registry/v0/openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Sandbox](https://api.sandbox.isometric.com)
- [Production](https://api.isometric.com)
- [Changelog](https://isometric.com/changelog)
- [Protocols](https://registry.isometric.com/protocols)
- [Protocols](https://isometric.com/protocols)
- [Standard](https://registry.isometric.com/standard)
- [Suppliers](https://registry.isometric.com/suppliers)
- [Pricing](https://isometric.com/pricing)
- [Certify](https://isometric.com/certify)
- [Product](https://isometric.com/carbon)
- [Product](https://isometric.com/superpollutants)
- [Product](https://isometric.com/energy)
- [Product](https://isometric.com/fuel)
- [Product](https://isometric.com/materials)
- [Pathway](https://isometric.com/pathways/biochar)
- [Pathway](https://isometric.com/pathways/enhanced-weathering)
- [Pathway](https://isometric.com/pathways/biosphere)
- [Pathway](https://isometric.com/pathways/direct-air-capture)
- [Company](https://isometric.com/about)
- [Careers](https://isometric.com/careers)
- [Press](https://isometric.com/press)
- [Partners](https://isometric.com/partners)
- [Science Network](https://isometric.com/science-network-members)
- [Blog](https://isometric.com/writing)
- [Sign In](https://registry.isometric.com/signin)
- [Sign Up](https://registry.isometric.com/get-started)
- [M C P Server](https://docs.isometric.com/user-guides/general/mcp-server)
- [LinkedIn](https://www.linkedin.com/company/isometric-com)
- [Events](https://luma.com/isometric-hq)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
