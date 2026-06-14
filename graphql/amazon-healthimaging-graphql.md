# AWS HealthImaging GraphQL Schema

## Overview

This directory contains a conceptual GraphQL schema for the AWS HealthImaging service. AWS HealthImaging is a HIPAA-eligible service that enables healthcare providers and software partners to store, access, and analyze medical images (DICOM) at scale. The service supports sub-second image retrieval and scales from hundreds to millions of medical images.

The schema is derived from the AWS HealthImaging REST API, the DICOM data model, and the HealthImaging Developer Guide at https://docs.aws.amazon.com/healthimaging/latest/devguide/.

## Files

- `amazon-healthimaging-schema.graphql` — Full GraphQL schema with 55+ named types covering the complete HealthImaging and DICOM data model.

## Data Model

### Core Resources

| Type | Description |
|------|-------------|
| `Datastore` | Top-level repository for image sets. Each datastore holds all image sets for an organization or use case. |
| `DatastoreProperties` | Lightweight summary of a datastore returned in list operations. |
| `ImageSet` | A logical collection of DICOM images associated with a study or series. |
| `ImageSetVersion` | A versioned snapshot of an image set produced by import, copy, or update. |
| `ImageSetMetadata` | Structured DICOM metadata document attached to an image set. |
| `ImageFrame` | An individual image frame (pixel data unit) within an image set. |
| `PixelData` | Descriptor for the raw pixel data of an image frame, including S3 URI and checksum. |

### DICOM Hierarchy

The schema follows the standard DICOM information hierarchy:

```
Patient
  └── DICOMStudy
        └── DICOMSeries
              └── DICOMInstance
                    └── ImageFrame
                          └── PixelData
```

| Type | Description |
|------|-------------|
| `Patient` | Demographic information extracted from DICOM metadata (PatientID, name, birthdate, sex). |
| `DICOMStudy` | A DICOM study grouping all images from a single imaging encounter (StudyInstanceUID). |
| `DICOMSeries` | A DICOM series grouping images acquired under the same protocol and modality. |
| `DICOMInstance` | A single DICOM SOP instance (image file) within a series. |
| `DICOMMetadata` | Raw DICOM metadata container for an image set. |
| `DICOMAttribute` | A single DICOM attribute with tag, VR, and value. |
| `DICOMTag` | A DICOM data element tag (group + element + keyword). |
| `InstanceMetadata` | Instance-level metadata summary including pixel dimensions and representation. |

### Clinical and Equipment Types

| Type | Description |
|------|-------------|
| `Equipment` | Imaging device details: manufacturer, model, station name, institution. |
| `Acquisition` | Acquisition parameters: date/time, kVp, exposure, magnetic field strength, TR/TE. |
| `Modality` | Enum of DICOM modality codes (CT, MR, US, PT, XA, DX, CR, MG, etc.). |

### Import Jobs

| Type | Description |
|------|-------------|
| `ImportJob` | A DICOM bulk import job that ingests images from an Amazon S3 bucket. |
| `ImportJobStatus` | Enum: SUBMITTED, IN_PROGRESS, COMPLETED, FAILED. |
| `ImportJobSummary` | Lightweight summary for list operations. |
| `ImportJobError` | Error detail recorded for failed import files. |
| `Manifest` | Manifest document describing DICOM files in an import job. |
| `ManifestCollection` | A collection of DICOM file references within a manifest. |
| `ManifestDICOMItem` | A single DICOM file entry pointing to an S3 URI with DICOM UIDs. |

### Search Types

| Type | Description |
|------|-------------|
| `SearchCriteria` | Top-level search criteria containing filters and sort configuration. |
| `SearchFilter` | A filter with one or more values and a comparison operator. |
| `SearchFilterValue` | Filter value targeting DICOM identifiers or timestamps. |
| `SearchSort` | Sort configuration (field + order). |
| `SearchResult` | Paged list of image set summaries matching the search criteria. |
| `ImageSetSummary` | Lightweight image set entry in search results with key DICOM identifiers. |
| `DICOMSearch` | DICOM-specific search parameters (patientID, accessionNumber, study/series UIDs). |
| `SearchFilterOperator` | Enum: EQUAL, BETWEEN, LESS_THAN, GREATER_THAN, etc. |

### Mutation Result Types

| Type | Description |
|------|-------------|
| `CopyImageSet` | Result of copying an image set within or between datastores. |
| `ImageSetCopyProperties` | Source or destination properties returned by a copy operation. |
| `CopyImageSetInformation` | Bundle combining source and destination references for a copy request. |
| `CopySourceImageSetInformation` | Source image set identifier and version for a copy. |
| `CopyDestinationImageSetInformation` | Optional destination image set for a copy. |
| `DICOMCopies` | DICOM SOP instance attributes to include in a copy. |
| `UpdateImageSet` | Result of updating metadata on an existing image set. |
| `MetadataUpdate` | Metadata update payload (DICOM attribute inserts/removals or version revert). |
| `DICOMMetadataUpdates` | DICOM attribute update instructions within a metadata update. |
| `DeleteImageSet` | Result of deleting an image set. |

### Tagging

| Type | Description |
|------|-------------|
| `Tag` | A key-value tag on a HealthImaging resource. |
| `TagResource` | Result of a tag or untag operation including the resource ARN. |

### Enums

| Enum | Values |
|------|--------|
| `DatastoreStatus` | CREATING, CREATE_FAILED, ACTIVE, DELETING, DELETED |
| `ImageSetState` | ACTIVE, LOCKED, DELETED |
| `ImageSetWorkflow` | COPY, UPDATE, DELETE |
| `ImportJobStatus` | SUBMITTED, IN_PROGRESS, COMPLETED, FAILED |
| `ImageFrameType` | ORIGINAL, OVERLAY, ICON, THUMBNAIL |
| `SortOrder` | ASC, DESC |
| `Modality` | CT, MR, US, PT, NM, XA, DX, CR, MG, RF, SC, OT, SR, PR, KO, and more |
| `UpdateMetadataAction` | INSERT, REMOVE, FORCE_REMOVE |
| `SearchFilterOperator` | EQUAL, BETWEEN, LESS_THAN, GREATER_THAN, LESS_THAN_OR_EQUAL, GREATER_THAN_OR_EQUAL |

## Queries

| Query | Description |
|-------|-------------|
| `listDatastores` | List datastores optionally filtered by status. |
| `getDatastore` | Get properties of a specific datastore. |
| `getImageSet` | Get properties of an image set at an optional version. |
| `getImageSetMetadata` | Get structured DICOM metadata for an image set. |
| `listImageSetVersions` | List all versions of an image set. |
| `getImageFrame` | Retrieve a specific image frame with pixel data descriptor. |
| `searchImageSets` | Search image sets in a datastore by DICOM identifiers or timestamps. |
| `getDICOMImportJob` | Get status and details of a DICOM import job. |
| `listDICOMImportJobs` | List import jobs for a datastore optionally filtered by status. |
| `listTagsForResource` | List tags attached to a HealthImaging resource ARN. |

## Mutations

| Mutation | Description |
|----------|-------------|
| `createDatastore` | Create a new datastore with optional KMS key and tags. |
| `deleteDatastore` | Delete an empty datastore. |
| `startDICOMImportJob` | Start a bulk DICOM import from an S3 source. |
| `copyImageSet` | Copy an image set within or across datastores. |
| `updateImageSetMetadata` | Insert, remove, or revert DICOM metadata on an image set. |
| `deleteImageSet` | Delete an image set (moves to DELETED state). |
| `tagResource` | Add or overwrite tags on a resource ARN. |
| `untagResource` | Remove tags from a resource ARN. |

## References

- AWS HealthImaging Developer Guide: https://docs.aws.amazon.com/healthimaging/latest/devguide/
- AWS HealthImaging API Reference: https://docs.aws.amazon.com/healthimaging/latest/devguide/API_Reference.html
- DICOM Standard: https://www.dicomstandard.org/current
- AWS HealthImaging GitHub User Guide: https://github.com/awsdocs/aws-healthimaging-user-guide
- AWS HealthImaging Pricing: https://aws.amazon.com/healthimaging/pricing/
