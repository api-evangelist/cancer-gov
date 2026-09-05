---
name: search-clinical-trials
description: Search NCI-supported cancer clinical trials through the NCI Clinical Trials Search API, including key setup and the limits of the data.
api: cancer-gov:clinical-trials-api
generated: 2026-09-05
method: generated
source: https://www.cancer.gov/syndication/api and openapi/cancer-gov-trials-api-openapi.yml — see the caveat below on the provenance of that spec.
operations:
  - getTrials
  - getTrialById
---

# Search NCI clinical trials

Base URL: `https://clinicaltrialsapi.cancer.gov/api/v2`

> **Contract caveat — read before relying on parameter names.** NCI publishes no machine-readable
> specification for this API. `clinicaltrialsapi.cancer.gov` is a single-page application whose
> catch-all returns HTTP 200 with a 1,754-byte HTML shell for *every* path, including
> `/openapi.json`, `/swagger.json`, `/api-docs` and `/v3/api-docs`. The OpenAPI files in this repo
> for the trials, interventions, diseases and terms surfaces are **hand-authored from documentation**,
> not harvested from NCI, and they say so in `info.description`. Treat their schemas as a sketch and
> verify field names against a live response. The other seven specs in `openapi/` are the real thing.

## Steps

1. **Get a key.** Register free at the CTS Developer Accounts portal,
   https://clinicaltrialsapi.cancer.gov/. Send it as the `X-API-KEY` header. Verified live: a request
   without a key returns HTTP `401` with the body `{"message":"Forbidden"}` — note the body and the
   status disagree, so branch on the status code, not the message.

2. **Search.** `GET /trials` with query parameters, or `POST /trials` for structured queries.
   `size` and `from` page the results; `include` and `exclude` project fields, which matters here
   because a full trial record is large.

3. **Fetch one trial.** `GET /trials/{nci_id}`.

4. **Constrain by disease or intervention** using `/diseases` and `/interventions` to resolve a
   user's plain-language term to the codes the trials index actually uses, rather than passing raw
   text as a keyword.

## Rules

- **This is NOT ClinicalTrials.gov.** ClinicalTrials.gov is operated by the National Library of
  Medicine at `clinicaltrials.gov` and is a different API from a different agency. This API covers
  NCI-supported trials sourced from NCI's Clinical Trials Reporting Program (CTRP). Never mix the two
  base URLs or their parameter conventions.
- **Know what the data excludes.** NCI states this API does not include regulatory information (IRB
  approval, IND/IDE details, NCI Data Table 4), biomarker data, or any accrual information. If a user
  asks whether a trial is still enrolling in a specific location, say what the API can and cannot
  tell them.
- **Never present trial data as a treatment recommendation.** Return trials with their NCI ID and a
  link, and direct clinical questions to the trial's own contact or the user's care team.
- **Rate limits are undocumented.** NCI publishes no limit and returns no rate-limit headers. Third
  party guides circulate a "50 requests per minute" figure that is not sourced to NCI — do not treat
  it as a contract.
- **Support:** ctrp_support@mail.nih.gov
