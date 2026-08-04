# Cancer.gov (cancer-gov)

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

Cancer.gov is the web presence of the National Cancer Institute (NCI), the U.S. federal government's principal agency for cancer research and training. NCI and its partner programs expose a rich set of open APIs covering cancer clinical trials, genomic data, cancer-incidence surveillance, research data and models, terminology and vocabularies, and PDQ content — giving researchers, advocacy groups, clinicians, and application developers programmatic access to authoritative cancer data and content.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/cancer-gov/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/cancer-gov/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Provider
- **Access:** Open

## Tags

- Cancer
- Federal Government
- Healthcare
- Research
- Clinical Trials
- Genomics
- Surveillance
- Open Data

## Timestamps

- **Created:** 2024-07-02
- **Modified:** 2026-04-23

## APIs

### NCI Clinical Trials Search API

RESTful API that lets developers build applications, search tools, and digital platforms over NCI-supported cancer clinical trials data sourced from NCI's Clinical Trials Reporting Program (CTRP). The same API powers NCI's public Clinical Trials Search. Developers register for a free API key through the CTS Developer Accounts portal.

- **Human URL:** [https://clinicaltrialsapi.cancer.gov/](https://clinicaltrialsapi.cancer.gov/)
- **Base URL:** `https://clinicaltrialsapi.cancer.gov/api/v2`

#### Tags

- Clinical Trials
- CTRP
- Research

#### Properties

- [Documentation](https://clinicaltrialsapi.cancer.gov/)
- [Sign Up](https://clinicaltrialsapi.cancer.gov/)
- [Parent Page](https://www.cancer.gov/syndication/api)
- [Postman Collection](collections/cancer-gov.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/cancer-gov.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### NCI Genomic Data Commons (GDC) API

The external-facing REST interface for the NCI Genomic Data Commons. Drives the GDC Data Portal and GDC Submission Portal and is open for programmatic access. Provides query, download, and submission endpoints for cancer genomics datasets including TCGA, TARGET, CPTAC, and other NCI-funded genomic programs.

- **Human URL:** [https://gdc.cancer.gov/developers/gdc-application-programming-interface-api](https://gdc.cancer.gov/developers/gdc-application-programming-interface-api)
- **Base URL:** `https://api.gdc.cancer.gov`

#### Tags

- Genomics
- TCGA
- Research Data

#### Properties

- [Documentation](https://docs.gdc.cancer.gov/API/Users_Guide/Getting_Started/)
- [Reference](https://docs.gdc.cancer.gov/Encyclopedia/pages/REST_API/)
- [Portal](https://portal.gdc.cancer.gov/)
- [Postman Collection](collections/cancer-gov.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/cancer-gov.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### NCI SEER API

RESTful API for the Surveillance, Epidemiology, and End Results (SEER) Program. Supports SEER datasets plus staging APIs for cancer staging (TNM and Collaborative Stage algorithms), enabling developers to embed authoritative incidence, survival, and staging logic into their own systems.

- **Human URL:** [https://api.seer.cancer.gov/](https://api.seer.cancer.gov/)
- **Base URL:** `https://api.seer.cancer.gov`

#### Tags

- Surveillance
- Epidemiology
- Staging
- SEER

#### Properties

- [Documentation](https://api.seer.cancer.gov/docs)
- [Portal](https://api.seer.cancer.gov/)
- [Postman Collection](collections/cancer-gov.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/cancer-gov.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### NCI MoDaC API

The NCI Model and Data Clearinghouse (MoDaC) API provides programmatic access to cancer research data, computational models, and associated tools hosted in MoDaC. Developers can search, retrieve metadata, and download model/data artifacts produced by NCI-funded research programs.

- **Human URL:** [https://modac.cancer.gov/](https://modac.cancer.gov/)

#### Tags

- Research Data
- Models
- Clearinghouse

#### Properties

- [Documentation](https://modac.cancer.gov/swagger-ui/4.14.0/index.html)
- [Portal](https://modac.cancer.gov/)
- [Postman Collection](collections/cancer-gov.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/cancer-gov.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### NCI EVS Terminology API

Enterprise Vocabulary Services (EVS) exposes NCI Thesaurus and NCI Metathesaurus content — over 192,000 concepts, 154,000 textual definitions, 623,000 synonyms and 630,000 inter-concept relationships — through a search and browse API used to code, analyze, and share cancer and biomedical research information.

- **Human URL:** [https://evs.nci.nih.gov/](https://evs.nci.nih.gov/)

#### Tags

- Terminology
- Vocabulary
- NCI Thesaurus

#### Properties

- [Documentation](https://evs.nci.nih.gov/)
- [Explorer](https://evsexplore.semantics.cancer.gov/)
- [White Paper](https://evs.nci.nih.gov/ftp1/NCI_Metathesaurus/EVS%20Metathesaurus%20White%20Paper.pdf)
- [Postman Collection](collections/cancer-gov.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/cancer-gov.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### NCI Content Syndication Services

A suite of syndicated content channels — RSS feeds, the NCI Dictionary Widget, and syndicated publication content — that partner sites and health platforms can embed to deliver authoritative cancer content sourced from cancer.gov.

- **Human URL:** [https://www.cancer.gov/syndication](https://www.cancer.gov/syndication)

#### Tags

- Syndication
- Content
- Widgets
- RSS

#### Properties

- [Documentation](https://www.cancer.gov/syndication)
- [Postman Collection](collections/cancer-gov.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/cancer-gov.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/NCIOCPL)
- [Website](https://www.cancer.gov/)
- [Portal](https://api.cancer.gov/)
- [Syndication Services](https://www.cancer.gov/syndication)
- [Data Science](https://datascience.cancer.gov/)
- [Open Data Policy](https://www.cancer.gov/research/resources/open-science)
- [Privacy Policy](https://www.cancer.gov/policies/privacy-security)
- [Licensing And Reuse](https://www.cancer.gov/policies/copyright-reuse)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
