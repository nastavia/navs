# NAVS.G4.31.1: Data Governance Assessment Framework (DGAF) — Part 1: Core Framework

**Voluntary Standard for a Sector-Neutral Data Governance Assessment Reference Framework**  
**Developed and maintained by Nastavia** — https://www.nastavia.com

| Attribute | Value |
| :--- | :--- |
| **ID** | NAVS.G4.31.1 |
| **Name** | Data Governance Assessment Framework (DGAF) — Core Framework |
| **Formal Title / Subject** | Voluntary Standard for the Data Governance Assessment Framework — Part 1: Core Framework |
| **Parent standard** | NAVS.G4.31 — Data Governance Assessment Framework |
| **Group** | NAVS.G4 — Reference Models and Frameworks |
| **Version** | 2026.3 |
| **Status** | Draft |
| **Publication Date** | [TBD — not yet published] |
| **Developer / Maintainer** | Nastavia |
| **Canonical Reference** | [TBD] |
| **Supersedes** | None |
| **Related NAVS Standards** | [TBD — no dependency designated for this draft] |

This document is part of the **Nastavia Voluntary Standards (NAVS)** system and is developed and maintained by **Nastavia**. It provides a voluntary, sector-neutral reference for organizing and examining enterprise Data Governance capabilities and identifying areas for structured improvement.

Adoption is voluntary unless made mandatory by an adopting organization's rules, contracts, policies, regulations, or other governing instruments. Conformance relates only to the explicitly normative provisions within the declared scope and does not constitute certification, regulatory approval, legal compliance, or a claim of Data Governance maturity.

**Draft status notice.** This document establishes a proposed structural baseline for consultation. The Pillar and Section titles reproduce the supplied XML source; their accompanying descriptions are newly drafted explanatory interpretations. Nineteen of the twenty source Sections carry a `group="Review"` marker; their inclusion here is **not** an assertion of substantive approval. No detailed assessment objectives, questions, scores, or maturity thresholds are adopted by this edition.

---

## 1. Purpose

NAVS.G4.31.1 establishes the sector-neutral **Core Framework** of the Data Governance Assessment Framework (DGAF), providing a consistent organization of governance domains that can be used to structure assessment, compare coverage, identify capability gaps, and guide later improvement planning.

DGAF recognizes Data Governance as an enterprise-wide discipline encompassing organizational authority, contextual and semantic understanding, operational management, and legal or regulatory obligations. The framework aims to support a governed data environment capable of underpinning reliable interpretation and better-informed organizational decisions.

The principal outcome of this edition is a stable, understandable and extensible **reference structure** rather than a completed assessment questionnaire or maturity-scoring system.

## 2. Scope

This Part specifies the sector-neutral organization of DGAF at two levels: **L1 — Pillar** and **L2 — Section**, together with the planned hierarchy for elaborating those domains. It applies to organizations seeking a common structure for Data Governance assessment irrespective of industry, size, ownership, technology platform, or regulatory profile, subject to proportional application and any sector-specific extensions.

Intended users include governing bodies, executives, Data Governance functions, data owners and stewards, assurance functions, assessment practitioners, and professionals designing Data Governance development programs.

This edition does **not** specify:

- a mandatory assessment questionnaire or evidence checklist;
- detailed L3 Chapters, L4 Assessment Objectives, or L5 Assessment Questions;
- scoring formulas, rating scales, maturity levels, aggregate indexes, or radar-chart calculations;
- auditor qualification, independent assurance, accreditation, or certification arrangements;
- mandatory tools, vendor products, organizational structures, or implementation technologies;
- sector-specific assessment content or assertions of legal/regulatory compliance.

Later DGAF artifacts may elaborate these matters, but their existence in a working source file does not make them normative under this Part.

## 3. References and Dependencies

### 3.1 Normative References

**None designated for this draft.** Conformance to the structure specified here does not require adoption of any external standard.

### 3.2 Informative References and Source Material

- **`DGAF.0.2603.xml`** — working DGAF outline, XML version `2603`; direct source for the Pillar and Section titles and their ordering. The detailed underlying nodes are not incorporated normatively.
- **`NAVS_Overview.md`** — NAVS system architecture and current identifier conventions (internal project governance reference).
- **`NAVS_Standard_Template.md`** — NAVS common drafting and document structure (internal project governance reference).

The XML attributes `source`, `refs`, `group`, and `part` represent working source metadata. References within `refs` are **not automatically normative references** of NAVS.G4.31.1 and are not independently validated by their inclusion in the XML.

### 3.3 Related NAVS Standards

No related NAVS standard is designated as a normative dependency in this edition. The DGAF multipart family relationship is described in Clause 5.

## 4. Terms, Definitions and Abbreviations

**Data Governance:** The organizational arrangements, responsibilities, policies, processes, controls, and semantic foundations through which data is directed, managed, interpreted, and used accountably in support of organizational objectives.

**DGAF (Data Governance Assessment Framework):** The NAVS reference framework for systematically organizing and assessing the capabilities of Data Governance.

**Core Framework:** The sector-neutral reference structure defined in Part 1, containing common domains intended to be inherited by DGAF sector-specific parts.

**Sector-specific part:** A separately developed member of the NAVS.G4.31 family that specializes or adds assessment content for a particular sector while preserving the Core Pillar and Section structure.

**L1 — Pillar (`P`):** A principal Data Governance domain at the highest level of the DGAF hierarchy.

**L2 — Section (`S`):** A coherent assessment area within a Pillar.

**L3 — Chapter (`C`):** A lower-level subdivision of a Section grouping related assessment topics.

**L4 — Assessment Objective (`O`):** An assessable capability or governance outcome within a Chapter. The source XML labels this node type `Objective`.

**L5 — Assessment Question (`Q`):** A question through which an Assessment Objective may be examined and supported by evidence. This node is a planned elaboration level, not a normative questionnaire in this edition.

**Structural conformance:** Alignment of a stated framework representation or mapping with the hierarchy, identities, and extension boundaries specified in this Part; it does not establish organizational maturity or practical effectiveness.

## 5. DGAF Framework Architecture

### 5.1 Multipart standard family

The DGAF standard family is identified by **NAVS.G4.31**. This document is **NAVS.G4.31.1**, where the terminal component `1` identifies the **Core Framework**. Other terminal numeric or alphabetic components may identify separate sector-specific parts, subject to allocation and registration. The terminal component is a **part identifier**, not a revision or document version.

This multipart notation is a **DGAF-specific design decision**. The NAVS system-level overview currently establishes the base `NAVS.Gn.xx` convention; a NAVS-wide multipart identifier policy remains to be formalized. No identifiers for individual sectors are allocated by this document.

### 5.2 Five-level reference hierarchy

DGAF is organized conceptually as follows:

| Level | Name | XML marker | Role | Status in this edition |
| :--- | :--- | :---: | :--- | :--- |
| L1 | Pillar | `P` | Principal governance domain | **Included in structural baseline** |
| L2 | Section | `S` | Subdomain within a Pillar | **Included in structural baseline** |
| L3 | Chapter | `C` | Organized topics within a Section | Defined as hierarchy type only |
| L4 | Assessment Objective | `O` | Specific assessable capability or outcome | Defined as hierarchy type only |
| L5 | Assessment Question | `Q` | Evidence-oriented assessment prompt | Defined as hierarchy type only |

The relationship is **Pillar → Section → Chapter → Assessment Objective → Assessment Question**. The concept of five levels does not imply that their entire content has already been approved or published.

### 5.3 Structural baseline and source metadata

The **four Pillars and twenty Sections** in Clause 6 constitute the proposed normative structural baseline of this draft. A representation claiming structural conformance to the finalized edition would preserve those titles, their Pillar-to-Section placement, and their order. Alternative visual layouts or internal numeric keys may be used provided a precise one-to-one mapping to the published structure is maintained.

Numbers such as `1.1` or `3.4` in Clause 6 are **navigation labels assigned in this document**, not independent NAVS standard identifiers or asserted permanent registry keys. The underlying XML provides node types and titles, not a canonical identifier for each Pillar or Section.

### 5.4 Intended uses and boundaries

DGAF can provide a common domain vocabulary and navigation structure for baseline assessments, gap analysis, evidence gathering, comparisons across organizational units, and planning improvement initiatives. Actual assessment instruments, proof requirements, weightings, scoring, and maturity interpretation must be specified independently before such results can be claimed to follow a standardized DGAF method.

## 6. DGAF Core Reference Structure

**Status of this clause:** Pillar and Section *names and grouping* are proposed normative structure for this draft. Descriptive text is **informative** and intended to communicate coverage rather than impose detailed operational requirements. Section titles are retained verbatim from the XML source (XML entity escapes rendered as characters).

### 6.1 Pillar 1 — Organizational Data Governance

Addresses how an organization establishes authority, accountability, policy, culture, competence, and ongoing oversight for Data Governance. The Pillar connects leadership arrangements and organizational behavior with assessment, improvement, and the allocation of resources.

#### 6.1.1 Section 1.1 — Authority, Strategy and Operational Model

Establishes the organizational foundations for Data Governance, including formal mandates, decision rights, strategy, executive accountability, governance bodies, operating arrangements, and alignment with business architecture. It addresses how governing authority is assigned, exercised, escalated, and sustained across organizational boundaries.

#### 6.1.2 Section 1.2 — Data Ownership, Stewardship & Cross-Functional Accountability

Addresses the allocation and coordination of accountability for data creation, stewardship, custody, consumption, and cross-functional use. It encompasses formally defined data roles, responsibility assignments, and ownership across business processes, product teams, and organizational units.

#### 6.1.3 Section 1.3 — Policies, Standards, Procedures & Governance Services

Covers the institutional mechanisms through which Data Governance policies and standards are established, maintained, applied, and monitored. It encompasses documented procedures, operational governance services, exception management, enforcement arrangements, and management review.

#### 6.1.4 Section 1.4 — Culture, Competence, Change & Knowledge Sharing

Addresses the human and organizational conditions necessary for effective Data Governance, including awareness, competence, data literacy, training, change adoption, and shared organizational knowledge. It recognizes that sustainable governance depends on established behaviors and collaboration as well as formal structures.

#### 6.1.5 Section 1.5 — Governance Performance, Assessment & Investment

Addresses the evaluation of Data Governance outcomes, evidence-based capability assessment, and the use of assessment findings to guide priorities and investments. It encompasses performance measures, improvement roadmaps, resource commitments, and the sustained realization of governance value.

### 6.2 Pillar 2 — Contextual Data Governance

Addresses the meaning, business relevance, discovery, authoritative representation, and sharing of data across contexts. The Pillar focuses on preserving the relationship between data and its interpretation, including semantics, data products, analytics, and interoperability.

#### 6.2.1 Section 2.1 — Business Metadata, Discovery & Data Product Governance

Covers the identification, description, discovery, and responsible use of business-relevant data assets and data products. It encompasses business glossaries, critical data identification, data catalogs, trustworthy asset descriptions, governed measures and metrics, product ownership, and consumer feedback.

#### 6.2.2 Section 2.2 — Context, Terminology, Semantic Models & Interoperability

Addresses the representation and consistent interpretation of data in business and technical contexts. It covers controlled terminology, semantic models, taxonomies, ontologies, mappings, knowledge graphs, and the governance of interoperability across organizational and system boundaries.

#### 6.2.3 Section 2.3 — Master Entities, Reference Data & Authoritative Representations

Covers consistent identification and authoritative representation of important business entities and reference values. It encompasses master data ownership, entity matching, identity resolution, golden records, source authority, reference data governance, and synchronization across consuming systems.

#### 6.2.4 Section 2.4 — Data Governance for Analytics, ML, Generative AI & Automated Actions

Addresses governance of the data and contextual information used by analytics, machine learning, generative AI, and automated or agentic processes. It includes dataset suitability, provenance, labeling, features, reproducibility, drift, bias, retrieval contexts, machine action boundaries, and traceability of analytical outcomes.

#### 6.2.5 Section 2.5 — Data Sharing, Data Spaces & Stakeholder Context

Covers governance arrangements for sharing and reusing data within and beyond the organization. It addresses domain boundaries, data-sharing conditions, federated data spaces, stakeholder trust, usage rights, openness, and responsible reuse in differing contexts.

### 6.3 Pillar 3 — Operational Data Governance

Addresses the execution and technical-operational management of data across its lifecycle. The Pillar encompasses quality assurance, metadata and lineage, architecture, integration, availability, resilience, and continuity of data services.

#### 6.3.1 Section 3.1 — Data Quality Management & Source-Level Assurance

Addresses the definition, measurement, monitoring, and improvement of data quality from point of capture through downstream use. It encompasses quality dimensions and thresholds, source validation, producer–consumer commitments, transformation quality, observability, and defect remediation.

#### 6.3.2 Section 3.2 — Metadata, Provenance, Lineage & Impact Governance

Covers the capture, management, and verification of metadata, provenance, and end-to-end data lineage. It addresses technical metadata currency, asset identification, transformation visibility, dependency analysis, historical reproducibility, and impact assessment of changes.

#### 6.3.3 Section 3.3 — Data Lifecycle, Architecture & Asset Stewardship

Addresses governance of data assets throughout their operating lives, including architectural boundaries, value-stream dependencies, storage, retention, archiving, depreciation or retirement of assets, disposal, and management of architectural and data-related technical debt.

#### 6.3.4 Section 3.4 — Data Acquisition, Integration & Delivery Governance

Covers the governed acquisition, ingestion, exchange, transformation, migration, and delivery of data. It encompasses interfaces and integration controls, acceptance and licensing conditions, change management, timely delivery, local processing, and handling of unstructured or streaming data.

#### 6.3.5 Section 3.5 — Data Availability, Resilience & Operational Continuity

Addresses the continuity and dependable availability of governed data capabilities, including operational resilience, recoverability, capacity, monitoring, and response arrangements. The scope encompasses maintaining access to data and data services under disruption and recovering them in accordance with business needs.

### 6.4 Pillar 4 — Regulatory Data Governance

Addresses the governance of data in relation to binding obligations, risk, control assurance, individual rights, evidentiary requirements, and cross-jurisdictional dependencies. The Pillar connects organizational governance practices with externally imposed duties and risk-management needs.

#### 6.4.1 Section 4.1 — Legal, Regulatory & Compliance Obligations

Addresses identification, interpretation, allocation, and operationalization of legal, regulatory, and contractual obligations affecting data. It encompasses obligations management and the ability to connect applicable requirements to governance policies, accountable parties, and supporting evidence.

#### 6.4.2 Section 4.2 — Data Risk, Control Assurance & Risk-Prevention Value

Covers data-related risk identification, control arrangements, assurance, and the contribution of governance to preventing adverse business and regulatory outcomes. It addresses the connection between data risks, control effectiveness, monitoring, and remedial action.

#### 6.4.3 Section 4.3 — Data Protection, Access, Privacy Design & Rights

Addresses protection of data and governance of access and individual rights across its use and processing. It encompasses security-related controls, privacy-by-design considerations, access decisions, and handling of relevant data rights and restrictions.

#### 6.4.4 Section 4.4 — Preservation, Discovery, Evidence & Incident Governance

Covers preservation and discoverability of records and data required for evidentiary, investigative, and incident-response purposes. It addresses defensible retention, traceability, access to evidence, investigation support, and governance of data-related incidents.

#### 6.4.5 Section 4.5 — Third-Party, Distributed & Jurisdictional Data Risk

Addresses risks to governed data arising from outsourcing, service providers, distributed ecosystems, and activity across legal jurisdictions. It encompasses third-party accountability, dependency oversight, jurisdictional requirements, and cross-boundary data governance.

## 7. Framework Extension and Evolution

### 7.1 Core preservation principle

Sector-specific DGAF parts are developed separately from Part 1. They inherit the **Core L1 Pillars and L2 Sections without renaming, removing, reassigning, or changing their defined organizational relationships**. Sector-specific content is expressed as additional specialization or assessment detail under the inherited reference structure, with clear traceability to the Core.

A proposal to modify the Core L1/L2 hierarchy is a proposed **Core revision**, not a unilateral change permitted to an individual sector-specific part.

### 7.2 Development of lower-level items

The L1/L2 structure is designed for progressive elaboration into **L3 Chapters**, **L4 Assessment Objectives**, and **L5 Assessment Questions**. Lower-level content may identify assessment subjects, intended governance outcomes, evidence prompts, and sector-specific concerns, but no such detailed content is incorporated as a normative requirement in the present edition.

Future publications should preserve traceability from lower-level items to their parent Section and Pillar. Detailed identifier patterns, schema conventions, and mapping rules for lower-level items remain **[TBD]**.

### 7.3 Relationship between source files and released standards

The XML outline is a working development source and may contain draft lower-level nodes, candidate external references, and review-state annotations. Its structure and content beyond the levels explicitly published here do not acquire normative standing merely by reference. A future release may include an authoritative machine-readable representation; its designation, location and version-control mechanism are **[TBD]**.

### 7.4 Sector-specific parts

Future parts may elaborate assessment objectives, questions, evidence expectations, or sector-relevant concerns without displacing Core coverage. Each sector-specific part should declare its sector scope, identifier, version, relationship with Core, and any additional conformance provisions. Rules for reconciling competing sector extensions and representing cross-sector applicability are **[TBD]**.

## 8. Conformance and Adoption

### 8.1 Conformance target

Conformance under this edition is limited to the **structure of a DGAF framework representation, mapping, or organized assessment instrument**. It is not an attestation concerning an organization's governance performance.

### 8.2 Structural conformance conditions

Within a claim to structural conformance with NAVS.G4.31.1, the claimant shall:

1. represent all four Core Pillars and all twenty Core Sections established in Clause 6;
2. preserve their names, Pillar membership and ordering, or supply a complete and unambiguous mapping to the published structure if another internal label scheme is used;
3. distinguish supplementary or sector-specific content from Core content;
4. refrain from presenting unpublished lower-level DGAF content as normative content of this edition; and
5. identify the NAVS standard part and publication version against which the structural claim is made.

These conditions concern **classification and traceability**, not whether every domain has been implemented effectively within an organization. A domain may be assessed as absent or immature without making the assessment instrument structurally nonconformant.

### 8.3 Limitations

Structural conformance does not establish an assessment score, maturity level, certification status, regulatory compliance, or completeness of an organization's Data Governance controls. Claims of capability, implementation quality, or externally assured conformance require separate criteria and evidence not defined here.

## 9. Governance and Maintenance

NAVS.G4.31.1 is developed and maintained by **Nastavia** under the NAVS system. Nastavia is responsible for maintaining the authoritative published Core structure, considering interpretation issues and proposals for revision, and coordinating the consistency of Core and sector-specific parts.

Changes to L1/L2 structure should be reviewed as potentially substantive revisions with attention to backward compatibility and impacts on sector-specific mappings. Changes to lower-level assessment materials must not be implied to amend this Part unless formally incorporated into a published revision.

The NAVS-wide approval process, feedback channel, detailed publication lifecycle, revision compatibility policy, and canonical machine-readable artifact designation remain **[TBD]**.



