---
name: look-up-a-cancer-term
description: Resolve a cancer term to its authoritative NCI Dictionary of Cancer Terms definition, with autosuggest for partial input.
api: cancer-gov:glossary-api
generated: 2026-09-05
method: generated
source: openapi/cancer-gov-glossary-openapi.yml (harvested verbatim from https://webapis.cancer.gov/glossary/v1/swagger/v1/swagger.json on 2026-09-05)
operations:
  - Autosuggest_GetSuggestions
  - Terms_Search
  - Terms_GetByName
  - Terms_GetById
  - HealthCheck_IsHealthy
---

# Look up a cancer term

Base URL: `https://webapis.cancer.gov/glossary/v1`

**No credential is required.** The Glossary Term API declares no `securityScheme`. Do not send an
`X-API-KEY` — that header belongs to a different NCI service (the Clinical Trials Search API).

Every path takes three routing segments before anything else:

- `{dictionary}` — the dictionary to read, e.g. `Cancer.gov`
- `{audience}` — `Patient` or `HealthProfessional`
- `{language}` — `en` or `es`

Getting these wrong is the most common failure: the API answers `400`, not `404`.

## Steps

1. **If you only have partial or user-typed input, suggest first.**
   `GET /Autosuggest/{dictionary}/{audience}/{language}/{searchText}` — `Autosuggest_GetSuggestions`.
   Use this to turn "melanom" into real term candidates before committing to a lookup.

2. **If you have a full phrase, search.**
   `GET /Terms/search/{dictionary}/{audience}/{language}/{query}` — `Terms_Search`.
   Page with `size` and `from`; these are offset-based, and the response carries no next-link, so you
   stop when a page comes back shorter than `size`.

3. **Fetch the definition.**
   Prefer `GET /Terms/{dictionary}/{audience}/{language}/{prettyUrlName}` — `Terms_GetByName` — when
   you have the slug, because it is the same identifier cancer.gov uses in its own URLs and it is
   stable enough to cache. Use `GET /Terms/{dictionary}/{audience}/{language}/{id}` —
   `Terms_GetById` — when you already hold a numeric id.

4. **Report the audience you read.** A `Patient` definition and a `HealthProfessional` definition of
   the same term are written differently on purpose. Always say which one you returned.

## Rules

- **Read-only.** This API has zero mutating operations. There is nothing here to undo, and nothing
  that needs an idempotency key.
- **No rate-limit signal.** NCI publishes no limit for this service and returns no `X-RateLimit-*` or
  `Retry-After` header. Back off on your own schedule rather than waiting for a signal that will
  never arrive.
- **Errors are not RFC 9457.** Expect a plain JSON body, not `application/problem+json`. See
  `errors/cancer-gov-problem-types.yml`.
- **Health check before a batch run:** `GET /HealthCheck/status` — `HealthCheck_IsHealthy`.
