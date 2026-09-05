---
name: resolve-an-nci-thesaurus-concept
description: Resolve a biomedical term to an NCI Thesaurus concept code and walk its hierarchy, synonyms and cross-terminology maps.
api: cancer-gov:evs-api
generated: 2026-09-05
method: generated
source: openapi/cancer-gov-evs-openapi.yml (harvested verbatim from https://api-evsrest.nci.nih.gov/v3/api-docs on 2026-09-05)
operations:
  - getTerminologies
  - search
  - searchSingleTerminology
  - getConcept
  - getParents
  - getChildren
  - getPathsToRoot
  - getMaps
---

# Resolve an NCI Thesaurus concept

Base URL: `https://api-evsrest.nci.nih.gov`

**No credential is required.** Verified live: `GET /api/v1/metadata/terminologies` returns `200`
anonymously.

This is the API to reach for when a term needs to become a *code* — something another system can
join on.

## Steps

1. **Pin the terminology and its version first.**
   `GET /api/v1/metadata/terminologies` — `getTerminologies`. EVS serves more than NCIt: the live
   response includes `ncit`, `mdr` (MedDRA), `hl7v30`, `snomedct_us`, `icd10`, `radlex` and `ndfrt`,
   each with its own version and date. Record the version you used — `ncit 26.06e` dated `2026-06-29`
   at time of writing — because concept codes are stable but their surrounding relationships are not.

2. **Search for the term.**
   `GET /api/v1/concept/{terminology}/search` — `searchSingleTerminology` — when you already know the
   terminology. `GET /api/v1/concept/search` — `search` — to search across them. Page with `pageSize`
   and order with `sort`.

3. **Fetch the concept.**
   `GET /api/v1/concept/{terminology}/{code}` — `getConcept`.

4. **Walk the hierarchy only as far as you need.**
   `getParents` and `getChildren` for one step; `getPathsToRoot` for full lineage. Prefer the
   single-step calls — `getDescendants` on a high-level concept returns a very large result.

5. **Crossing to another vocabulary?**
   `GET /api/v1/concept/{terminology}/{code}/maps` — `getMaps` — is the supported route. Do not
   hand-map NCIt to SNOMED or ICD-10 yourself when EVS publishes the mapping.

## Rules

- **Always report the terminology version alongside the code.** A bare code with no version is not
  reproducible.
- **`417`, not `400`.** EVS uses `417 Expectation Failed` as its general bad-parameter code — it
  appears 36 times in the contract. Treat `417` as "your request was malformed", not as a transport
  fault to retry.
- **Error shape is Spring's `RestException`:** `{timestamp, status, error, message, path}`.
- **Terms of use:** https://evs.nci.nih.gov/ftp1/NCI_Thesaurus/ThesaurusTermsofUse.htm
