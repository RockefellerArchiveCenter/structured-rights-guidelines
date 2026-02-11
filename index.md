---
layout: docs
title:  "Creation, Maintenance and Use of Structured Rights Statements"
---
## Introduction

Structured rights are standardized, machine-readable metadata statements that document the legal and policy conditions governing the use, access, and management of collections. They capture information such as copyright status, donor-imposed restrictions, institutional access policies, and applicable time limits in a machine-actionable format. Structured rights statements and narrative rights notes have very different purposes: structured rights have fields that are based on controlled vocabularies that help systems automate workflows, while narrative notes provide contextual explanation for users. This document focuses on structured rights and their implementation at the RAC.

Structured rights as they are implemented at the RAC enable reliable automation and prevent unnecessary restrictions. They prevent undocumented assumptions about rights, ensure application of organizational policies, and enable rights management to scale beyond individual expertise. Ultimately, by centralizing creation and maintenance with a specialized Structured Rights Management Team, requiring formal approval by senior archival leadership, and embedding assignment within core accessioning, processing, and digitization workflows, the RAC ensures that rights metadata remains accurate, consistent, auditable, and aligned with institutional policy.

## What Structured Rights Do

Structured rights statements are assertions of rights, not records of information from which rights can be determined. In other words, the purpose of structured rights statements is to provide actionable information to a digital system, not to help humans make rights determinations on an ongoing basis.

There is a distinction between rights and permissions. Rights are entitlements allowed to people or institutions by copyright or other legally binding agreements. Permissions come from these rights, being powers or privileges granted, or restrictions placed on material by the legal rights. For instance, rights might stipulate a digitized letter may still be under copyright, and the rights-holder controls all reproduction or distribution. Permissions describe what the rights-holder lets an institution or person do with the materials, like digitization for preservation or access.

These permissions and restrictions are captured in machine-actionable representations of known rights conditions designed to convey what an archival repository is allowed, or not allowed, to do with an object or group of objects. These statements provide software systems with a way to automatically and consistently act upon them. This allows preservation and access systems to know what rights or permissions an object has and what they can do with it over time.

**What rights statements can do**

- Enable automated system behavior. They allow systems to decide what actions may be taken (providing access, migrating file formats, or deleting files) automatically.
- Support repeatable workflows. When rights are expressed in structured forms, access platforms can predict the desired long-term disposition of the objects.
- Reduce dependency on individual judgement. Structured rights statements help prevent siloing knowledge where only a few staff members understand how rights apply in practice and provide a framework for applying rights to new material.

**What rights statements cannot do**

- Replace legal interpretation. They express decisions made considering agreements, copyright statutes, or policy, but they do not determine whether these exist.
- Resolve ambiguity or make decisions automatically. If rights are unknown, contested, or complicated, a structured statement will not help determine the answer. A human still must create the rights statement and assign it to objects.
- Serve as the authoritative legal record. They may reference donor agreements, policy statements, or statutes, but they do not serve as an authoritative record.

## Structured Rights at the RAC

The RAC’s implementation of structured rights draws from established archival and digital preservation standards, including the [PREMIS Data Dictionary for Preservation Metadata](https://www.loc.gov/standards/premis/v3/), which provides a widely adopted model for expressing rights statements. The RAC has implemented structured rights statements based on PREMIS concepts in its local systems and policies, even though the rights statements may not be serialized as PREMIS-compliant XML documents.

When digital records — including both born-digital and digitized records — are stored in the RAC’s systems, structured rights systems which document both use (such as copyright status) and rights that govern access (such as donor-imposed or institutional restrictions) must also be added in the appropriate system. When applicable, these access conditions should be derived from a donor agreement and documented accordingly. In cases where no donor agreement exists, access conditions must instead be based on applicable institutional policies. Institutional policy–based access conditions must also be documented when they impose restrictions beyond those specified in a donor agreement. In such cases, both donor-derived and policy-derived access conditions may apply concurrently.

## Systems That Use Structured Rights at the RAC

The RAC’s systems support structured rights at different points in the archival, preservation, and access lifecycle. Together, they ensure that rights governing use and access are captured, maintained, and enforced consistently as materials move from acquisition through preservation and, where applicable, public access.

### ArchivesSpace

Structured rights information in ArchivesSpace focuses primarily on access and use conditions derived from donor agreements and institutional policy. The system does not use full PREMIS but models its structured rights sections on the PREMIS vocabulary. These rights statements document restrictions such as embargoes, access limitations, or special conditions that affect how materials may be accessed.

ArchivesSpace serves as both a source of user-facing descriptive information and a system for managing structured rights data. ArchivesSpace stores descriptive and structured rights data that is used by other systems in various ways.

Information about ArchivesSpace Rights Statement subrecords can be found on the [ArchivesSpace Wiki](https://archivesspace.atlassian.net/wiki/pages/viewpageattachments.action?pageId=815136782&preview=%2F815136782%2F864780289%2FRights%20Statements%20Sub-Record%20(v2.1.0%20and%20later)%20-%20Updated%20with%20track%20changes.docx).

### Archivematica

Archivematica manages the long-term preservation of digital objects and requires structured rights information as part of the ingest process. These structured rights support both use and access, ensuring that preserved objects retain clear, machine-actionable statements about copyright status and any access conditions that apply.

Rights information ingested into Archivematica is recorded using the PREMIS data dictionary, associated with preservation packages, and maintained alongside other preservation metadata. This allows rights information to persist over time tied to the actual digital objects.

You can read more about PREMIS rights statements in our [Archivematica documentation](https://docs.rockarch.org/archivematica-local).

### Aurora

Aurora is the RAC’s system for receiving, validating, and managing incoming born-digital transfers from donors and organizations. It plays a crucial role in ensuring that structured rights information is captured early in the born-digital materials lifecycle and associated with the correct objects and record types. Aurora validates transfers against organizational requirements, allows staff to review and appraise incoming records, and supports the accessioning of materials into other systems like Archivematica and ArchivesSpace.

Within Aurora, archivists can create, edit, and manage structured rights statements and associate them with specific record types defined for an organization. These rights statements reflect conditions drawn from donor agreements (and, where applicable, institutional policies) and are used to communicate what can and cannot be done with digital records as they enter the RAC’s preservation and access workflows. Aurora also captures structured rights information alongside metadata at the transfer stage so that it travels with the digital objects as they move through appraisal, accessioning, and preservation ingest. These structured rights statements are based on the PREMIS vocabulary but are not technically PREMIS because they are serialized in JSON rather than XML formats.

Some basic information about rights statements and how they are used within Aurora can be found in the [Aurora User Guide](https://docs.rockarch.org/aurora-docs#organization-administration).

### Aquila

Aquila serves as a centralized repository of structured rights statements used by downstream workflows such as the digitized image and audiovisual ingest pipelines. In addition to providing an API layer for systems integrations, Aquila provides an interface where authorized users can create and manage rights statements and groupings.

### Digitized Image and AV Ingest Pipelines

The digitized and audiovisual ingest pipelines are responsible for preparing materials for preservation and access. These pipelines require structured rights information to be assigned at ingest to ensure that digital objects enter the preservation system with clearly defined rights governing both use and access. The pipelines pull structured rights information directly from Aquila.

Structured rights captured or referenced during ingest are embedded into packages with digital objects. This ensures that rights information is consistently applied from the moment of ingest and remains actionable throughout the lifecycle of the digital object.

## How People Interact With Structured Rights at the RAC

The creation, maintenance, and application of structured rights statements at the RAC is a shared institutional responsibility. To ensure that rights information remains accurate, consistent, and actionable across systems, the RAC uses an approach comprising the Structured Rights Knowledge Team, management approvers, and staff responsible for assigning rights within specific workflows. Because the creation and assignment of structured rights happens at different points of the records lifecycle for born-digital and digitized records, these processes are managed by different organizational roles.

## Structured Rights Management Team

The Structured Rights Knowledge Team serves as the primary steward of all structured rights statements used within the RAC’s digital preservation and access ecosystems. This team is composed of selected members of the Processing Team, the Appraisal Archivist and Records Manager, and the Audiovisual Archivist.

The Structured Rights Knowledge Team is responsible for the full lifecycle of structured rights statements, including:

- **Creation** of new structured rights statements when new donor agreements, policies, or collection needs require them.
- **Updating** existing structured rights statements to reflect changes in policy, donor conditions, or institutional needs.
- **Deletion** of structured rights statements when they are no longer accurate, appropriate, or necessary.

Because structured rights statements are machine-actionable and underpin automated preservation and access workflows, the Structured Rights Knowledge Team plays a key role in ensuring that rights logic is expressed accurately, clearly, and consistently.

## Managing Structured Rights

For born-digital materials, the Appraisal Archivist is authorized to determine the appropriate access and use conditions based on donor agreements, institutional policy, and copyright status as part of the process of onboarding a donor organization. The Appraisal Archivist then creates, updates, or deletes structured rights statements in Aurora as necessary, and associates those statements with specific record types within a donor organization.

For digitized materials, the Structured Rights Knowledge Team prepares proposed changes and submits them for review and approval to the Assistant Director of Processing. Only after receiving approval from the Assistant Director of Processing may the team create, update, or delete a structured rights statement.

## Assigning Structured Rights

For born-digital materials, structured rights statements are automatically assigned during transfer to Aurora, based on the record type applied to the package of records by a donor organization.

For digitized materials, structured rights assignment occurs after digitization but before material is made available through access systems. Responsibility for assignment is distributed according to material type and program area.

For digitized audiovisual materials, the Audiovisual Archivist assigns the appropriate structured rights statements when materials are prepared for preservation and access.

For digitized textual and still image materials produced through ongoing digitization programs, the Digitization Program Manager is responsible for assigning structured rights statements.

If the Digitization Program Manager or Audiovisual Archivist have questions about assigning rights statements in the course of their work, those questions should be directed to the Assistant Director of Processing.

As with born-digital materials, these assignments are made using rights statements that have been created, reviewed, and approved through the Structured Rights Knowledge Team.