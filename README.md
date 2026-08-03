# Amazon HealthImaging (amazon-healthimaging)

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

AWS HealthImaging is a HIPAA-eligible service that helps healthcare providers and their software partners store, transform, and apply machine learning to medical images. It provides sub-second image retrieval and enables scaling from hundreds to millions of medical images.

**URL:** [https://aws.amazon.com/healthimaging/](https://aws.amazon.com/healthimaging/)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags:

 - AWS, Healthcare, HIPAA, Machine Learning, Medical Imaging, DICOM

## Timestamps

- **Created:** 2026-03-16
- **Modified:** 2026-04-19

## APIs

### AWS HealthImaging API
The AWS HealthImaging API provides programmatic access to create and manage datastores, image sets, and DICOM import jobs for storing and retrieving medical imaging data at scale. The API is HIPAA-eligible and supports sub-second image retrieval.

**Human URL:** [https://aws.amazon.com/healthimaging/](https://aws.amazon.com/healthimaging/)

#### Tags:

 - Healthcare, HIPAA, Medical Imaging, DICOM, Datastores

#### Properties

- [Documentation](https://docs.aws.amazon.com/healthimaging/latest/devguide/API_Reference.html)
- [OpenAPI](openapi/amazon-healthimaging-openapi.yaml)
- [GettingStarted](https://aws.amazon.com/healthimaging/getting-started/)
- [Pricing](https://aws.amazon.com/healthimaging/pricing/)
- [FAQ](https://aws.amazon.com/healthimaging/faqs/)
- [APIReference](https://docs.aws.amazon.com/healthimaging/latest/devguide/API_Reference.html)
- [Authentication](https://docs.aws.amazon.com/healthimaging/latest/devguide/security-iam.html)
- [JSONSchema](json-schema/healthimaging-datastore-schema.json)
- [JSONLD](json-ld/amazon-healthimaging-context.jsonld)

## Common Properties

- [Portal](https://aws.amazon.com/healthimaging/)
- [Documentation](https://docs.aws.amazon.com/healthimaging/)
- [TermsOfService](https://aws.amazon.com/service-terms/)
- [PrivacyPolicy](https://aws.amazon.com/privacy/)
- [Support](https://aws.amazon.com/premiumsupport/)
- [Blog](https://aws.amazon.com/blogs/industries/healthcare/)
- [GitHubOrganization](https://github.com/aws)
- [Console](https://console.aws.amazon.com/healthimaging/)
- [SignUp](https://portal.aws.amazon.com/billing/signup)
- [StatusPage](https://health.aws.amazon.com/health/status)
- [Contact](https://aws.amazon.com/contact-us/)
- [SDK](https://aws.amazon.com/developer/tools/)
- [CLI](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/medical-imaging/index.html)

## Features

| Name | Description |
|------|-------------|
| HIPAA-Eligible Storage | Fully HIPAA-eligible service for storing protected health information including medical images. |
| DICOM Support | Native support for DICOM format, the standard for medical imaging data exchange and storage. |
| Sub-Second Retrieval | Optimized storage architecture enabling sub-second retrieval of medical images at any scale. |
| Machine Learning Integration | Built-in support for applying machine learning models to medical imaging data for analysis. |
| Scalable Datastores | Create and manage datastores that scale from hundreds to millions of medical images. |
| Image Set Management | Organize medical images into sets with comprehensive metadata management and versioning. |
| Bulk Import | DICOM import jobs enable bulk import of medical imaging data from Amazon S3. |

## Use Cases

| Name | Description |
|------|-------------|
| Radiology Workflow | Streamline radiology workflows by centralizing medical image storage and enabling rapid retrieval. |
| AI-Powered Diagnostics | Apply machine learning models to medical images for automated diagnostic assistance. |
| Healthcare Data Archiving | Archive medical imaging data in a HIPAA-eligible, scalable environment with long-term retention. |
| Multi-Site Imaging | Centralize medical imaging data from multiple healthcare sites for unified access and analysis. |
| Clinical Research | Support clinical research by providing scalable access to large medical imaging datasets. |

## Integrations

| Name | Description |
|------|-------------|
| Amazon S3 | Import medical imaging data from S3 buckets using DICOM import jobs. |
| AWS IAM | Control access to HealthImaging resources using IAM roles and policies. |
| Amazon CloudWatch | Monitor HealthImaging operations and performance metrics through CloudWatch. |
| AWS HealthLake | Integrate with HealthLake for combining medical imaging with FHIR health records. |
| Amazon SageMaker | Apply SageMaker ML models to medical images for AI-powered analysis and diagnostics. |

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [AWS HealthImaging OpenAPI](openapi/amazon-healthimaging-openapi.yaml)

### JSON Schema

113 schema files in [json-schema/](json-schema/)

### JSON Structure

113 structure files in [json-structure/](json-structure/)

### JSON-LD

- [Amazon HealthImaging Context](json-ld/amazon-healthimaging-context.jsonld)

### Examples

113 example files in [examples/](examples/)

## Capabilities

Naftiko capabilities organized as shared per-API definitions composed into customer-facing workflows.

### Shared Per-API Definitions

- [AWS HealthImaging](capabilities/shared/amazon-healthimaging.yaml) — 18 operations for medical imaging management

### Workflow Capabilities

| Workflow | APIs Combined | Tools | Persona |
|----------|--------------|-------|---------|
| [Amazon HealthImaging Medical Imaging Operations](capabilities/amazon-healthimaging-medical-imaging-operations.yaml) | AWS HealthImaging | 12 | Healthcare Developer, Medical Imaging Engineer, HIPAA Compliance Officer |

## Vocabulary

- [Amazon HealthImaging Vocabulary](vocabulary/amazon-healthimaging-vocabulary.yaml) — Unified taxonomy mapping 5 resources, 10 actions, 1 workflow, and 3 personas across operational (OpenAPI) and capability (Naftiko) dimensions

## Rules

- [Amazon HealthImaging Spectral Rules](rules/amazon-healthimaging-spectral-rules.yml) — 8 rules across 4 categories enforcing Amazon HealthImaging API conventions

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
