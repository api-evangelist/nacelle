# Nacelle (nacelle)

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
