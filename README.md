# Cancer.gov (cancer-gov)

Cancer.gov is the web presence of the National Cancer Institute (NCI), the U.S. federal government's principal agency for cancer research and training. NCI and its partner programs expose a rich set of open APIs covering cancer clinical trials, genomic data, cancer-incidence surveillance, research data and models, terminology and vocabularies, and PDQ content — giving researchers, advocacy groups, clinicians, and application developers programmatic access to authoritative cancer data and content.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/cancer-gov/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Provider
- **Access:** Open

## Tags

 - Cancer, Federal Government, Healthcare, Research, Clinical Trials, Genomics, Surveillance, Open Data

## Timestamps

- **Created:** 2024-07-02
- **Modified:** 2026-04-23

## APIs

### NCI Clinical Trials Search API

RESTful API that lets developers build applications, search tools, and digital platforms over NCI-supported cancer clinical trials data sourced from NCI's Clinical Trials Reporting Program (CTRP). The same API powers NCI's public Clinical Trials Search. Developers register for a free API key through the CTS Developer Accounts portal.

**Human URL:** [https://clinicaltrialsapi.cancer.gov/](https://clinicaltrialsapi.cancer.gov/)

#### Tags

 - Clinical Trials, CTRP, Research

#### Properties

- [Documentation](https://clinicaltrialsapi.cancer.gov/)
- [Sign Up](https://clinicaltrialsapi.cancer.gov/)
- [Parent Page](https://www.cancer.gov/syndication/api)

### NCI Genomic Data Commons (GDC) API

The external-facing REST interface for the NCI Genomic Data Commons. Drives the GDC Data Portal and GDC Submission Portal and is open for programmatic access. Provides query, download, and submission endpoints for cancer genomics datasets including TCGA, TARGET, CPTAC, and other NCI-funded genomic programs.

**Human URL:** [https://gdc.cancer.gov/developers/gdc-application-programming-interface-api](https://gdc.cancer.gov/developers/gdc-application-programming-interface-api)

#### Tags

 - Genomics, TCGA, Research Data

#### Properties

- [Documentation](https://docs.gdc.cancer.gov/API/Users_Guide/Getting_Started/)
- [Reference](https://docs.gdc.cancer.gov/Encyclopedia/pages/REST_API/)
- [Portal](https://portal.gdc.cancer.gov/)

### NCI SEER API

RESTful API for the Surveillance, Epidemiology, and End Results (SEER) Program. Supports SEER datasets plus staging APIs for cancer staging (TNM and Collaborative Stage algorithms), enabling developers to embed authoritative incidence, survival, and staging logic into their own systems.

**Human URL:** [https://api.seer.cancer.gov/](https://api.seer.cancer.gov/)

#### Tags

 - Surveillance, Epidemiology, Staging, SEER

#### Properties

- [Documentation](https://api.seer.cancer.gov/docs)
- [Portal](https://api.seer.cancer.gov/)

### NCI MoDaC API

The NCI Model and Data Clearinghouse (MoDaC) API provides programmatic access to cancer research data, computational models, and associated tools hosted in MoDaC. Developers can search, retrieve metadata, and download model/data artifacts produced by NCI-funded research programs.

**Human URL:** [https://modac.cancer.gov/](https://modac.cancer.gov/)

#### Tags

 - Research Data, Models, Clearinghouse

#### Properties

- [Documentation](https://modac.cancer.gov/swagger-ui/4.14.0/index.html)
- [Portal](https://modac.cancer.gov/)

### NCI EVS Terminology API

Enterprise Vocabulary Services (EVS) exposes NCI Thesaurus and NCI Metathesaurus content — over 192,000 concepts, 154,000 textual definitions, 623,000 synonyms and 630,000 inter-concept relationships — through a search and browse API used to code, analyze, and share cancer and biomedical research information.

**Human URL:** [https://evs.nci.nih.gov/](https://evs.nci.nih.gov/)

#### Tags

 - Terminology, Vocabulary, NCI Thesaurus

#### Properties

- [Documentation](https://evs.nci.nih.gov/)
- [Explorer](https://evsexplore.semantics.cancer.gov/)
- [White Paper](https://evs.nci.nih.gov/ftp1/NCI_Metathesaurus/EVS%20Metathesaurus%20White%20Paper.pdf)

### NCI Content Syndication Services

A suite of syndicated content channels — RSS feeds, the NCI Dictionary Widget, and syndicated publication content — that partner sites and health platforms can embed to deliver authoritative cancer content sourced from cancer.gov.

**Human URL:** [https://www.cancer.gov/syndication](https://www.cancer.gov/syndication)

#### Tags

 - Syndication, Content, Widgets, RSS

#### Properties

- [Documentation](https://www.cancer.gov/syndication)

## Use Cases

- Clinical-trial matching tools that help patients, advocates, and oncologists find NCI-supported trials by condition, location, biomarker, and eligibility.
- Research pipelines that pull genomic data (TCGA, TARGET, CPTAC) from the GDC API for secondary analysis.
- Public-health dashboards reporting SEER-derived cancer incidence, prevalence, and survival statistics.
- Decision-support and EHR integrations that use EVS terminology (NCI Thesaurus) to code oncology concepts consistently.
- Partner health sites embedding NCI Dictionary Widget and syndicated cancer content for authoritative, up-to-date patient information.
- Data-science teams downloading curated NCI models and datasets from MoDaC to benchmark and validate cancer research workflows.

## Common Properties

- [Website](https://www.cancer.gov/)
- [Portal](https://api.cancer.gov/)
- [Syndication Services](https://www.cancer.gov/syndication)
- [Data Science at NCI](https://datascience.cancer.gov/)
- [Open Data Policy](https://www.cancer.gov/research/resources/open-science)
- [Privacy Policy](https://www.cancer.gov/policies/privacy-security)
- [Licensing and Reuse](https://www.cancer.gov/policies/copyright-reuse)

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
