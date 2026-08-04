# Schema Stitching

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
