# NAVS.701: Voluntary Standard for Electronic Citizen Identifier (e-CID)
**Developed by Nastavia** (www.nastavia.com)

---

## 1. Purpose

The **NAVS.701** standard defines a voluntary, interoperable approach for implementing an **Electronic Citizen Identifier (e-CID)** as a non-secret digital reference to a natural person.

The purpose of this standard is to enable **safe, consistent, and privacy-preserving identification** across digital public and private services by clearly separating **identification** from **authentication, authorization, and consent mechanisms**. NAVS.701 is designed to reduce systemic identity risks, support Digital Public Infrastructure (DPI), and improve citizen control over personal data usage.

---

## 2. Scope

NAVS.701 applies to:

- Government information systems and registries
- Digital public service platforms
- Regulated and non-regulated private-sector digital services
- Interoperability frameworks, APIs, and data exchange layers

The standard is applicable wherever a stable person-level reference is required **without exposing personal data or security credentials**.

---

## 3. e-CID Concept and Definition

The **Electronic Citizen Identifier (e-CID)** is a **persistent, unique, and non-secret digital identifier** assigned to a natural person.

The e-CID functions exclusively as a **digital alias** and:

- **Does not** serve as a password, credential, or authentication factor
- **Does not** provide proof of identity by itself
- **Does not** enable access to personal data or services without additional authorization

Its sole purpose is to provide a **reliable reference key** for associating records, transactions, and interactions across systems.

---

## 4. Separation of Identification and Security Functions

NAVS.701 establishes a strict separation between:

- **Identification** — referencing a person using e-CID
- **Authentication** — verifying the person’s presence or intent
- **Authorization** — determining permitted actions
- **Consent** — approving data access or processing

The e-CID itself is **safe for disclosure** and may appear in user interfaces, logs, APIs, and interoperability exchanges. Any operation with legal, financial, or personal-data impact requires **explicit, user-controlled authorization**, implemented via:

- time-bound one-time passwords (OTP),
- cryptographic tokens,
- or equivalent secure mechanisms.

---

## 5. User Control and Data Protection

The e-CID framework is designed to ensure **full control by the e-CID holder** over personal data shared with third parties.

In particular:

- Use of an e-CID does **not imply disclosure** of personal attributes
- Personal data is shared **only upon explicit, informed consent**
- Consent must be **purpose-limited, time-bound, and revocable**
- Systems should request and process **only the minimum data necessary**

This approach aligns with **GDPR principles**, including lawfulness, purpose limitation, data minimisation, transparency, and user rights over personal data.

---

## 6. Security and Risk Reduction Principles

Because the e-CID carries **no intrinsic security value**, its exposure does not enable:

- impersonation,
- unauthorized access,
- or direct misuse of personal data.

By decoupling identity reference from security controls, NAVS.701 significantly reduces risks commonly associated with static identifiers and supports more resilient digital service ecosystems.

---

## 7. Interoperability and DPI Enablement

The e-CID is intended as a **foundational building block of Digital Public Infrastructure (DPI)**. It enables interoperability across systems without requiring:

- duplication of identity records,
- synchronization of sensitive personal data,
- or uniform technical implementations.

The e-CID may be used consistently across public and private services, subject to applicable legal frameworks.

---

## 8. Illustrative Usage Scenarios

Typical use cases of e-CID include:

- consistent citizen referencing across multiple public services,
- consent-based data exchange between government institutions,
- user-approved sharing of verified attributes with private service providers,
- digital service access where identification is required but permanent data disclosure is not.

---

## 9. Voluntary Adoption and Evolution

NAVS.701 is defined as a **voluntary standard**. Organizations may:

- adopt it incrementally,
- integrate it with existing identity and trust frameworks,
- pilot and evolve implementations over time.

The standard is designed to remain technology-agnostic and adaptable to legal, institutional, and technical developments.

---

## 10. Compliance and Governance

This standard is provided as a voluntary guideline developed by **Nastavia** to promote interoperability, security, and user-centric digital identity practices.

Organizations adopting NAVS.701 are responsible for ensuring alignment with applicable legislation, regulatory requirements, and internal governance policies.
