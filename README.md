# Nacelle (nacelle)

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

Nacelle is a headless / composable commerce data platform that ingests, normalizes, and indexes commerce and content data (Shopify, Contentful and other CMS sources) per Space, and serves it back to headless storefronts through a single, fast GraphQL Storefront API. The company has since pivoted toward an AI personalization engine, and the headless commerce Storefront API is now a legacy / maintenance-mode product rather than an actively expanding platform.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/nacelle/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/nacelle/refs/heads/main/apis.yml)

## Current Status

- **Not acquired.** Nacelle (founded 2019; ~$72.8M raised, incl. a $50M Series B led by Tiger Global in 2021) remained an independent company. It has repositioned around an **AI personalization engine** for e-commerce customer acquisition.
- The original **headless commerce Storefront GraphQL API** is best treated as **legacy / maintenance-mode**. The docs publish both a "stable" and a "legacy" version of the Storefront API.
- The **Admin (indexing / ingestion) API** is documented as a **beta / limited-availability** feature.
- **GraphQL-first:** No public REST API is documented, so this catalog entry includes a GraphQL schema and omits OpenAPI honestly.

## Tags

- Commerce
- Headless Commerce
- Composable Commerce
- GraphQL
- Content
- Data Indexing

## Timestamps

- **Created:** 2026-07-01
- **Modified:** 2026-07-01

## APIs

### Nacelle Storefront Products API

The `allProducts` query on Nacelle's Storefront GraphQL API returns normalized product entries (variants, pricing, media, metafields) drawn from ingested Shopify or other commerce sources, with Relay-style pagination by handle or nacelleEntryId.

- **Human URL:** [https://docs.nacelle.com/docs/storefront-graphql-api-stable](https://docs.nacelle.com/docs/storefront-graphql-api-stable)
- **Base URL:** `https://storefront.api.nacelle.com/graphql/v1/spaces`

#### Tags

- Products
- Catalog
- GraphQL
- Commerce

#### Properties

- [Documentation](https://docs.nacelle.com/docs/storefront-graphql-api-stable)
- [API Reference](https://docs.nacelle.com/reference/api-reference)
- [GraphQL](graphql/nacelle-graphql.md)
- [GraphQL Schema](graphql/nacelle-schema.graphql)
- [Postman Collection](collections/nacelle.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/nacelle.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Nacelle Storefront Product Collections API

The `allProductCollections` query returns merchandised collections of products (the normalized equivalent of Shopify collections) with their member product references, for building category and listing pages on a headless storefront.

- **Human URL:** [https://docs.nacelle.com/docs/storefront-graphql-api-stable](https://docs.nacelle.com/docs/storefront-graphql-api-stable)
- **Base URL:** `https://storefront.api.nacelle.com/graphql/v1/spaces`

#### Tags

- Product Collections
- Merchandising
- GraphQL

#### Properties

- [Documentation](https://docs.nacelle.com/docs/storefront-graphql-api-stable)
- [GraphQL](graphql/nacelle-graphql.md)
- [GraphQL Schema](graphql/nacelle-schema.graphql)
- [Postman Collection](collections/nacelle.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/nacelle.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Nacelle Storefront Content API

The `allContent` query returns CMS content entries (pages, articles, marketing blocks, media) ingested from sources such as Contentful, with a configurable entryDepth for resolving nested content references.

- **Human URL:** [https://docs.nacelle.com/docs/storefront-graphql-api-stable](https://docs.nacelle.com/docs/storefront-graphql-api-stable)
- **Base URL:** `https://storefront.api.nacelle.com/graphql/v1/spaces`

#### Tags

- Content
- CMS
- GraphQL

#### Properties

- [Documentation](https://docs.nacelle.com/docs/storefront-graphql-api-stable)
- [GraphQL](graphql/nacelle-graphql.md)
- [GraphQL Schema](graphql/nacelle-schema.graphql)
- [Postman Collection](collections/nacelle.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/nacelle.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Nacelle Storefront Navigation and Spaces API

The `navigation` and `spaceProperties` queries return a space's navigation groups (menus) and space-level configuration (locales, currency, metadata) used to render a headless storefront's chrome and localization.

- **Human URL:** [https://docs.nacelle.com/docs/spaces](https://docs.nacelle.com/docs/spaces)
- **Base URL:** `https://storefront.api.nacelle.com/graphql/v1/spaces`

#### Tags

- Navigation
- Spaces
- Settings
- GraphQL

#### Properties

- [Documentation](https://docs.nacelle.com/docs/spaces)
- [API Reference](https://docs.nacelle.com/docs/storefront-graphql-api-stable)
- [GraphQL](graphql/nacelle-graphql.md)
- [GraphQL Schema](graphql/nacelle-schema.graphql)
- [Postman Collection](collections/nacelle.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/nacelle.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Nacelle Admin Indexing and Ingestion API

The Admin GraphQL API triggers and monitors the indexing / ingestion pipeline that pulls data from connected sources (Shopify, CMS) into a space - starting or resetting index jobs for a data source, entry, or entry type, and querying indexing status. Documented as a beta / limited-availability feature and authenticated with an admin token.

- **Human URL:** [https://docs.nacelle.com/docs/admin-api](https://docs.nacelle.com/docs/admin-api)
- **Base URL:** `https://admin.api.nacelle.com/graphql`

#### Tags

- Indexing
- Ingestion
- Admin
- GraphQL

#### Properties

- [Documentation](https://docs.nacelle.com/docs/admin-api)
- [GraphQL](graphql/nacelle-graphql.md)
- [GraphQL Schema](graphql/nacelle-schema.graphql)
- [Postman Collection](collections/nacelle.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/nacelle.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Authentication

- **Storefront API:** `x-nacelle-space-id` + `x-nacelle-space-token` (public storefront token).
- **Admin API:** `x-nacelle-space-id` + `x-nacelle-admin-token`.

## Common Properties

- [GitHub Organization](https://github.com/getnacelle)
- [LinkedIn](https://www.linkedin.com/company/nacelle)
- [Website](https://nacelle.com/)
- [Documentation](https://docs.nacelle.com/)
- [Plans](plans/nacelle-plans-pricing.yml)
- [Rate Limits](rate-limits/nacelle-rate-limits.yml)
- [Fin Ops](finops/nacelle-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
