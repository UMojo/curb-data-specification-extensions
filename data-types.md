# Curb Data Specification: **Data Types**

This CDS data types page catalogs the data objects (fields, types, requirements, descriptions) used across CDS APIs and endpoints.

## Table of Contents

- [External Reference](#external-reference)

## External Reference

An External Reference object describes a specific feature from a data feed or API that is relevant to the curb place via an external reference. This allows CDS users to reference other data feeds that impact the area, and see full details in the agency's data feed. Data feeds can be any existing standard (MDS, WzDX, CWZ, GTFS, GBFS, etc) or a custom feed.

An `external_reference` is a JSON array with the following fields within objects:

| Name   | Type   | Required/Optional   | Description   |
| ------ | ------ | ------------------- | ------------- |
| `data_feed_url` | URL | Required | An identifier for the source of the publicly or privately accessible data feed. This MUST be a full HTTPS URL pointing to the data feed which contains more information about the underlying work zone impacting the CDS place. |
| `field_name` | String | Required | The name of the data field that is referenced by `feature_ids`. E.g. "trip_id". |
| `feature_ids` | Array | Required | An array of one or more **ids** strings of a data feed that impacts the use of or relationship to a curb zone. The **ids** details are be provided in the referenced `data_feed_url`. |

[Top][toc]

[toc]: #table-of-contents
