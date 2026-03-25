# DecisionOps Corpus Catalogue

**Version:** 2.9
**Status:** Approved (awaiting verification)
**Owner:** DecisionOps Architecture
**Purpose:** Provide the authoritative inventory and structural definition of the DecisionOps documentation corpus aligned to the approved corpus taxonomy.
**Doc Repository Location:** corpus/00_governance/catalogue/decisionops_corpus_catalogue.md
**Create Date:** 2026-03-14 (Document Origin Date — the date the catalogue concept was first created. Regenerated catalogue instances must retain this origin date.)

**Edit History**

**2026-03-14** v0.0 Initial Draft
**2026-03-14** v1.0 Initial approval (awaiting verification)
**2026-03-14** v1.1 Repository taxonomy and corpus navigation structure added
**2026-03-15** v1.2 Manifest-based catalogue regeneration rules added
**2026-03-15** v1.3 CI metadata validation rule added
**2026-03-19** v1.4 Registered NHIE Governance Architecture Specification v0.3 in 01_architecture/specification; updated white paper catalogue entries to current approved versions (Technical White Paper v2.1.1, Marketing White Paper v2.0, Investor White Paper v0.3, Future Evolutions v0.2.1); applied bold date convention to edit history
**2026-03-21** v1.5 Added ci and project_instructions to 00_governance structure; renamed enterprise-ai-workplace to enterprise_ai_workplace and added threat_landscape to 04_intelligence; added white_paper to 10_branding_and_marketing; added 02_schemas Drive URL to Section 4
**2026-03-21** v1.6 Registered Document Retirement Policy v1.0 in 00_governance/policies; added Section 10 Retired Documents
**2026-03-21** v1.7 Document Retirement Policy updated to v1.1 (version suffix rename at retirement)
**2026-03-21** v1.8 Document Retirement Policy updated to v1.2 (Section 4.1 reconstitution rule added)
**2026-03-21** v1.9 Document Retirement Policy updated to v1.3 (00_governance/catalogue exception; underscore version separators; derivative format exclusion; extension preservation rules)
**2026-03-21** v2.0 Removed imagery subfolders (png, social, svg) from 10_branding_and_marketing/branding; branding retained as governed document folder
**2026-03-21** v2.1 Worklist reconciliation: Section 7.2 expanded with four previously missing architecture documents now confirmed present; Section 7.3 added for operations and security documents; Section 9 updated — three Architecture Kernel items resolved, twelve worklist items added as Missing
**2026-03-22** v2.2 Group 2 governance file location assignments added to Section 7.1; Corpus Manifest version corrected to 1.3; Section 2 tree, Section 3 YAML, and Section 4 folder definition updated accordingly
**2026-03-22** v2.3 All repository location paths prefixed corpus/ per ADR-048; ADR-047 and ADR-048 registered in Section 7.1; Corpus Manifest updated to v1.5; Project Instructions updated to v1.1; self-reference updated to v2.3; Section 8 ADR location updated; Doc Repository Location updated
**2026-03-22** v2.4 Removed Google Drive URLs from Section 4; updated Section 4 intro to reflect repository as corpus truth post-migration
**2026-03-22** v2.5 Project Instructions updated to v1.2 (Section 22 PFS Sync Gate added)
**2026-03-23** v2.6 Registered architecture_phase0_boundaries.md in corpus/01_architecture/platform
**2026-03-24** v2.7  Updated decisionops_project_instructions.md version field from v1.2 to v1.4; added Section 10 deferred catalogue retirement reconciliation per Section 19 of project instructions
**2026-03-24** v2.8  Project Instructions corrected to v1.5 (Section 24 post-merge catalogue patch); Corpus Catalogue self-reference corrected from v2.5 to v2.8
**2026-03-25** v2.9  Registered ADR-049 and architecture_session_context.md; project instructions updated to v1.6; manifest updated to v1.6; registered decisionops-governance public repository reference

-----

# 1. Overview

This document represents the catalogue of the DecisionOps documentation corpus.

The catalogue provides a structured inventory of all documents and defines the operational structure of the documentation system used to support the DecisionOps platform.

The catalogue ensures that:

- all documentation assets are tracked
- repository locations are defined
- missing specifications remain visible
- corpus structure remains aligned with the approved taxonomy

The catalogue forms part of the documentation governance layer supporting **Specification Driven Development (SDD)**.

-----

# 2. Repository Structure

The corpus follows the structured taxonomy below. All numbered taxonomy folders are located under `corpus/` at the repository root per ADR-048.

```
decisionops-platform/
├── corpus/
│   ├── 00_governance
│   │   ├── adr
│   │   ├── catalogue
│   │   │   └── _retired
│   │   ├── ci
│   │   ├── freeze-manifest
│   │   ├── governance-model
│   │   ├── policies
│   │   └── project_instructions
│   ├── 01_architecture
│   │   ├── context-map
│   │   ├── domain-model
│   │   ├── platform
│   │   ├── positioning
│   │   ├── runtime
│   │   ├── specification
│   │   ├── subsystems
│   │   ├── threat-models
│   │   └── trust
│   ├── 02_schemas
│   │   ├── capability
│   │   ├── connector
│   │   ├── governance
│   │   ├── prompt
│   │   └── provenance
│   ├── 03_api
│   │   ├── admin
│   │   ├── connectors
│   │   └── control-plane
│   ├── 04_intelligence
│   │   ├── ecosystem
│   │   ├── enterprise_ai_workplace
│   │   ├── market
│   │   ├── regulatory
│   │   └── threat_landscape
│   ├── 05_security
│   │   ├── controls
│   │   ├── runtime-security
│   │   └── threat-model
│   ├── 06_operations
│   │   ├── deployment
│   │   ├── governance-packs
│   │   └── rollback
│   ├── 07_reference
│   │   ├── acronyms
│   │   ├── taxonomy
│   │   └── terminology
│   ├── 08_strategy
│   │   ├── investor
│   │   ├── positioning
│   │   └── roadmap
│   ├── 09_sources
│   │   ├── adr
│   │   ├── external research
│   │   ├── sdd research
│   │   └── uploaded papers
│   ├── 10_branding_and_marketing
│   │   ├── branding
│   │   ├── notebooklm
│   │   └── white_paper
│   └── 11_development_process
│       └── ai_sdd_evaluation
├── apps/
├── docs/
├── packages/
└── scripts/
```

-----

# 3. Machine-Readable Corpus Taxonomy

The YAML structure below is the **authoritative machine-readable representation** of the DecisionOps corpus taxonomy. CI validation, automated catalogue generation, and documentation integrity checks must treat this structure as the canonical definition of the repository hierarchy.

Indentation and nesting must exactly mirror the folder hierarchy defined in the repository structure above.

```yaml
DecisionOps_Corpus:
  root: corpus
  corpus/00_governance:
    - adr
    - catalogue:
      - _retired
    - ci
    - freeze-manifest
    - governance-model
    - policies
    - project_instructions

  corpus/01_architecture:
    - context-map
    - domain-model
    - platform
    - positioning
    - runtime
    - specification
    - subsystems
    - threat-models
    - trust

  corpus/02_schemas:
    - capability
    - connector
    - governance
    - prompt
    - provenance

  corpus/03_api:
    - admin
    - connectors
    - control-plane

  corpus/04_intelligence:
    - ecosystem
    - enterprise_ai_workplace
    - market
    - regulatory
    - threat_landscape

  corpus/05_security:
    - controls
    - runtime-security
    - threat-model

  corpus/06_operations:
    - deployment
    - governance-packs
    - rollback

  corpus/07_reference:
    - acronyms
    - taxonomy
    - terminology

  corpus/08_strategy:
    - investor
    - positioning
    - roadmap

  corpus/09_sources:
    - adr
    - external research
    - sdd research
    - uploaded papers

  corpus/10_branding_and_marketing:
    - branding
    - notebooklm
    - white_paper

  corpus/11_development_process:
    - ai_sdd_evaluation
```

-----

# 4. Folder Definitions

Each corpus folder is described below with its purpose and subfolder structure.

-----

### corpus/00_governance

Catalogue, policies, freeze manifest, project control and corpus governance.

Subfolders

- adr
- catalogue (_retired)
- ci
- freeze-manifest
- governance-model
- policies
- project_instructions

-----

### corpus/01_architecture

Architecture maps, domain models, system context maps and platform structural design.

Subfolders

- context-map
- domain-model
- platform
- positioning
- runtime
- specification
- subsystems
- threat-models
- trust

-----

### corpus/02_schemas

Canonical schema definitions and schema design guidance.

Subfolders

- capability
- connector
- governance
- prompt
- provenance

-----

### corpus/03_api

External and internal API and interface specifications.

Subfolders

- admin
- connectors
- control-plane

-----

### corpus/04_intelligence

Ecosystem intelligence, industry monitoring and environmental analysis.

Subfolders

- ecosystem
- enterprise_ai_workplace
- market
- regulatory
- threat_landscape

-----

### corpus/05_security

Security architecture, threat modelling inputs and defensive architecture.

Subfolders

- controls
- runtime-security
- threat-model

-----

### corpus/06_operations

Deployment procedures, rollback processes and governance pack operations.

Subfolders

- deployment
- governance-packs
- rollback

-----

### corpus/07_reference

Acronyms, taxonomy and terminology reference materials.

Subfolders

- acronyms
- taxonomy
- terminology

-----

### corpus/08_strategy

Strategic positioning documents, investor narratives and platform direction.

Subfolders

- investor
- positioning
- roadmap

-----

### corpus/09_sources

Uploaded external research artefacts and reference materials.

Subfolders

- adr
- external research
- sdd research
- uploaded papers

-----

### corpus/10_branding_and_marketing

Brand assets, marketing materials and visual identity resources.

Subfolders

- branding
- notebooklm
- white_paper

Note: imagery assets (png, svg, social) have been removed from the corpus. The `branding` subfolder is reserved for brand governance documents (guidelines, standards, frameworks).

-----

### corpus/11_development_process

Development process documentation including SDD workflows and evaluation frameworks.

Subfolders

- ai_sdd_evaluation

-----

### External Repositories

| Repository | URL | Purpose |
|---|---|---|
| decisionops-governance | https://github.com/jamieco/decisionops-governance | Public governance interface — bootstrap verification files |

-----

# 5. Corpus Validation Rules

To maintain structural integrity the DecisionOps documentation corpus follows explicit validation rules.

**Rule 1 — Catalogue Registration**

Every governed document must appear in the **DecisionOps Corpus Catalogue**.

**Rule 2 — Catalogue Resolution**

Every catalogue entry must resolve to a real document in the repository at the location defined by the *Doc Repository Location* field.

**Rule 3 — Metadata Consistency**

Document metadata must match the catalogue entry metadata including:

- Version
- Status
- Doc Repository Location

**Rule 4 — Structural Compliance**

All documents must be stored within `corpus/` at the repository root. Numbered taxonomy folders must not exist outside `corpus/`.

**Rule 5 — Missing Document Visibility**

Missing documents must be explicitly recorded using:

`Status: Missing`

These rules ensure the documentation system remains auditable, deterministic and ready for automated CI validation during Specification Driven Development.

### CI Enforcement Rules

```yaml
ci_orphan_document_detection:
  description: Detect files present in the repository that are not registered in the corpus catalogue.

  validation_steps:
    - scan_repository_tree
    - load_corpus_catalogue
    - compare_repository_files_to_catalogue_entries

  failure_conditions:
    - orphan_document_detected

  enforcement:
    fail_ci_on_orphan_document: true

ci_catalogue_missing_document_detection:
  description: Detect catalogue entries that reference documents not present in the repository.

  validation_steps:
    - load_corpus_catalogue
    - scan_repository_tree
    - compare_catalogue_entries_to_repository_files

  failure_conditions:
    - catalogue_entry_without_document

  enforcement:
    fail_ci_on_missing_document: true

ci_metadata_validation:
  description: Validate that document metadata fields match the catalogue entry and required governance schema.

  validation_steps:
    - scan_repository_documents
    - extract_document_metadata
    - load_corpus_catalogue
    - compare_metadata_to_catalogue_entries

  failure_conditions:
    - metadata_missing_required_fields
    - metadata_version_mismatch
    - metadata_status_mismatch
    - metadata_location_mismatch

  enforcement:
    fail_ci_on_metadata_validation_error: true
```

-----

# 6. Corpus Catalogue Framework

The DecisionOps Corpus Catalogue provides the authoritative index of all documents in the corpus.

The catalogue exists to:

- maintain corpus integrity
- record missing documents
- track document status
- enable governance visibility

Where a document is still missing, the gap is recorded rather than silently omitted.

-----

# 7. Catalogue Entry Structure

The schema definition for catalogue entries is formally defined in:

```
corpus/00_governance/catalogue/catalogue_schema.yaml
```

This schema provides the machine-readable validation rules for catalogue entries and is used by CI tooling to verify catalogue integrity.

Each catalogue entry must follow a strict five-column schema to ensure reliable rendering across markdown processors and compatibility with automated tooling.

## 7.1 Governance Documents

|Document Name                         |Type      |Status  |Version|Repository Location                      |
|--------------------------------------|----------|--------|-------|-----------------------------------------|
|DecisionOps Project Instructions      |Governance|Approved|1.6    |corpus/00_governance/project_instructions|
|Corpus Manifest                       |Governance|Approved|1.6    |corpus/00_governance/freeze-manifest     |
|Corpus Catalogue                      |Governance|Approved|2.8    |corpus/00_governance/catalogue           |
|DecisionOps CI Documentation Guard    |Governance|Draft   |0.1    |corpus/00_governance/ci                  |
|Repository Migration Map              |Governance|Approved|1.0    |corpus/00_governance/project_instructions|
|Document Retirement Policy            |Governance|Approved|1.3    |corpus/00_governance/policies            |
|ADR Index and Status Register         |Governance|Approved|1.1    |corpus/00_governance/adr                 |
|DecisionOps ADR Taxonomy Map          |Governance|Approved|1.0    |corpus/00_governance/adr                 |
|Markdown Canonical Source Policy      |Governance|Approved|1.0    |corpus/00_governance/policies            |
|Documentation Versioning Policy       |Governance|Approved|1.0    |corpus/00_governance/policies            |
|Baseline Freeze and Release Policy    |Governance|Approved|1.0    |corpus/00_governance/policies            |
|Documentation Lifecycle and CUR Policy|Governance|Approved|1.0    |corpus/00_governance/governance-model    |
|Terminology and Naming Governance     |Reference |Approved|1.0    |corpus/07_reference/terminology          |
|README                                |Governance|Approved|1.1    |Corpus Root                              |
|ADR-047 Phase 0 Scaffold Contract     |ADR       |Approved|1.0    |corpus/00_governance/adr                 |
|ADR-048 Corpus Subdirectory Root      |ADR       |Approved|1.0    |corpus/00_governance/adr                 |
|ADR-049 Public Governance Repository and Bootstrap Sync|ADR|Approved|1.0|corpus/00_governance/adr|

## 7.2 Architecture Specifications

|Document Name                                                      |Type                      |Status  |Version|Repository Location                 |
|-------------------------------------------------------------------|--------------------------|--------|-------|------------------------------------|
|Non-Human-Initiated Execution Governance Architecture Specification|Architecture Specification|Draft   |0.3    |corpus/01_architecture/specification|
|Autonomous Experiment Loop Governance Architecture                 |Architecture Specification|Approved|1.0    |corpus/01_architecture/specification|
|Capability Registry Architecture                                   |Architecture Specification|Approved|1.0    |corpus/01_architecture/trust        |
|Policy Reasoning Engine Architecture                               |Architecture Specification|Approved|1.0    |corpus/01_architecture/runtime      |
|Governance Runtime Architecture                                    |Architecture Specification|Draft   |1.0    |corpus/01_architecture/runtime      |
|Intent Integrity Architecture Specification                        |Architecture Specification|Approved|1.0    |corpus/01_architecture/specification|
|Phase 0 Platform Architecture Boundaries                          |Architecture             |Approved|1.0    |corpus/01_architecture/platform     |
|Architecture Session Context                                       |Architecture             |Approved|1.0    |corpus/01_architecture/platform     |

## 7.3 Operations and Security

|Document Name                      |Type                 |Status|Version|Repository Location              |
|-----------------------------------|---------------------|------|-------|---------------------------------|
|Internal Service Contract Map      |Architecture         |Draft |1.0    |corpus/01_architecture/subsystems|
|Event Interface Specification      |Interface Standard   |Draft |1.0    |corpus/01_architecture/subsystems|
|Security Architecture              |Security Architecture|Draft |1.0    |corpus/05_security/controls      |
|Threat Model Pack                  |Security             |Draft |1.0    |corpus/05_security/threat-model  |
|AI Security Layer Architecture     |Security Architecture|Draft |1.0    |corpus/05_security/controls      |
|Rollout and Rollback Strategy      |Operations           |Draft |1.0    |corpus/06_operations/rollback    |
|Staging and Preview Deployment Flow|Operations           |Draft |1.0    |corpus/06_operations/deployment  |

## 7.4 Strategy and Positioning

|Document Name                                       |Type                  |Status  |Version|Repository Location           |
|----------------------------------------------------|----------------------|--------|-------|------------------------------|
|DecisionOps Platform Technical White Paper          |Technical White Paper |Approved|2.1.1  |corpus/08_strategy/positioning|
|DecisionOps Platform Marketing White Paper          |Marketing White Paper |Approved|2.0    |corpus/08_strategy/positioning|
|DecisionOps Platform Investor White Paper           |Investor White Paper  |Approved|0.3    |corpus/08_strategy/investor   |
|DecisionOps Platform Future Evolutions              |Strategic Exploration |Approved|0.2.1  |corpus/08_strategy/positioning|
|DecisionOps Platform White Paper Technical Alignment|Internal Alignment    |Draft   |2.0    |corpus/08_strategy/positioning|
|DecisionOps Platform White Paper Marketing Alignment|Internal Alignment    |Draft   |2.0    |corpus/08_strategy/positioning|
|DecisionOps Reference Architecture White Paper      |Reference Architecture|Draft   |1.0    |corpus/08_strategy/positioning|
|DecisionOps Analyst Briefing Pack                   |Analyst Briefing      |Draft   |1.0    |corpus/08_strategy/positioning|

-----

# 8. ADR Library

The ADR library represents the permanent architecture decision record.

Location

```
corpus/00_governance/adr
```

All architecture-level changes must be recorded in this library.

The following ADR items are outstanding, having been identified as open governance design choices in the NHIE Governance Architecture Specification v0.3. Each must be resolved and recorded in the ADR library before implementation of the affected components.

|ADR Item                                                               |Source                   |Status|
|-----------------------------------------------------------------------|-------------------------|------|
|Supervised continuation window duration and maximum                    |NHIE Spec v0.3 Section 14|Open  |
|Activation chain depth thresholds by risk tier                         |NHIE Spec v0.3 Section 14|Open  |
|Temporal chain depth limit by risk tier                                |NHIE Spec v0.3 Section 14|Open  |
|Authority Continuity Cache validity window (standard and single-person)|NHIE Spec v0.3 Section 14|Open  |
|Corroboration source requirements by risk tier and integration posture |NHIE Spec v0.3 Section 14|Open  |
|Must-route assessment sub-deadline                                     |NHIE Spec v0.3 Section 14|Open  |
|Single-person extended re-validation window                            |NHIE Spec v0.3 Section 14|Open  |
|Trigger rate limit and burst threshold defaults                        |NHIE Spec v0.3 Section 14|Open  |
|Cost envelope advisory threshold                                       |NHIE Spec v0.3 Section 14|Open  |
|Re-attestation cycle maximum interval                                  |NHIE Spec v0.3 Section 14|Open  |
|Tier 2 self-modification reflection window                             |NHIE Spec v0.3 Section 14|Open  |
|Tier 3 self-modification reflection window                             |NHIE Spec v0.3 Section 14|Open  |
|Signal source degraded trust threshold                                 |NHIE Spec v0.3 Section 14|Open  |

-----

# 9. Missing Document Policy

The corpus catalogue must explicitly record missing documents.

A document gap must never be hidden by omission.

The following documents are defined by the architecture corpus but not yet produced. They are recorded here as open gaps.

|Document                                         |Type               |Status |Required By                  |
|-------------------------------------------------|-------------------|-------|-----------------------------|
|Governance Decision Engine Architecture          |Architecture       |Missing|Architecture Kernel          |
|Security Runtime Architecture                    |Architecture       |Missing|Architecture Kernel          |
|Approval Identity and Authority Model            |Architecture       |Missing|Architecture Kernel          |
|Authorisation Authority Registry Schema          |Schema             |Missing|NHIE Spec v0.3               |
|Activation Source Registry Schema                |Schema             |Missing|NHIE Spec v0.3               |
|Standing Execution Authorisation Schema          |Schema             |Missing|NHIE Spec v0.3               |
|Activation Context Envelope Schema               |Schema             |Missing|NHIE Spec v0.3               |
|Authority Lifecycle Signal Standard Specification|Interface Standard |Missing|NHIE Spec v0.3               |
|Founding Governance Instrument Specification     |Governance Standard|Missing|NHIE Spec v0.3               |
|Integration Coverage Declaration Schema          |Schema             |Missing|NHIE Spec v0.3               |
|Governance Dependency Security Classification    |Governance         |Missing|NHIE Spec v0.3               |
|Domain Event Taxonomy                            |Architecture       |Missing|Architecture Kernel          |
|Data and Persistence Architecture                |Architecture       |Missing|Architecture Kernel          |
|Tenant and Workspace Model                       |Architecture       |Missing|Architecture Kernel          |
|Scope Configuration Model                        |Architecture       |Missing|Architecture Kernel          |
|ADR Review and Maturity Policy                   |Governance         |Missing|corpus/00_governance/policies|
|Prompt Builder UX Specification                  |UX Specification   |Missing|Architecture Kernel          |
|Capability Authoring UX Specification            |UX Specification   |Missing|Architecture Kernel          |
|Approval Workflow Architecture                   |Architecture       |Missing|Architecture Kernel          |
|Observability and Telemetry Specification        |Architecture       |Missing|Architecture Kernel          |
|GovernancePack Schema                            |Schema             |Missing|corpus/06_operations         |
|Provider Risk Intelligence Policy                |Governance         |Missing|corpus/04_intelligence       |
|DecisionOps Update Advisor Specification         |Architecture       |Missing|corpus/04_intelligence       |

-----

# 10. Retired Documents

This section is the authoritative inventory of all documents that have been formally retired from the corpus under the Document Retirement Policy.

Retired documents remain permanently discoverable here. They must not be removed from this section.

|Document Name|Type|Retired Date|Superseded By|Original Location|Retirement Location|
|-------------|----|------------|-------------|-----------------|-------------------|

No documents have been retired at this version. Retroactive retirement entries for documents found in pre-policy `_retired` folders will be added as part of the GitHub migration baseline commit.

### 10.1 Deferred Catalogue Retirement Reconciliation — Pre-Migration Intermediate Versions

**Governance authority:** Section 19, `decisionops_project_instructions.md` v1.4
**Retirement point:** Migration baseline freeze — commit `fc84c16`, 2026-03-23
**Reconciliation date:** 2026-03-24

|Field                       |Value                                                                            |
|----------------------------|---------------------------------------------------------------------------------|
|Document                    |`decisionops_corpus_catalogue.md`                                                |
|Versions covered            |All intermediate versions from initial creation through v2.2 (migration baseline)|
|Status                      |Retired                                                                          |
|Retired by                  |Migration baseline freeze (commit `fc84c16`, 2026-03-23)                         |
|Physical files in `_retired`|None — deferred retirement per Section 19                                        |
|Retirement folder           |`00_governance/catalogue/_retired/` (reserved; no files present)                 |

**Governance note:** Intermediate versions of `decisionops_corpus_catalogue.md`
produced during the pre-GitHub migration phase were not individually retired
through the Drive corpus, consistent with Section 19 of the project
instructions. The migration baseline commit (`fc84c16`, 2026-03-23)
constitutes the first formal retirement point for all pre-migration catalogue
versions. This entry is a catalogue-record reconciliation only; no files are
physically present in `_retired`. Full retirement discipline — physical file
placement in `_retired` with version suffix per Section 18 — applies to all
post-migration catalogue versions.

-----

# 11. Catalogue Regeneration From Manifest

To support automation, the corpus catalogue may be regenerated from the **Corpus Integrity Manifest**.

Automated tooling may therefore:

- read `corpus_manifest.yaml`
- scan the repository structure
- validate folder compliance
- detect missing or uncatalogued documents
- update catalogue entries

The **manifest acts as the machine integrity layer**, while the **catalogue remains the authoritative human-readable inventory**.

-----

# 12. Conclusion

The DecisionOps documentation corpus operates as a governed documentation system built on three core governance artefacts:

- **Corpus Catalogue** — the authoritative human-readable inventory of documentation
- **Corpus Manifest** — the machine-readable definition of the repository structure
- **CI validation rules** — automated enforcement of documentation governance

Together these artefacts form the documentation governance model supporting **Specification Driven Development (SDD)**.

The AI assistant manages the corpus directly within the GitHub repository. The human acts as reviewer and approver only via pull request review. This model is the canonical post-migration operating model per ADR-048.

Once Specification Driven Development begins, the DecisionOps GitHub repository is the definitive and authoritative repository for all platform specifications and architecture artefacts.

By enforcing taxonomy control, location entries, ADR governance and catalogue management, the documentation system remains consistent, auditable and scalable as the DecisionOps platform evolves.