# NAVS.G4.11: x-UIN — Extended UIN Framework

**Voluntary Reference Framework for Extended Use of Unique Identification Numbers**  
**Developed and maintained by Nastavia**

| Attribute | Value |
| :--- | :--- |
| **ID** | NAVS.G4.11 |
| **Name** | x-UIN — Extended UIN Framework |
| **Formal Title / Subject** | Voluntary Reference Framework for Extended Use of Unique Identification Numbers |
| **Group** | NAVS.G4 — Reference Models and Frameworks |
| **Established** | Y2024 |
| **Version** | 2026.1 |
| **Status** | Draft |
| **Publication Date** | 2026-09-12 |
| **Developer / Maintainer** | Nastavia |
| **Canonical Reference** | [GitHub](https://github.com/nastavia/navs/tree/main/NAVS.G4/NAVS.G4.11) |
| **Supersedes** | None |
| **Related NAVS** | None |

This document is part of the **Nastavia Voluntary Standards (NAVS)** system and is developed and maintained by **Nastavia**. It provides a voluntary reference framework for extending the use of nationally issued Unique Identification Numbers (UINs) through explicit separation of identification from security functions, privacy controls, issuer-governed user management, issuer-defined service credentials, and global interoperability.

Adoption of this standard is voluntary unless required by an applicable policy, contract, regulation, or other governing instrument. Conformance with this standard does not, by itself, constitute certification, legal compliance, or regulatory approval.

---

## 1. Purpose

NAVS.G4.11 establishes **x-UIN**, a reference framework for extending the safe, privacy-aware, interoperable, and user-controlled use of a persistent national UIN without requiring replacement of the underlying identifier.

x-UIN is based on five principles:

- The UIN identifies; it does not authenticate.
- The UIN is persistent and non-secret.
- Authentication, authorization, and consent are independent from the UIN.
- Privacy is achieved through controlled use, tokenization, contextual separation, and user control rather than UIN secrecy.
- National UINs can be used globally without replacing existing national numbering schemes.

x-UIN also defines an issuer-governed **x-UIN User Portal / App** and a **Credential Pair** model for environments where persistent client continuity and traceability are contextually important.

---

## 2. Scope

x-UIN applies to identity environments in which a competent national authority assigns or recognizes a persistent UIN for a natural person.

A UIN holder may be:

- A citizen.
- A resident or residence-permit holder.
- Another person whose identity and legal status are formally recognized by the country.

x-UIN may be used across public services, private services, regulated sectors, Digital Public Infrastructure, and cross-border environments.

This standard does not prescribe:

- A national numbering scheme.
- Replacement or renumbering of existing UINs.
- Authentication technologies.
- Cryptographic algorithms.
- API, database, or application architectures.
- National eligibility rules for receiving a UIN.
- A certification scheme.

---

## 3. References and Dependencies

### 3.1 Normative reference

**ISO 3166-1 — Codes for the representation of names of countries and their subdivisions**

The ISO 3166-1 alpha-3 country code is used in the Global UIN representation.

### 3.2 Conceptual reference

**World Bank Identification for Development (ID4D), ID4D Practitioner’s Guide, Version 1.0**

x-UIN uses the ID4D **Unique ID Number (UIN)** concept as the conceptual basis for the underlying persistent national person identifier.

ID4D also addresses privacy, security, authentication, and tokenization. x-UIN does not replace or restate that guidance. It extends it with a more specific UIN-level architecture covering:

- Non-secret use of the UIN.
- Explicit separation of identification from authentication and authorization.
- Issuer-governed user security management.
- Front-end tokenization within the x-UIN service model.
- Credential Pairs for contextual continuity and traceability.
- A globally qualified UIN representation.

ID4D addresses privacy and security broadly at the identification-system level. x-UIN specializes these dimensions by defining additional architectural properties for **UIN usage itself**.

### 3.3 Related NAVS standards

None designated in this version.

---

## 4. Terms and Definitions

### 4.1 x-UIN

**x-UIN — Extended UIN Framework** is the reference framework defined by NAVS.G4.11.

The `x` denotes **Extended**. The framework extends how a UIN is used; it does not require modification of the national UIN itself.

### 4.2 Unique Identification Number (UIN)

A **UIN** is a persistent person-level identifier assigned or recognized by a competent national authority and unique within the applicable national identity system.

For x-UIN purposes, the UIN is represented as a sequence of decimal digits.

Although composed of digits, a UIN has **string semantics**, not arithmetic semantics. Significant leading zeros in existing national schemes remain part of the identifier.

### 4.3 Global UIN

A **Global UIN** is the globally qualified representation of a national UIN:

```text
UIN.<CCC>.<UIN-value>
```

Where:

- `UIN` is the literal namespace prefix.
- `<CCC>` is the ISO 3166-1 alpha-3 code of the issuing country.
- `<UIN-value>` is the canonical national UIN.

Example:

```text
UIN.GEO.01001234567
```

Structural regular expression:

```regex
^UIN\.[A-Z]{3}\.[0-9]+$
```

The country component is additionally validated against ISO 3166-1 alpha-3.

### 4.4 UIN Issuing Authority

The **UIN Issuing Authority** is the competent national authority responsible for issuing, recognizing, maintaining, or governing the national UIN.

### 4.5 x-UIN User Portal / App

The **x-UIN User Portal / App** is the trusted user-facing environment through which the UIN holder manages and reviews security-related aspects of x-UIN usage.

It is governed exclusively by the competent national UIN Issuing Authority.

### 4.6 Credential Pair

A **Credential Pair** is an x-UIN service construct consisting of:

1. A **Presentation Credential**, which is the actual UIN.
2. A **Service Credential**, which is a credential provided by the UIN Issuing Authority and defines the authorized scope of UIN use for the operation counterparty.

Both credentials are linked, under the governance of the UIN Issuing Authority, to the same UIN holder.

Neither credential provides authorization on its own. They are used only in combination.

---

## 5. x-UIN Reference Model

### 5.1 UIN as a non-secret identifier

The UIN is a persistent reference to a person and is not treated as a security secret.

Knowledge or possession of a UIN does not, by itself:

- Authenticate the holder.
- Prove identity.
- Authorize an action.
- Express consent.
- Grant access to protected information.
- Establish an entitlement.

This avoids the **identifier-as-secret** model in which disclosure of a persistent identifier acquires password-like security consequences.

### 5.2 Separation of security functions

x-UIN distinguishes four functions:

1. **Identification** — Determines which person is referenced.
2. **Authentication** — Establishes that an interacting party is who it claims to be.
3. **Authorization** — Determines what an authenticated party may do.
4. **Consent** — Records the holder’s agreement where consent is the applicable basis.

The UIN performs only the identification function.

### 5.3 Persistence

The UIN remains a stable person reference.

Changes to passwords, devices, cryptographic keys, tokens, authorizations, or consents do not normally require changing the UIN.

### 5.4 Existing national UINs

x-UIN does not require replacement or renumbering of an existing national identifier that satisfies the UIN role.

The national authority retains responsibility for:

- Issuance.
- Uniqueness.
- Eligibility.
- Correction.
- Lifecycle management.

---

## 6. x-UIN Service and Privacy Model

### 6.1 Front-end tokenization

x-UIN can support **front-end tokenization** as described by the ID4D Version 1.0 framework where an implementation requires reduced exposure of the permanent UIN.

Front-end tokenization is complementary to the x-UIN Credential Pair model. It may be applied at the service boundary or presentation layer without changing the underlying Credential Pair semantics defined by this standard.

### 6.2 Credential Pairs

Where controlled UIN use, client continuity, or traceability is required, the x-UIN service model uses a **Credential Pair**.

The Presentation Credential is the actual UIN. The Service Credential is issued by the UIN Issuing Authority for a defined counterparty, service, or domain and establishes the permitted scope in which that UIN may be used.

The two credentials are evaluated together. Neither credential provides authorization independently.

### 6.3 Context-specific traceability

A Service Credential may define the permitted scope of UIN use for:

- A single relying service.
- A defined group of related services.
- A governed sector or domain.

The scope should reflect legitimate operational needs and privacy considerations.

Healthcare is a representative example. A healthcare-domain Service Credential may allow the same UIN to be used consistently across authorized treatment, record, or care contexts while preserving clear traceability of the counterparty and permitted scope.

Unrelated domains may use different Service Credentials for the same UIN holder.

### 6.4 Credential governance

The authoritative relationship between the UIN and Service Credentials is governed by the UIN Issuing Authority.

The UIN Issuing Authority defines and manages the scope represented by each Service Credential.

A relying service does not obtain authority over the underlying national identity merely because it receives or uses a Credential Pair.

### 6.5 Privacy principle

x-UIN separates privacy from identifier secrecy.

Privacy is achieved through:

- Purpose-limited disclosure.
- Tokenization.
- Context-specific credentials.
- Authorization.
- Consent where applicable.
- Data minimization.
- User visibility and control.
- Accountability and traceability.

---

## 7. x-UIN User Portal / App

The x-UIN User Portal / App is the principal holder-facing security-management instrument.

Depending on the national implementation, it may allow the holder to:

- Manage authentication settings.
- Review Service Credentials and their scope.
- Review or request revocation of Service Credentials where applicable.
- Review or withdraw applicable authorizations and consents.
- Review relevant access or transaction history.
- Receive security notifications.
- Respond to suspicious activity.

The Portal / App is governed exclusively by the national UIN Issuing Authority.

x-UIN does not prescribe whether it is implemented as a website, mobile application, or another trusted channel.

---

## 8. Global UIN

The Global UIN provides a globally unique representation without creating a global issuing authority.

Its canonical form is:

```text
UIN.<CCC>.<UIN-value>
```

Global uniqueness results from:

1. National uniqueness of the UIN.
2. Qualification by the ISO 3166-1 alpha-3 country code.

For example:

```text
UIN.GEO.123456789
UIN.EST.123456789
```

represent different national identifiers.

Existing significant leading zeros are preserved exactly:

```text
UIN.GEO.01234567890
```

is not presumed equivalent to:

```text
UIN.GEO.1234567890
```

The UIN value is processed as a digit string and is not numerically normalized.

---

## 9. UIN Design Guidance

**Status: Informative**

For newly established or materially redesigned national UIN schemes:

- Use a defined fixed length where practical.
- Allocate identifiers using the full defined length.
- Avoid leading zeros.
- Avoid encoding unnecessary personal attributes into the UIN.
- Treat the UIN as an identifier rather than an arithmetic number.

Leading zeros should be avoided because spreadsheets, import tools, databases, and other general-purpose software may remove or transform them.

This guidance does not alter existing UINs. Where leading zeros are already significant, x-UIN preserves them exactly.

---

## 10. Conformance and Adoption

An implementation conforms to NAVS.G4.11 where, within the scope of its conformance claim, it:

1. Uses a persistent and nationally unique UIN.
2. Does not depend on secrecy of the UIN for security.
3. Does not treat knowledge of the UIN as authentication.
4. Separates identification, authentication, authorization, and consent.
5. Preserves the canonical national UIN without numeric normalization.
6. Allows existing national UINs to be retained.
7. Places x-UIN User Portal / App governance under the national UIN Issuing Authority.
8. Uses the defined Global UIN structure where global qualification is required.
9. Uses Credential Pairs where the applicable service model requires controlled UIN use, counterparty scope, or contextual traceability, and may additionally use front-end tokenization where reduced UIN exposure is required.
10. Maintains applicable privacy, data-protection, and lawful-processing controls independently from possession of the UIN.

Countries may define additional authentication methods, assurance levels, credential structures, domain profiles, and operating procedures while preserving these principles.

Conformance with NAVS.G4.11 does not imply endorsement or certification by the World Bank or the ID4D initiative.

---

## 11. Governance and Maintenance

NAVS.G4.11 is developed and maintained by **Nastavia** as part of the Nastavia Voluntary Standards system.

The World Bank ID4D initiative is an external conceptual source for the UIN and front-end tokenization approaches referenced by x-UIN. x-UIN is an independent NAVS framework and does not imply World Bank sponsorship, approval, certification, or endorsement.

Revisions to NAVS.G4.11 should preserve the distinction between:

- Persistent identification.
- Authentication and security credentials.
- Authorization and consent.
- National identity authority.
- Context-specific service credentials.
- Implementation-specific technologies.
