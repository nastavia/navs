# NAVS.G4.11: Enhanced Citizen Identifier (e-CID)

**Voluntary Reference Framework for Enhanced Citizen Identification**  
**Developed and maintained by Nastavia** — https://www.nastavia.com

| Attribute | Value |
| :--- | :--- |
| **ID** | NAVS.G4.11 |
| **Name** | Enhanced Citizen Identifier (e-CID) |
| **Formal Title / Subject** | Voluntary Reference Framework for Enhanced Citizen Identification |
| **Group** | NAVS.G4 — Reference Models and Frameworks |
| **Type** | Reference Framework |
| **Version** | 2025.2 |
| **Status** | Draft |
| **Publication Date** | [TBD] |
| **Developer / Maintainer** | Nastavia |
| **Canonical Reference** | NAVS.G4.11 |
| **Supersedes** | None |
| **Related NAVS** | None |

> This document is part of the **Nastavia Voluntary Standards (NAVS)** system and is developed and maintained by **Nastavia**. It provides a voluntary reference framework for the use of a persistent national person identifier as a non-secret, interoperable reference while separating identification from authentication, authorization, consent, and other security functions. It is intended for public use by organizations, professionals, public authorities, service providers, and information systems where its scope is applicable.

---

## 1. Purpose

This standard establishes the **Enhanced Citizen Identifier (e-CID) Reference Framework** for using a persistent national person identifier as a reliable, non-secret digital reference while keeping security-sensitive functions independent from the identifier itself.

The purpose of e-CID is to enable safe, consistent, privacy-aware, and interoperable person identification across public and private digital services without requiring the underlying Citizen Identifier (CID) to function as a password, authentication factor, authorization mechanism, consent mechanism, or security secret.

The framework is intended to reduce systemic identity risks created when a persistent identifier is treated as confidential knowledge or as evidence of identity. Instead, e-CID places authentication, authorization, consent, and user-controlled security management in dedicated mechanisms surrounding the CID.

The framework also supports national and cross-border interoperability while allowing countries to retain their existing national CID schemes.

---

## 2. Scope

NAVS.G4.11 applies to national identity environments in which a country assigns or recognizes a persistent person-level identifier for individuals whose identity and legal status are formally recognized within that country's identity framework.

The framework is applicable to, among others:

- government information systems and registries;
- digital public service platforms;
- regulated and non-regulated private-sector digital services;
- interoperability frameworks and data exchange environments;
- Digital Public Infrastructure (DPI);
- systems requiring a stable reference to a person without using the identifier itself as a security credential;
- national and cross-border contexts in which a person must be referenced consistently across systems.

The term **Citizen** in the name **Enhanced Citizen Identifier** does not restrict the framework only to nationals of a country. Depending on the applicable national identity regime, a CID may also be assigned to lawful residents, residence-permit holders, or other natural persons whose identity and legal status are formally recognized by the country.

This standard is a **reference framework**. It defines the conceptual model, fundamental properties, boundaries, and security principles of e-CID. It does not prescribe:

- a particular national CID numbering scheme;
- replacement or renumbering of an existing national CID;
- a specific authentication technology;
- a specific authorization technology;
- cryptographic algorithms or token formats;
- API structures or exchange protocols;
- a particular technical implementation of the e-CID User Portal / App;
- national legal criteria determining who is eligible to receive a CID;
- a certification or assurance scheme.

---

## 3. References and Dependencies

### 3.1 Normative References

**ISO 3166-1 — Codes for the representation of names of countries and their subdivisions — Part 1: Country code**

ISO 3166-1 alpha-3 country codes are used by this framework to qualify a Local CID in the Global CID configuration.

No other external normative dependency is established by this version of the framework.

### 3.2 Informative References

**Regulation (EU) 2016/679 — General Data Protection Regulation (GDPR)**

GDPR is an informative reference for principles such as lawfulness, purpose limitation, data minimisation, transparency, and rights of data subjects. Reference to GDPR does not limit the applicability of e-CID to the European Union and does not imply that conformance with NAVS.G4.11 constitutes GDPR compliance.

### 3.3 Related NAVS Standards

No related NAVS standard is designated in this version.

---

## 4. Terms, Definitions and Abbreviations

### 4.1 e-CID

**Enhanced Citizen Identifier (e-CID)** is the reference framework defined by this standard for enhanced use of a national Citizen Identifier.

The enhancement concerns the architecture and governance surrounding the use of the CID rather than requiring alteration of the CID itself.

### 4.2 Citizen Identifier (CID)

A **Citizen Identifier (CID)** is a persistent person-level identifier assigned or recognized within a country's national identity framework.

Within e-CID, the CID functions as a reference to the person. It is not, by itself, an authentication credential, authorization instrument, consent mechanism, password, or proof that the person presenting or knowing the CID is its holder.

### 4.3 e-CID Holder

An **e-CID Holder** is a natural person whose identity and legal status are formally recognized within the applicable national identity framework and to whom a CID is assigned or recognized.

Depending on national rules, an e-CID Holder may be a citizen, lawful resident, residence-permit holder, or another person with a formally recognized identity status.

### 4.4 CID Issuing Authority

The **CID Issuing Authority** is the competent national authority responsible for issuing, recognizing, or governing the CID within the national identity framework.

### 4.5 Local CID

A **Local CID** is the CID in its national configuration. It is unique within the applicable country's national identity framework.

The Local CID may be an existing national person identifier. e-CID does not require the country to create a new identifier where an existing CID can perform the required reference function.

### 4.6 Global CID

A **Global CID** is the globally qualified configuration of a Local CID.

Its conceptual representation is:

```text
<localCID>.<ccc>.ecid
```

where:

- `<localCID>` is the Local CID;
- `<ccc>` is the ISO 3166-1 alpha-3 code of the country whose national identity framework governs the Local CID;
- `.ecid` identifies the e-CID namespace.

The country-qualified suffix:

```text
<ccc>.ecid
```

defines the national e-CID namespace.

Because the Local CID is unique within its national identity framework and the ISO 3166-1 alpha-3 code uniquely qualifies the country namespace, the resulting Global CID is globally unique by construction.

This reference framework does not prescribe transport-level encoding, escaping, or normalization rules. Any technical representation of the Global CID is expected to preserve an unambiguous relationship to the underlying Local CID and country namespace.

### 4.7 Identification

**Identification** is the act of referencing or distinguishing a person using a CID.

### 4.8 Authentication

**Authentication** is the process of establishing that a person or system interacting with a service is the entity it claims to be.

### 4.9 Authorization

**Authorization** is the determination or granting of permission to perform an action or access a resource.

### 4.10 Consent

**Consent** is an explicit expression of the e-CID Holder's agreement to an applicable data access, disclosure, processing activity, or other action where consent is the relevant basis.

### 4.11 e-CID User Portal / App

The **e-CID User Portal / App** is the trusted user-facing environment associated with the national e-CID implementation through which the e-CID Holder can manage and review security-related aspects of e-CID usage.

The e-CID User Portal / App is governed exclusively by the competent national CID Issuing Authority.

---

## 5. e-CID Reference Framework

### 5.1 Framework Principle

e-CID separates the function of **identifying a person** from the functions used to establish trust, permission, consent, or security.

The CID provides a persistent reference to the person. Security-sensitive consequences arise only through independent mechanisms that authenticate the relevant actor, establish applicable authorization, obtain consent where required, and enforce the relevant legal or organizational controls.

The identifier and the mechanisms protecting actions performed in relation to that identifier therefore form distinct conceptual layers.

### 5.2 Enhancement Without Replacement

e-CID does not require replacement of an existing national CID.

A country may apply the e-CID framework to an existing national person identifier where that identifier can operate as a persistent and unique national reference. The enhancement introduced by e-CID is principally the security, authorization, interoperability, user-control, and governance model surrounding use of the CID.

Existing national numbering structures may therefore remain unchanged.

### 5.3 National Identity Context

The authoritative meaning of a Local CID originates in the national identity framework of the country that assigns or recognizes it.

e-CID does not create a supranational authority for determining a person's legal identity or status. National authorities retain responsibility for determining eligibility, assignment, recognition, correction, and other legal aspects of the underlying CID.

The Global CID extends national uniqueness into a global namespace without transferring national identity authority to an external or global issuer.

---

## 6. CID Properties and Configurations

### 6.1 Persistence

The CID within e-CID is persistent.

It is intended to remain a stable reference to the same person throughout the period in which that identity remains recognized within the applicable national framework. Ordinary changes to authentication credentials, devices, passwords, tokens, permissions, or security settings do not require rotation of the CID.

Persistence distinguishes the CID from security credentials, which may be changed, replaced, suspended, or renewed as security conditions require.

### 6.2 Local Uniqueness

A Local CID uniquely references one e-CID Holder within the applicable national identity framework.

The e-CID framework relies on national uniqueness as the basis for consistent domestic referencing across systems and services.

### 6.3 Global Uniqueness

Where a CID is used in a global or cross-border context, the Local CID is qualified by its ISO 3166-1 alpha-3 country namespace using the Global CID configuration:

```text
<localCID>.<ccc>.ecid
```

This construction preserves the national CID while resolving namespace collisions that could otherwise occur where different countries independently assign identical Local CID values.

The framework does not require a global CID registry in order to establish the conceptual uniqueness of the Global CID.

### 6.4 Non-Secret Identifier Principle

The CID is treated as a **non-secret identifier**.

Knowledge or possession of a Local CID or Global CID does not, by itself:

- authenticate a person;
- prove that a person is the CID holder;
- authorize an action;
- express consent;
- grant access to a service;
- grant access to protected personal data;
- establish an entitlement;
- create a security privilege.

The CID may therefore be used as a reference in interfaces, records, transactions, logs, interoperability exchanges, and other contexts in which disclosure of the identifier itself is appropriate.

Non-secret does not mean that every publication or disclosure of a CID is automatically appropriate. Applicable privacy, confidentiality, purpose-limitation, and data-protection rules continue to govern the contexts in which identifiers and related information are processed.

---

## 7. Separation of Identification and Security Functions

### 7.1 Identification Is Not Authentication

Referencing a person through a CID identifies the subject of a record, transaction, or interaction. It does not establish that the person currently interacting with a system is that subject.

Authentication is therefore performed independently from the CID.

### 7.2 Identification Is Not Authorization

A CID does not carry permission.

Authorization to perform an action, retrieve protected information, change data, enter into a transaction, or exercise another controlled capability is established by mechanisms independent from knowledge or possession of the CID.

### 7.3 Identification Is Not Consent

Use of a CID does not imply that its holder has agreed to disclosure, processing, or transfer of personal information.

Where consent is the applicable basis for an action, consent is obtained and managed independently from the identifier.

### 7.4 Identification Is Not Proof of Identity

A CID is a reference to an identity recorded or recognized within the applicable national framework. Knowledge of the CID is not proof that the person presenting it is the corresponding e-CID Holder.

Any context requiring proof of identity relies on appropriate authentication, verification, or other trust mechanisms separate from the CID.

### 7.5 Rejection of Identifier-as-Secret Security

e-CID explicitly rejects security models in which a persistent person identifier is treated as if secrecy of the identifier were an authentication or security control.

A persistent identifier is normally stable, widely referenced, and difficult or undesirable to rotate. Treating knowledge of such an identifier as evidence of identity creates an inherently weak security dependency: disclosure of the identifier can become equivalent to disclosure of a reusable security factor even though the identifier was created for identification rather than authentication.

Under e-CID, compromise or public knowledge of the CID does not compromise authentication, authorization, or consent because those controls are independent of the identifier.

> **Informative note:** In some identity environments, persistent identifiers such as the United States Social Security Number (SSN) have historically been treated as sensitive knowledge and, in some contexts, used as an input to knowledge-based identity verification. e-CID is intentionally designed to avoid this pattern. The reference identifier remains stable and non-secret, while security depends on dedicated security mechanisms rather than on concealment of the identifier.

---

## 8. e-CID User Portal / App

### 8.1 Role

The e-CID framework includes the concept of an **e-CID User Portal / App** as the principal user-facing instrument for managing the security and control context surrounding use of the CID.

The Portal / App does not replace the CID and does not change the function of the CID as a persistent identifier. It provides the environment through which the e-CID Holder interacts with security-related controls associated with use of the identifier.

### 8.2 Governance

The e-CID User Portal / App is governed exclusively by the competent national CID Issuing Authority.

A relying public or private service does not become an alternative e-CID authority merely because it uses a CID or participates in e-CID-enabled transactions.

National implementations may determine their technical and organizational arrangements for delivering the Portal / App, but authority over its security-management role remains with the CID Issuing Authority.

### 8.3 Conceptual Capabilities

As applicable within the national implementation, the e-CID User Portal / App provides the e-CID Holder with capabilities to manage or review security-related aspects of e-CID usage, including:

- authentication-related settings or mechanisms;
- authorizations associated with use of the identity;
- consents where consent is the applicable basis;
- revocation or withdrawal of authorizations or consents where permitted;
- relevant usage, access, or transaction history;
- security-related information and notifications associated with e-CID usage.

This standard defines these capabilities conceptually and does not prescribe user-interface design, software architecture, authentication technology, device type, or delivery channel.

A country may provide web, mobile, or other trusted user-facing channels while preserving the same governance and security principles.

---

## 9. Data Protection and User Control Principles

### 9.1 CID and Personal Attributes

The CID is a reference to the person and does not, by itself, contain or imply disclosure of personal attributes.

A service that knows a CID does not thereby acquire a right to retrieve, infer, or process protected attributes associated with the e-CID Holder.

### 9.2 Authorized Data Use

Access to or processing of personal data associated with an e-CID Holder requires an applicable lawful and authorized basis under the relevant national or other governing framework.

Where the action relies on the e-CID Holder's consent, the consent is managed independently from the CID and is expected to be explicit, purpose-specific, understandable, and capable of withdrawal where the governing framework provides for withdrawal.

Where data processing is authorized on another lawful basis, the existence of the CID does not alter or replace that basis.

### 9.3 Data Minimization

Use of e-CID is intended to reduce unnecessary duplication and disclosure of personal information.

Systems using e-CID are expected to request, exchange, and process only the information necessary for the applicable purpose rather than treating the identifier as a gateway to unrestricted identity data.

### 9.4 User Visibility and Control

The e-CID framework promotes meaningful visibility for the e-CID Holder into security-sensitive use of the identifier and related personal data.

The e-CID User Portal / App is the principal framework instrument through which such visibility and applicable user controls are exposed.

User control under e-CID operates within the applicable legal framework and does not imply that every legally authorized processing activity depends on individual consent.

---

## 10. Interoperability and DPI Applicability

### 10.1 Common Person Reference

e-CID provides a common conceptual approach for referencing the same person across otherwise independent systems.

This enables systems to use a stable person-level key without requiring the CID itself to carry personal attributes or security credentials.

### 10.2 Public and Private Services

A CID may be used across public and private services where such use is permitted by the applicable national framework.

Relying services may use the identifier for consistent referencing while maintaining their own business logic, data models, and technical architectures.

### 10.3 Cross-Border Referencing

The Global CID configuration enables a nationally unique CID to be expressed within a globally unique namespace without replacing the Local CID.

The Global CID therefore supports cross-border or multi-country contexts in which a Local CID value alone would not identify its national namespace unambiguously.

### 10.4 Digital Public Infrastructure

e-CID may function as a foundational identity-reference component within Digital Public Infrastructure.

Its use can support interoperability without requiring:

- duplication of complete identity records;
- synchronization of unnecessary sensitive personal data;
- use of the identifier as a credential;
- uniform technical implementations across all participating systems.

### 10.5 Technology Neutrality

e-CID defines conceptual properties and relationships rather than a mandatory implementation stack.

Countries and organizations may use different databases, identity platforms, authentication technologies, authorization mechanisms, cryptographic tools, APIs, applications, and infrastructure while conforming to the e-CID reference framework.

---

## 11. Conformance and Adoption

### 11.1 Conformance Target

The principal conformance target of NAVS.G4.11 is a national or organizational implementation that claims to apply the e-CID Reference Framework to the use of a CID.

Conformance concerns preservation of the conceptual properties defined by this standard rather than use of a prescribed technology.

### 11.2 Minimum Conformance Conditions

An implementation claiming conformance with NAVS.G4.11 is expected to satisfy all of the following conditions within the scope of its claim:

1. the CID is a persistent person-level identifier;
2. the Local CID is unique within the applicable national identity framework;
3. the CID is treated as non-secret and is not used, by itself, as an authentication factor, password, authorization instrument, consent mechanism, or proof of identity;
4. authentication is functionally separated from identification;
5. authorization is functionally separated from identification;
6. consent, where applicable, is functionally separated from identification;
7. protected information or controlled actions cannot be obtained solely through knowledge or possession of the CID;
8. the implementation can accommodate an existing national CID without requiring replacement or renumbering solely for e-CID conformance;
9. the e-CID User Portal / App security-management function is governed exclusively by the competent national CID Issuing Authority;
10. where the Global CID configuration is used, it qualifies the Local CID through the applicable ISO 3166-1 alpha-3 national e-CID namespace;
11. the implementation preserves applicable privacy, data-protection, and lawful-processing requirements independently from the existence of the CID.

### 11.3 Local Adaptation

Countries may adapt the e-CID framework to their national identity, legal, institutional, and technical environments provided that the core conceptual separation between identifier and security functions is preserved.

National profiles may define additional requirements, controls, assurance levels, technical formats, or operating procedures.

Such extensions do not alter the meaning of conformance with NAVS.G4.11 unless they conflict with its fundamental provisions.

### 11.4 Adoption

Organizations may adopt e-CID incrementally and integrate it with existing identity, trust, security, interoperability, or Digital Public Infrastructure arrangements.

Adoption of the framework does not require uniform technical implementation across participating organizations.

### 11.5 Limitations of Conformance

Conformance with NAVS.G4.11:

- does not constitute certification unless a separate certification or assurance mechanism is defined;
- does not establish legal compliance;
- does not replace national identity law or regulation;
- does not determine eligibility for national identity status;
- does not prescribe a specific level of authentication assurance;
- does not guarantee the security of an implementation whose surrounding systems or controls are defective.

---

## 12. Governance and Maintenance

NAVS.G4.11 is developed and maintained by **Nastavia** as part of the Nastavia Voluntary Standards system.

Nastavia is responsible for maintaining the conceptual integrity of the standard, considering interpretation issues, and evaluating proposed revisions to the framework.

Detailed NAVS-wide procedures for formal change control, publication states, review cycles, and supersession remain subject to the applicable NAVS system-level rules as they are established.

Changes to this standard should preserve a clear distinction between:

- the persistent identity-reference role of the CID;
- security and trust functions surrounding use of the CID;
- national authority over identity recognition;
- implementation-specific mechanisms that remain outside the reference framework unless deliberately standardized in a future NAVS document.

---

# Annex A — Illustrative Usage Scenarios

**Status: Informative**

The scenarios in this annex illustrate possible uses of the e-CID framework. They do not add requirements beyond the normative provisions of the standard.

## A.1 Consistent Reference Across Public Services

A person is registered under a national CID and interacts with multiple government services.

Each service can use the same CID as the stable reference to the person without treating knowledge of the CID as proof that the current user is that person. Authentication and authorization are performed through independent mechanisms.

## A.2 Existing National CID Adoption

A country already operates a mature national person-identification number.

Adoption of e-CID does not require the country to replace or renumber that identifier. The existing number continues to function as the Local CID while the country applies the e-CID separation between identification and security functions and provides the associated user-control environment.

## A.3 User-Controlled Private-Service Interaction

A private service provider receives an e-CID Holder's CID as a reference.

Possession of the CID does not entitle the service provider to retrieve protected personal information. Any applicable authorization, consent, attribute sharing, or identity verification is handled through mechanisms independent from the CID and subject to the national framework.

## A.4 Global CID

Assume a nationally unique Local CID:

```text
123456789
```

and an ISO 3166-1 alpha-3 country code:

```text
GEO
```

Its conceptual Global CID representation is:

```text
123456789.GEO.ecid
```

The country-qualified namespace distinguishes this CID from an identical Local CID that might independently exist in another country.

The example is illustrative and does not prescribe the format of Local CIDs or transport-level encoding.

## A.5 e-CID User Portal / App

An e-CID Holder uses the national e-CID User Portal / App to review security-related activity associated with the identity, manage applicable authentication settings, review or revoke authorizations and consents where permitted, and inspect relevant usage history.

The public or private services relying on the CID do not become authorities over the e-CID security-management environment.

---

# Annex B — Conceptual Summary

**Status: Informative**

The e-CID Reference Framework can be summarized through the following principles:

1. **The CID identifies; it does not authenticate.**
2. **The CID is persistent; security credentials may change.**
3. **The CID is non-secret; knowledge of it conveys no privilege.**
4. **Authorization and consent are independent from the identifier.**
5. **The national CID can remain unchanged.**
6. **A Local CID is nationally unique.**
7. **A Global CID is formed by qualifying the Local CID with the national ISO 3166-1 alpha-3 e-CID namespace.**
8. **The e-CID User Portal / App is the holder-facing security-management instrument and is governed exclusively by the national CID Issuing Authority.**
9. **Personal attributes are not implied by possession of the CID.**
10. **e-CID is technology-neutral and can be integrated into existing national identity and Digital Public Infrastructure environments.**
