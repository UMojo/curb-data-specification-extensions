# Curb Data Specification

## Table of Contents

- [Overview](#overview)
- [Curb Data Specification APIs](#curb-data-specification-apis)
  - [Structure](#structure)
  - [Modularity](#modularity)
  - [CDS OpenAPI Schema](#cds-openapi-schema)
  - [MDS Overlap](#mds-overlap)
- [Work in Progress](#work-in-progress)
- [Get Involved](#get-involved)
- [Versions](#versions)
  - [Technical Information](#technical-information)
- [Membership](#membership) 
- [Organizations Using CDS](#organizations-using-cds) 
- [Data Privacy](#data-privacy)
- [Use Cases](#use-cases)

# Overview

The Curb Data Specification (**CDS**), a project of the [Open Mobility Foundation](http://www.openmobilityfoundation.org/) (**OMF**), is a data standard and set of Application Programming Interfaces (APIs) that helps cities manage and companies use dynamic curb zones that optimize loading activities of people and goods, and measure the impact of these programs.

Urban curb is a valuable, limited, and often under-managed part of the public right of way. Curb demand is growing, including from commercial activity like passenger pickup/drop off, traditional and on-demand delivery services, new mobility programs like scooters, bikeshare, and carshare, and goods and freight delivery. While cities have made some progress in digitizing their curb and using curb data, more tools are needed to proactively manage curbs and sidewalks, and to deliver more public value from this scarce resource. CDS can provide a mechanism for expressing static and dynamic regulations, measuring activity at the curb, and developing policies that create more accessible, useful curbs.

**CDS** is a key piece of digital infrastructure that supports the effective implementation of curb policies in cities and for curb users. For a high level overview and visuals, see the **[About CDS](https://www.openmobilityfoundation.org/about-cds/)** page on the OMF website.

![Curb Data Specification Logo](https://i.imgur.com/iGPCZyQ.png)

[Top][toc]

# Curb Data Specification APIs

CDS is at its core a set of Application Programming Interfaces (APIs) and endpoints within those APIs, which allow information to flow between organizations managing and using curb places. It includes the following three APIs, with multiple endpoints under each API:

---

<a href="/curbs/"><img src="https://i.imgur.com/ta5z101.png" width="80" align="left" alt="CDS Curbs Icon" border="0"></a>

The [`Curbs`](/curbs/) API is a standard way for cities to digitally publish curb locations and regulations, which can be shared with the public and with companies using curb space. It defines curb policies, curb zones, spaces in zones, and areas around curbs, and is used by Events and Metrics. 

---

<a href="/events/"><img src="https://i.imgur.com/p6Lp7Rv.png" width="80" align="left" alt="CDS Events Icon" border="0"></a>

The [`Events`](/events/) API is a standard way to transmit real-time and historic commercial events happening at the curb to cities. Event data can be derived from company data feeds, on street sensors, session payments, company check-ins, in-person parking personnel, and/or other city data sources. Connected to Curbs and used by Metrics.

---

<a href="/metrics/"><img src="https://i.imgur.com/9NkdqGs.png" width="80" align="left" alt="CDS Metrics Icon" border="0"></a>

The [`Metrics`](/metrics/) API is a way to track curb usage session details and define common calculation methodologies to measure historic dwell time, occupancy, usage and other aggregated statistics. It defines sessions and aggregates data derived from raw Events data.

---

CDS is a data exchange format and a translation layer between internal systems and external entities using data feeds. It is not expected that CDS will be the format used internally to store curb regulations in a city. The internal storage format is something different, and a subset of that data should be able to be converted to CDS for publishing out to the public and curb users. 

Many parts of the CDS definitions and APIs align across each other. In these cases, consolidated information can be found on the [General Information](/general-information.md) page.

## Structure

CDS contains a series of connected endpoints and fields beneath each interconnected API.

<p align="center"><img src="https://i.imgur.com/4DxMu6t.png" width="600" align="center" /></p>

## Modularity

CDS is designed to be a modular and flexible specification. Regulatory agencies can use the components of the API that are appropriate for their needs. An agency may choose to use only Curbs, while others may use Curbs, Events, and Metrics. Even within each API many endpoints and fields are optional. This design allows agencies, software and hardware companies, and curb users to use what's appropriate for their use cases, work within their operational capabilities, and text CDS in their pilot projects.

![CDS APIs and Endpoints](https://i.imgur.com/wlSeEa0.png)

## CDS OpenAPI Schema
For CDS data and feed validation, please see the [OpenAPI schema description](https://github.com/openmobilityfoundation/cds-openapi). Interactive OpenAPI documentation for the CDS APIs, endpoints, fields, and data objects is also available on OMF's [Stoplight Interactive Documentation](https://openmobilityfnd.stoplight.io/docs/cds-openapi/83teyinnn1py6-curb-api) page.
## MDS Overlap

Like the [Mobility Data Specification](https://github.com/openmobilityfoundation/mobility-data-specification/) (MDS), the CDS will be consumed by both cities and transportation providers operating in the public right of way. In many cases, the same mobility providers using curbs with CDS may also be interacting with other OMF [MDS Policy](https://github.com/openmobilityfoundation/mobility-data-specification/tree/main/policy), [MDS Provider](https://github.com/openmobilityfoundation/mobility-data-specification/tree/main/provider), and [MDS Agency](https://github.com/openmobilityfoundation/mobility-data-specification/tree/main/agency) data objects within the same [MDS Jurisdiction](https://github.com/openmobilityfoundation/mobility-data-specification/tree/main/jurisdiction) or [MDS Geography](https://github.com/openmobilityfoundation/mobility-data-specification/tree/main/geography), and using similar [MDS Metrics](https://github.com/openmobilityfoundation/mobility-data-specification/tree/main/metrics). Consistent with the Technology Design Principles codified in the [Technology Council's](https://github.com/openmobilityfoundation/governance/wiki/Technology-Council) OMF [Architectural Landscape Document](https://github.com/openmobilityfoundation/governance/blob/main/documents/OMF-MDS-Architectural-Landscape.pdf), the members of this working group are making reasonable best efforts to ensure that work is both _modular_ and _inter operable_ with other technology managed by the OMF as to avoid duplication and downstream implementation complexity. The first version of CDS intentionally has no direct connetions to MDS which allowed it to be created based strictly on real-world curb use cases and needs, but may align directly in future versions.

[Top][toc]

# Work in Progress

The CDS is a work in progress and is under ongoing development by the community under the guidance of the [Working Group Steering Committee](https://github.com/openmobilityfoundation/curb-data-specification/wiki) on specific [discussion topics](https://github.com/openmobilityfoundation/curb-data-specification/discussions) and bi-weekly [public meetings](https://github.com/openmobilityfoundation/curb-data-specification/wiki#meeting-agendas) around a specific [Scope of Work](https://docs.google.com/document/d/1yY5pRiiei8seVxXOmcYiqCA7wx7DueeatJnjbZoV3hU/). The Steering Committee has created supplementary resources like [Architectural Decisions](https://github.com/openmobilityfoundation/curb-data-specification/wiki/Curb-Architectural-Decisions), [Use Cases](https://github.com/openmobilityfoundation/curb-data-specification/wiki/CDS-Use-Cases), [Privacy Guidance](https://docs.google.com/document/d/117kJhXp6ldv7KHq7k9wHONHVVHw00xweaHpORVu_c10/edit?usp=sharing), [Policy Language Guidance](https://github.com/openmobilityfoundation/governance/blob/main/technical/OMF-CDS-Policy-Language-Guidance.md), and a [Pilot Project Guide](https://docs.google.com/document/d/1Mb1wpy4AFJ1MLvDpSIJsii4_1j2JC16NxNUVPI5BMNM/edit?usp=sharing). After the CDS 1.0 launch, the public working group will incorporate feedback from on-the-ground pilot programs into future versions.

[Top][toc]

# Get Involved

The OMF’s [Curb Management Working Group](https://github.com/openmobilityfoundation/curb-data-specification/wiki), led by a steering committee of individuals representing public agencies and private sector companies, has developed this data specification for curb usage.  The CDS encompasses digitized curb regulations, real time and historic event information, and utilization metrics. The specification allows sharing of this data between cities, commercial companies, and the public. Get involved by siging up to the [Curb Mailing List](https://groups.google.com/a/openmobilityfoundation.org/g/wg-curb).

The Curb Data Specification is an open source project with all development taking place on GitHub. Read our **[Community Wiki](https://github.com/openmobilityfoundation/curb-data-specification/wiki)** to get started. Comments and ideas can be shared by [starting a discussion](https://github.com/openmobilityfoundation/curb-data-specification/discussions), [creating an issue](https://github.com/openmobilityfoundation/curb-data-specification/issues), and specific changes can be suggested by [opening a pull request](https://github.com/openmobilityfoundation/curb-data-specification/pulls). Before contributing, please review our OMF [CONTRIBUTING page](https://github.com/openmobilityfoundation/governance/blob/main/CONTRIBUTING.md) and our [CODE OF CONDUCT page](https://github.com/openmobilityfoundation/governance/blob/main/CODE_OF_CONDUCT.md) to understand guidelines and policies for participation.

For questions about CDS please contact by email at [info@openmobilityfoundation.org](mailto:info@openmobilityfoundation.org) or [on our website](https://www.openmobilityfoundation.org/get-in-touch/). Media inquiries to [media@openmobilityfoundation.org](mailto:media@openmobilityfoundation.org).

[Top][toc]

# Versions

CDS has a **current release** (version 1.0.0), and an **upcoming releases** in development. For a full list of releases, their status, recommended versions, and timelines, see the [Official CDS Releases](https://github.com/openmobilityfoundation/curb-data-specification/wiki/Releases) page.

The OMF provides guidance on upgrading for cities, providers, and software companies, and sample permit language for cities. See our [CDS Version Guidance](https://github.com/openmobilityfoundation/governance/blob/main/technical/OMF-CDS-Version-Guidance.md) for best practices on how and when to upgrade CDS as new versions become available. Our complimentary [CDS Policy Language Guidance](https://github.com/openmobilityfoundation/governance/blob/main/technical/OMF-CDS-Policy-Language-Guidance.md) document is for cities writing CDS into their operating policy and includes sample policy language.

## Technical Information

The latest CDS release is in the [`main`](https://github.com/openmobilityfoundation/curb-data-specification/tree/main) branch, and development for the next release occurs in the [`dev`](https://github.com/openmobilityfoundation/curb-data-specification/tree/dev) and other branches.

The CDS specification is versioned using Git tags and [semantic versioning](https://github.com/openmobilityfoundation/governance/blob/main/technical/ReleaseGuidelines.md#versioning). 

* [Latest Release Branch](https://github.com/openmobilityfoundation/curb-data-specification/tree/main) (main)
* [Development Branch](https://github.com/openmobilityfoundation/curb-data-specification/tree/dev) (dev)
* [All GitHub Releases](https://github.com/openmobilityfoundation/curb-data-specification/releases)
* [CDS Releases](https://github.com/openmobilityfoundation/curb-data-specification/wiki/Releases) - current/recommended versions, timeline
* [Release Guidelines](https://github.com/openmobilityfoundation/governance/blob/main/technical/ReleaseGuidelines.md)

[Top][toc]

# Membership

OMF Members (public agencies and commercial companies) have additional participation opportunities with leadership roles within our OMF [governance](https://github.com/openmobilityfoundation/governance#omf-scope-of-work):

- [Board of Directors](https://www.openmobilityfoundation.org/about/)
- [Privacy, Security, and Transparency Committee](https://github.com/openmobilityfoundation/privacy-committee)
- [Technology Council](https://github.com/openmobilityfoundation/governance/wiki/Technology-Council)
- [Strategy Committee](https://github.com/openmobilityfoundation/governance/wiki/Strategy-Committee)
- [Advisory Committee](https://github.com/openmobilityfoundation/governance/wiki/Advisory-Committee)
- Steering committees of all [Working Groups](https://github.com/openmobilityfoundation/mobility-data-specification/wiki#omf-meetings), currently:
  - [MDS Working Group](https://github.com/openmobilityfoundation/mobility-data-specification/wiki/MDS-Working-Group)
  - [Curb Working Group](https://github.com/openmobilityfoundation/curb-data-specification/wiki)

Read about [how to become an OMF member](https://www.openmobilityfoundation.org/how-to-become-a-member/), [how to get involved and our governance model](https://www.openmobilityfoundation.org/how-to-get-involved-in-the-open-mobility-foundation/), and [contact us](https://mailchi.mp/openmobilityfoundation/membership) for more details. 

[Top][toc]

# Organizations Using CDS

Cities and public agencies, technology companies, commercial curb users, and operators are using CDS now and in the near term.  

- See our **[list of organizations using CDS](https://github.com/openmobilityfoundation/curb-data-specification/wiki#cds-users)**.

Please let us know [via our website](https://www.openmobilityfoundation.org/get-in-touch/) if you are an organization using CDS so we can add you to the list.

If you are a data source operator, you may also add yourself to the [operator list](/data_source_operators.csv) for a global ID and website link. Let us know [via our website](https://www.openmobilityfoundation.org/get-in-touch/) or find out how to do it yourself in our [Adding a CDS Data Source Operator ID](https://github.com/openmobilityfoundation/curb-data-specification/wiki/Adding-a-CDS-Data-Source-Operator-ID) help document.

[Top][toc]

# Data Privacy

CDS includes information about commercial vehicles using select curb zones in a city to allow agencies to regulate curb use and policy in the public right of way and to conduct analysis for program improvements. While CDS is not designed to convey any personal information and is focused on commerical curb activity, some uses of some fields can be sensitive. The OMF community has created a number of resources to help cities, fleet operators, and software companies handle vehicle data safely:

* [CDS Privacy Guidance](https://docs.google.com/document/d/1nujWaj1ScxQ-1I9_BGrMKZ_mV_8mbk8tG_C21CQO7Cw/edit?usp=sharing) - identifies relevant data in CDS, use cases, and provides suggestions on the safe handling of this data.
* [Privacy Guide for Cities](https://github.com/openmobilityfoundation/governance/raw/main/documents/OMF-MDS-Privacy-Guide-for-Cities.pdf) - guide that covers essential privacy topics and best practices
* [The Privacy Principles for Mobility Data](https://www.mobilitydataprivacyprinciples.org/) - principles endorsed by the OMF and other mobility organizations to guide the mobility ecosystem in the responsible use of data and the protection of individual privacy
* [Mobility Data State of Practice](https://github.com/openmobilityfoundation/privacy-committee/blob/main/products/state-of-the-practice.md) - real-world examples related to the handling and protection of MDS and other types of mobility data
* [CDS Use Cases](https://github.com/openmobilityfoundation/curb-data-specification/wiki/CDS-Use-Cases) - outlines real-world use cases, and how to use CDS to make them happen and why.

The OMF’s [Privacy, Security, and Transparency Committee](https://github.com/openmobilityfoundation/privacy-committee#welcome-to-the-privacy-security-and-transparency-committee) creates many of these resources, and advises the OMF on principles and practices that ensure the secure handling of mobility data. The committee – which is composed of both private and public sector OMF members – also holds regular public meetings, which provide additional resources and an opportunity to discuss issues related to privacy and mobility data. Learn more [here](https://github.com/openmobilityfoundation/privacy-committee#welcome-to-the-privacy-security-and-transparency-committee).

[Top][toc]

# Use Cases

How cities use CDS depends on a variety of factors: their transportation goals, existing services and infrastructure, and the unique needs of their communities. Cities are using CDS to create policy, manage curbs, and ensure the safe operation of vehicles in the public right of way. 

A list of use cases is useful to show what's possible with CDS, to see many use cases up front for privacy considerations, and to use for policy discussions and policy language. More details and examples can be seen on the [CDS Use Cases](https://github.com/openmobilityfoundation/curb-data-specification/wiki/CDS-Use-Cases).


[Top][toc]

[toc]: #table-of-contents
