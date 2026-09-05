---
name: look-up-a-cancer-drug
description: Resolve a drug name to its NCI Drug Dictionary entry, including brand/synonym matching via autosuggest.
api: cancer-gov:drug-dictionary-api
generated: 2026-09-05
method: generated
source: openapi/cancer-gov-drug-dictionary-openapi.yml (harvested verbatim from https://webapis.cancer.gov/drugdictionary/v1/swagger/v1/swagger.json on 2026-09-05)
operations:
  - Autosuggest_GetSuggestions
  - Drugs_Search
  - Drugs_GetByName
  - Drugs_GetById
  - Drugs_Expand
  - Drugs_GetStatus
---

# Look up a cancer drug

Base URL: `https://webapis.cancer.gov/drugdictionary/v1`

**No credential is required.** No `securityScheme` is declared.

Unlike the Glossary API, the routing segments here are query parameters, not path segments — the
paths are flat.

## Steps

1. **Disambiguate the name.** Cancer drugs carry a generic name, one or more brand names and a code
   name, and users type any of them. `GET /Autosuggest` — `Autosuggest_GetSuggestions` — matches
   across those forms; run it before assuming the user gave you a canonical name.

2. **Search.** `GET /Drugs/search` — `Drugs_Search`. Page with `size` and `from`.

3. **Fetch the entry.** `GET /Drugs/{prettyUrlName}` — `Drugs_GetByName` — when you have the slug;
   `GET /Drugs/{id}` — `Drugs_GetById` — when you have the id.

4. **Browsing alphabetically instead of searching?** `GET /Drugs/expand/{character}` —
   `Drugs_Expand` — returns every entry starting with that character. `GET /Drugs` — `Drugs_GetAll` —
   returns the whole set and should be paged, not pulled in one request.

## Rules

- **Read-only.** No mutating operations, so reversibility and idempotency do not apply.
- **Do not treat a dictionary entry as clinical guidance.** These are definitions, not dosing or
  treatment recommendations. Return the NCI definition and link back to it rather than paraphrasing
  it into advice.
- **Different service, different conventions.** The Glossary API next door uses path segments for
  dictionary/audience/language and this one does not. Do not copy a working Glossary URL shape here.
- **Status:** `GET /Drugs/status` — `Drugs_GetStatus`.
