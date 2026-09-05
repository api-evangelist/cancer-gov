---
name: query-genomic-data-commons
description: Query NCI Genomic Data Commons cases, files and projects over the GDC GraphQL endpoint, and download open-access files.
api: cancer-gov:gdc-api
generated: 2026-09-05
method: generated
source: graphql/cancer-gov-gdc.graphql (live anonymous introspection of https://api.gdc.cancer.gov/v0/graphql, HTTP 200, 2026-09-05) and https://docs.gdc.cancer.gov/API/Users_Guide/Getting_Started/
operations:
  - graphql:Root.explore
  - graphql:Root.repository
  - graphql:Root.projects
  - graphql:Root.annotations
  - graphql:Root.viewer
---

# Query the Genomic Data Commons

GraphQL endpoint: `https://api.gdc.cancer.gov/v0/graphql`
REST base: `https://api.gdc.cancer.gov`

The GDC is the one API in this estate with **no OpenAPI document**. Probing `/openapi.json`,
`/swagger.json`, `/apidocs` and `/v0/apispec` all returned `404`. The machine-readable contract is
the GraphQL schema, captured in `graphql/cancer-gov-gdc.graphql` (315 types). Ground every query in
that file rather than guessing field names.

## Steps

1. **Check the release you are querying against.**
   `GET https://api.gdc.cancer.gov/status` returns `{"status":"OK","tag":"8.5.0","data_release":"Data
   Release 46.0 - August 10, 2026", ...}`. Quote the `data_release` in any result you hand a
   researcher — GDC data is re-harmonized between releases and a case count is only meaningful with
   its release.

2. **Query.** The root type is `Root`, with these entry fields: `node`, `viewer`, `user`, `query`,
   `repository`, `explore`, `annotations`, `projects`, `cart_summary`, `analysis`.
   - `repository` — files and cases as stored.
   - `explore` — the cohort-building surface, with the aggregation types (`CaseAggregations`,
     `Aggregations`, `Bucket`, `Stats`) the Data Portal itself uses.
   - `projects` — TCGA, TARGET, CPTAC and the rest.

3. **Filter with `FiltersArgument`.** GDC filters are a JSON structure passed as a variable, not
   inline predicates. Build the filter object, pass it as a variable, and keep it out of the query
   string.

4. **Downloading files.** Use the REST download endpoints by GDC UUID, or hand the user a manifest
   and point them at the GDC Data Transfer Tool (`cli/cancer-gov-cli.yml`) for anything bulk.

## Rules

- **Open access is anonymous; controlled access is not.** Introspection and open data answer with no
  credential. Controlled-access data and submission require an `X-Auth-Token` header carrying a token
  downloaded from the GDC Data Portal.
- **Never put a GDC token in a URL, a log line, or a shared manifest.** NCI's own documentation warns
  the token "allows access to all data accessible by the associated user account."
- **Controlled-access genomic data is human-subjects data.** Do not move it into a general-purpose
  context, summarize identifiable content, or write it anywhere outside the environment approved for
  it.
- **Deprecations are invisible in the contract.** GDC v8.3.0 and v8.5.0 both removed dictionary
  properties and made them inaccessible via the API, announced only in the release notes at
  https://docs.gdc.cancer.gov/API/Release_Notes/API_Release_Notes/. Check the notes before assuming a
  field that worked last year still exists.
- **No idempotency, no reversal.** GDC submission has no `Idempotency-Key` and no documented undo
  window.
