# NAVS-421: Enhanced Citizen ID (e-CID)  
  
**Voluntary Standard by Nastavia** (www.nastavia.com)
---
### Purpose

The **Electronic Citizen Identifier (e-CID)** is a **persistent, unique, and non-secret digital identifier** assigned to a natural person for use across digital public and private services.

The e-CID functions solely as a **digital reference (alias) to a person** and **does not constitute proof of identity, authentication material, or a security credential**. Its role is to enable **reliable identification, interoperability, and data association**, while all security-critical functions are handled through **separate, purpose-specific mechanisms**.

### Separation of Identification and Control

Under the e-CID model, a clear separation is established between:
- **Identification** (who the person is, referenced by e-CID), and  
- **Authentication, authorization, and consent** (how and under what conditions access is granted).

The e-CID itself is **safe for disclosure**, including within system interfaces, transaction logs, APIs, and interoperability layers. Any action involving access to personal data, service execution, or legal effect requires **explicit user-controlled authorization**, implemented through **time-limited, scope-restricted, and revocable authentication instruments**, such as one-time passwords, cryptographic tokens, or equivalent secure technologies.

### User Control and Data Minimisation

The e-CID framework is designed to ensure that the **individual remains in full control of personal data flows**. In particular:

- Use of the e-CID does **not imply automatic disclosure of personal attributes**.
- Personal data is shared with third parties **only upon explicit consent of the e-CID holder**, for a defined purpose and duration.
- Systems integrating e-CID are expected to request and process **only the minimum data necessary** for the declared service purpose.
- The citizen may review, approve, deny, or revoke data access granted to third parties, in line with applicable legal and technical frameworks.

This approach supports **privacy-by-design and privacy-by-default** principles and aligns with **GDPR requirements**, including lawfulness, purpose limitation, data minimisation, transparency, and user rights over personal data.

### Security and Risk Reduction

Because the e-CID carries **no intrinsic security value**, its exposure or reuse does not enable impersonation, unauthorized access, or data compromise. This significantly reduces systemic risk compared to models where a single identifier simultaneously serves as both **identity reference and authentication secret**.

By decoupling identity reference from security controls, the e-CID approach enables:
- safer interoperability across systems,
- reduced incentives for identity theft,
- and greater resilience of digital public services.

### Interoperability and Digital Public Infrastructure Enablement

The e-CID is intended as a **foundational component of Digital Public Infrastructure (DPI)**. It provides a stable, vendor-neutral, and technology-agnostic reference that can be used consistently across:

- government registries and service platforms,
- regulated private-sector services (e.g. banking, utilities, telecom),
- cross-sector and cross-border digital interactions, where legally permitted.

The e-CID enables systems to interoperate without duplicating identity data, synchronising sensitive personal information, or enforcing a single technical implementation model.

### Incremental and Voluntary Adoption

The e-CID is defined as a **voluntary standard**, allowing institutions and service providers to:
- adopt it incrementally,
- integrate it with existing identity, authentication, and trust services,
- and align implementation with national legislation, institutional mandates, and technical maturity.

This flexibility supports experimentation, piloting, and phased rollout, while preserving compatibility with existing systems and enabling future evolution of digital identity ecosystems.

### Illustrative Usage Examples

Typical uses of e-CID include, but are not limited to:
- referencing a citizen consistently across multiple public services without exposing personal identifiers,
- enabling secure, consent-based data exchange between government agencies,
- facilitating user-approved sharing of verified attributes with private service providers,
- supporting digital service access where identity reference is required but permanent data disclosure is not.
