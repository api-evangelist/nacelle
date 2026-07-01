# Nacelle GraphQL APIs

Nacelle is a headless / composable commerce data platform. It ingests and normalizes
commerce data (Shopify) and content (Contentful and other CMS sources), indexes it
per **Space**, and serves it back to headless storefronts through a single, fast
**Storefront GraphQL API**. A separate **Admin GraphQL API** drives the indexing /
ingestion pipeline.

> **Current status (2026-07-01):** Nacelle was **not** acquired. The company remained
> independent and has since repositioned around an **AI personalization engine** for
> e-commerce customer acquisition. The original headless-commerce Storefront GraphQL
> API is now effectively a **legacy / maintenance-mode** product. The "stable" and
> "legacy" Storefront API versions are both still documented, but treat this surface
> as mature rather than actively expanding, and verify the current endpoints and
> availability against the live docs before building against it.

## Storefront GraphQL API

- **Endpoint:** `POST https://storefront.api.nacelle.com/graphql/v1/spaces/<SPACE_ID>`
- **Documentation:** https://docs.nacelle.com/docs/storefront-graphql-api-stable
- **API Reference:** https://docs.nacelle.com/reference/api-reference
- **Auth headers:**
  - `x-nacelle-space-id: <SPACE_ID>`
  - `x-nacelle-space-token: <PUBLIC_STOREFRONT_TOKEN>`
  - `Content-Type: application/json`

### Queries

| Query | Returns |
| --- | --- |
| `allProducts` | Normalized product entries (Relay-style connection) |
| `allProductCollections` | Merchandised product collections (Relay-style connection) |
| `allContent` | CMS content entries (Relay-style connection) |
| `navigation` | Navigation groups (menus) for a space |
| `spaceProperties` | Space-level configuration (locales, currency, metadata) |

Common filter arguments: `first`, `after`, `handles`, `nacelleEntryIds`,
`entryDepth` (default 4, for resolving nested content references), and `locale`
(e.g. `en-US`). Connections expose `edges { cursor node { ... } }`, `pageInfo`,
and `totalCount` — note that Nacelle does not support requesting both `edges` and
`nodes` in the same connection. Automatic Persisted Queries (APQ) are supported for
CDN caching (~60s TTL). Payloads are capped at 10 MB with a 20-second request timeout.

### Example — fetch products by handle

```graphql
query Products {
  allProducts(filter: { first: 5, handles: ["classic-tee"] }) {
    edges {
      cursor
      node {
        nacelleEntryId
        sourceEntryId
        handle
        locale
        content { title description featuredMedia { src altText } }
        variants { nacelleEntryId sku availableForSale price compareAtPrice }
      }
    }
    pageInfo { hasNextPage endCursor }
    totalCount
  }
}
```

## Admin GraphQL API (Indexing / Ingestion)

- **Endpoint:** `POST https://admin.api.nacelle.com/graphql`
- **Documentation:** https://docs.nacelle.com/docs/admin-api
- **Auth headers:**
  - `x-nacelle-space-id: <SPACE_ID>`
  - `x-nacelle-admin-token: <ADMIN_TOKEN>`
- **Status:** Documented as a **beta / limited-availability** feature.

The Admin API programmatically performs dashboard-equivalent actions on a Space —
principally driving the indexing pipeline that pulls data from connected sources
(Shopify, CMS) into the Space. Typical operations: start or reset an index for a data
source / individual entry / entry type, and query the current indexing status.

```graphql
mutation StartIndex {
  startIndex(input: { dataSourceId: "shopify:my-store" }) {
    jobId
    status
    startedAt
  }
}
```

## Notes on this artifact

- **Endpoint:** Two live GraphQL endpoints (Storefront + Admin).
- **Schema:** `graphql/nacelle-schema.graphql` is a representative schema derived from
  the public Nacelle documentation; it captures the real query names, arguments, and
  the shape of the Product / ProductCollection / Content / Navigation types, but is
  not a byte-for-byte introspection dump of Nacelle's production schema.
- **No REST surface:** Nacelle's public data APIs are GraphQL-first. No genuine public
  REST API is documented, so no OpenAPI artifact is included for this provider.
- Source: https://docs.nacelle.com/
