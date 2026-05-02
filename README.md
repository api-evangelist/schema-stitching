# Schema Stitching

Schema Stitching is a GraphQL technique for combining multiple GraphQL schemas into a single unified API gateway. It enables developers to compose distributed GraphQL services, integrate third-party APIs, and build federated data layers by merging types, queries, and mutations from multiple subgraphs into one executable schema.

The primary implementation is provided by The Guild's `@graphql-tools/stitch` package, which supports type merging, stitching directives, schema delegation, and automated query planning comparable to Apollo Federation.

**Human URL:** [https://the-guild.dev/graphql/stitching](https://the-guild.dev/graphql/stitching)

## Resources

- [Documentation](https://the-guild.dev/graphql/stitching/docs)
- [Getting Started](https://the-guild.dev/graphql/stitching/docs/getting-started)
- [Schema Stitching Handbook](https://the-guild.dev/graphql/stitching/handbook)
- [GitHub Repository](https://github.com/ardatan/graphql-tools)
- [npm Package](https://www.npmjs.com/package/@graphql-tools/stitch)
- [Blog](https://the-guild.dev/blog)

## Core Concepts

**Type Merging** — Merges types with the same name from multiple subschemas into a single unified type at the gateway. Keys identify objects for cross-service resolution.

**Schema Delegation** — The mechanism by which the gateway proxies field resolution to underlying subschemas, forwarding queries to each service's executor.

**Stitching Directives** — SDL directives (`@key`, `@merge`, `@computed`, `@canonical`) that let subservices declare their own merging configuration for gateway-reloadable composition.

**Schema Transforms** — Functions applied to subschemas before stitching: rename types, filter fields, wrap queries, hoist fields, or prune schemas.

## Related Tools

| Tool | Purpose |
|---|---|
| [GraphQL Mesh](https://the-guild.dev/graphql/mesh) | Stitch REST, gRPC, and database sources into GraphQL |
| [Hive Gateway](https://the-guild.dev/graphql/hive/docs/gateway) | Federated GraphQL router supporting stitching and federation |
| [Apollo Federation](https://www.apollographql.com/docs/federation/) | Alternative supergraph composition approach |
| [GraphQL Yoga](https://the-guild.dev/graphql/yoga-server) | GraphQL server compatible with schema stitching |

## Artifacts

### JSON Schema

- [schema-stitching-config-schema.json](json-schema/schema-stitching-config-schema.json) — JSON Schema for stitching gateway configuration

### JSON Structure

- [schema-stitching-config-structure.json](json-structure/schema-stitching-config-structure.json) — Document structure for stitching configuration

### JSON-LD

- [schema-stitching-context.jsonld](json-ld/schema-stitching-context.jsonld) — Linked data context for schema stitching vocabulary

### Examples

- [schema-stitching-basic-gateway-example.json](examples/schema-stitching-basic-gateway-example.json) — Basic gateway combining two GraphQL services
- [schema-stitching-type-merging-example.json](examples/schema-stitching-type-merging-example.json) — Type merging with stitching directives

### Vocabulary

- [schema-stitching-vocabulary.yml](vocabulary/schema-stitching-vocabulary.yml) — Domain vocabulary and taxonomy for schema stitching concepts

## Maintainers

**Kin Lane** — kin@apievangelist.com
