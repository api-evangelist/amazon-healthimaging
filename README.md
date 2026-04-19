# Amazon HealthImaging (amazon-healthimaging)
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
