# NAVS.G2.21: Compact Cash Denomination Code

**Voluntary Standard for Fixed-Length Operational Representation of Banknote and Coin Denominations**
**Developed and maintained by Nastavia** — https://www.nastavia.com

| Attribute                  | Value                                    |
| :------------------------- | :--------------------------------------- |
| **ID**                     | NAVS.G2.21                               |
| **Name**                   | Compact Cash Denomination Code |
| **Group**                  | NAVS.G2 — Operational Standards          |
| **Version**                | 2026.1                                    |
| **Status**                 | Draft                                    |
| **Publication Date**       | 2026-09-11                                    |
| **Canonical Reference**    | NAVS.G2.21                                    |
| **Supersedes**             | 2025.1                                  |
| **Related NAVS Standards** | None      |

This document is part of the **Nastavia Voluntary Standards (NAVS)** system and is developed and maintained by **Nastavia**. It provides a voluntary reference for compact operational identification of banknote and coin denominations, particularly in information structures where available display space is limited and rapid visual recognition is important.

Adoption of this standard is voluntary unless its use is made mandatory by an adopting organization's internal rules, contractual arrangements, policy, regulation, or another governing instrument. Conformance with this standard means satisfying the provisions explicitly identified as normative within its defined scope; it does not, by itself, constitute certification, legal compliance, or regulatory approval.

Where this standard depends on external standards, their role is identified as normative or informative within this document.

---

## 1. Purpose

NAVS.G2.21 establishes a compact, fixed-length notation for operational identification of banknote and coin denominations.

Its primary intended use is in **bank cash-storage, treasury, branch cash-position, cash inventory, spreadsheet, reporting, and similar operational environments** in which individual denominations are commonly represented as columns or other space-constrained identifiers and where full textual descriptions would make the information structure unnecessarily wide or difficult to scan.

The standard is designed primarily for **rapid visual recognition of frequently used denomination categories**, rather than for repeated manual decoding of every character. A user working regularly with a particular set of currencies may therefore recognize a code directly as a specific tender type without mentally calculating the denomination encoded within it.

The systematic structure nevertheless provides consistent rules for constructing, validating, exchanging, and processing such identifiers.

The principal design objectives are:

* fixed-length representation;
* compactness suitable for dense operational tables;
* rapid human recognition;
* predictable machine processing;
* distinction between banknotes and coins;
* distinction between major and minor currency units;
* explicit identification of exceptional or locally mapped denominations;
* operational distinction between active, unfit, and withdrawn cash;
* suitability for use in URI components and common digital information systems.

---

## 2. Scope

NAVS.G2.21 applies to information systems, spreadsheets, databases, APIs, reports, cash-management tools, and other digital or semi-digital structures that identify physical banknote and coin denominations.

The standard is primarily intended for operational cash-management contexts in banks and similar organizations but may be adopted in other environments where a compact and stable representation is useful.

The standard defines:

* the fixed four-character core representation;
* denomination representation rules;
* banknote and coin classification;
* major-unit and minor-unit distinction;
* special-denomination mapping;
* operational cash status;
* optional currency prefixing;
* character and serialization constraints.

NAVS.G2.21 does **not** define:

* banknote printing batches;
* printing plates;
* serial-number structures;
* signature combinations;
* banknote design generations or series;
* detailed numismatic condition grading;
* counterfeit-detection characteristics;
* authenticity assessment;
* currency conversion;
* monetary valuation;
* precious-metal bars or other non-banknote/non-coin material assets.

An implementation may maintain such information separately from the NAVS.G2.21 representation.

---

## 3. References and Dependencies

### 3.1 Normative References

**ISO 4217 — Codes for the representation of currencies**

ISO 4217 three-letter alphabetic currency codes are used where the optional currency prefix defined by this standard is included.

**RFC 3986 — Uniform Resource Identifier (URI): Generic Syntax**

RFC 3986 provides the basis for the URI-unreserved character considerations described in Section 7.

### 3.2 Informative References

None required for application of this edition.

### 3.3 Related NAVS Standards

No normative dependency on another NAVS standard has been established for this edition.

---

## 4. Terms, Definitions and Abbreviations

### 4.1 Major unit

The principal monetary unit of a currency.

Examples include euro, dollar, pound, lari, and dinar where these represent the principal unit of the applicable currency.

### 4.2 Minor unit

A monetary subdivision of a major currency unit.

Examples include cent and similar subdivisions where applicable.

### 4.3 Regular denomination

A denomination that can be represented by a single non-zero significant digit followed by zero or more trailing zeros.

Examples include:

`5`, `10`, `50`, `100`, `500`, `1,000`, `5,000`, and similar values.

### 4.4 Special denomination

A denomination that is intentionally represented through an implementation-defined two-digit mapping rather than through the regular denomination algorithm.

Special-denomination representation is intended principally for denominations that do not fit the regular single-significant-digit pattern, including values such as `12`, `25`, `250`, `25,000`, or other locally relevant denominations.

### 4.5 Tender type

For the purposes of this standard, a tender type is an operational cash category identified by the combination of physical form, unit level, denomination representation, and operational status.

### 4.6 Active

A denomination or cash category that remains valid for normal operational circulation under the applicable implementation context.

### 4.7 Unfit

A physical cash category that belongs to an active denomination but is not fit for return to normal circulation.

Unfit cash may remain redeemable or otherwise valid; the designation does not imply loss of monetary value.

### 4.8 Withdrawn

A denomination or cash category that has been withdrawn from normal circulation under the applicable implementation context.

A withdrawn denomination may remain redeemable under applicable issuer or legal arrangements.

### 4.9 Implementation-defined mapping

A mapping established by the adopting organization or implementation for interpreting special two-digit denomination codes.

NAVS.G2.21 standardizes the structure of such codes but does not prescribe their denomination assignments.

---

## 5. Core Representation

The normative NAVS.G2.21 core representation consists of exactly four characters:

**`TDZV`**

where:

| Component | Meaning                                                        |
| :-------: | :------------------------------------------------------------- |
|   **T**   | Tender form, unit level, and regular/special denomination mode |
|   **D**   | First denomination character                                   |
|   **Z**   | Second denomination character or trailing-zero indicator       |
|   **V**   | Operational status                                             |

The four-character core remains fixed in length regardless of the magnitude of the represented denomination.

The representation is case-sensitive.

---

## 6. T — Tender Type

The `T` component identifies:

1. banknote or coin;
2. major or minor monetary unit;
3. regular or special denomination representation.

The following values are defined:

| Code | Meaning                     | DZ interpretation                   |
| :--: | :-------------------------- | :---------------------------------- |
|  `B` | Regular major-unit banknote | Regular denomination algorithm      |
|  `b` | Regular minor-unit banknote | Regular denomination algorithm      |
|  `C` | Regular major-unit coin     | Regular denomination algorithm      |
|  `c` | Regular minor-unit coin     | Regular denomination algorithm      |
|  `X` | Special major-unit banknote | Implementation-defined `DD` mapping |
|  `x` | Special minor-unit banknote | Implementation-defined `DD` mapping |
|  `Y` | Special major-unit coin     | Implementation-defined `DD` mapping |
|  `y` | Special minor-unit coin     | Implementation-defined `DD` mapping |

Uppercase values identify **major-unit** forms.

Lowercase values identify **minor-unit** forms.

`B/b` and `X/x` identify banknotes.

`C/c` and `Y/y` identify coins.

`B/b/C/c` indicate that the denomination can be interpreted using the regular denomination algorithm.

`X/x/Y/y` indicate explicitly that the `DZ` component is a special, implementation-defined denomination code and must not be interpreted using the regular denomination algorithm.

---

## 7. DZ — Denomination Representation

### 7.1 Regular denomination mode

For `T` values `B`, `b`, `C`, or `c`, the denomination is represented through the regular `DZ` algorithm.

`D` is the single non-zero significant digit of the denomination and uses a decimal digit from `1` through `9`.

`Z` represents the number of trailing zeros.

The following values are defined:

| Z value | Meaning           |
| :-----: | :---------------- |
|   `-`   | No trailing zeros |
|   `A`   | 1 trailing zero   |
|   `B`   | 2 trailing zeros  |
|   `C`   | 3 trailing zeros  |
|   `D`   | 4 trailing zeros  |
|   `E`   | 5 trailing zeros  |
|   `F`   | 6 trailing zeros  |
|   `G`   | 7 trailing zeros  |
|   `H`   | 8 trailing zeros  |
|   `I`   | 9 trailing zeros  |
|   `J`   | 10 trailing zeros |
|   `K`   | 11 trailing zeros |
|   `L`   | 12 trailing zeros |
|   `M`   | 13 trailing zeros |
|   `N`   | 14 trailing zeros |
|   `O`   | 15 trailing zeros |
|   `P`   | 16 trailing zeros |
|   `Q`   | 17 trailing zeros |
|   `R`   | 18 trailing zeros |
|   `S`   | 19 trailing zeros |
|   `T`   | 20 trailing zeros |
|   `U`   | 21 trailing zeros |
|   `V`   | 22 trailing zeros |
|   `W`   | 23 trailing zeros |
|   `X`   | 24 trailing zeros |
|   `Y`   | 25 trailing zeros |
|   `Z`   | 26 trailing zeros |

Examples:

| Denomination |  DZ  |
| -----------: | :--: |
|            5 | `5-` |
|           10 | `1A` |
|           50 | `5A` |
|          100 | `1B` |
|          500 | `5B` |
|        1,000 | `1C` |
|        5,000 | `5C` |
|     5 × 10¹² | `5L` |

The alphabetical zero-count convention provides a fixed-width representation across both ordinary and exceptionally large denominations.

Users are not expected to calculate the meaning of the zero-count character during routine use. In frequently used operational environments, the complete four-character code is expected to function primarily as a learned and visually recognizable tender identifier.

### 7.2 Special denomination mode

For `T` values `X`, `x`, `Y`, or `y`, both `D` and `Z` are decimal digits.

The resulting two-character `DZ` value is an **implementation-defined denomination code** expressed in `DD` form.

NAVS.G2.21 does not prescribe the mapping between a particular `DD` value and a monetary denomination.

For example, an implementation may define:

| DZ code | Locally mapped denomination |
| :-----: | --------------------------: |
|   `26`  |                         250 |
|   `28`  |                      25,000 |

These mappings are illustrative only and are not universal NAVS.G2.21 assignments.

Special-denomination codes are not numerically comparable by their `DD` value alone.

For example, code `28` does not inherently represent a greater denomination than code `26`.

Where special-denomination codes are exchanged between systems, interpretation depends on the applicable implementation mapping.

---

## 8. V — Operational Status

The `V` component provides a compact operational status relevant to cash handling and recirculation.

The following values are defined:

| Code | Meaning                                             |
| :--: | :-------------------------------------------------- |
|  `A` | Active and fit for normal circulation               |
|  `U` | Active but unfit for recirculation                  |
|  `W` | Withdrawn from normal circulation                   |
|  `-` | Operational status is not tracked or not applicable |

### 8.1 Active — `A`

`A` identifies cash belonging to an active denomination and suitable for normal operational circulation.

### 8.2 Active but unfit — `U`

`U` identifies cash belonging to an active denomination but classified by the applicable cash-management process as unfit for return to circulation.

The designation concerns operational recirculation and does not imply that the monetary item has ceased to have legal or redemption value.

### 8.3 Withdrawn — `W`

`W` identifies a denomination or cash category withdrawn from normal circulation.

The code does not distinguish between different post-withdrawal arrangements, such as continuing redemption by an issuing institution.

### 8.4 Status not tracked — `-`

`-` may be used where the adopting implementation does not maintain operational status as part of the tender code or where such status is not applicable.

### 8.5 Design and print series

`V` does not identify banknote design generations, printing series, signature variants, production batches, printing plates, or similar issuance characteristics.

Where several design generations remain operationally active, they may share the same NAVS.G2.21 representation.

The purpose of `V` is operational cash treatment rather than historical or numismatic differentiation.

---

## 9. Currency Prefix

A NAVS.G2.21 representation may optionally be prefixed with the applicable ISO 4217 three-letter alphabetic currency code followed by a full stop (`.`).

The complete form is:

**`CCC.TDZV`**

where `CCC` is the ISO 4217 currency code.

Example:

`USD.B1BA`

The currency prefix may be omitted where currency context is already provided unambiguously by the containing table, record, column group, dataset, system screen, file, or other information structure.

Accordingly:

**Contextual form:** `TDZV`
**Currency-qualified form:** `CCC.TDZV`

The contextual four-character form is particularly suitable for bank cash-position tables in which the currency is already established at worksheet, section, account, or other grouping level.

---

## 10. Character Set and Serialization

NAVS.G2.21 uses only ASCII characters drawn from the following repertoire:

* uppercase letters `A–Z`;
* lowercase letters `a–z`;
* decimal digits `0–9`;
* hyphen-minus `-`;
* full stop `.` when the optional currency prefix is present.

Whitespace is not part of a canonical NAVS.G2.21 representation.

The ASCII hyphen-minus `-` is distinct from typographic dash characters and must not be substituted by an en dash, em dash, Unicode hyphen, full-width hyphen, or visually similar character.

The representation is case-sensitive because case carries semantic meaning in the `T` component.

All characters used by the canonical representation belong to the RFC 3986 unreserved character repertoire. A canonical NAVS.G2.21 value therefore does not require percent-encoding when represented as data within URI components, subject to the rules of the applicable URI scheme and implementation.

NAVS.G2.21 does not define or require Base64 or base64url encoding.

---

## 11. Examples

This section is informative.

### 11.1 Regular major-unit banknote

`USD.B1BA`

Interpretation:

`USD` — United States dollar
`B` — regular major-unit banknote
`1B` — denomination 100
`A` — active and fit for circulation

### 11.2 Major-unit and minor-unit coins

`EUR.C1-A`

Regular major-unit coin with denomination 1, active and fit for circulation.

`EUR.c1-A`

Regular minor-unit coin with denomination 1, active and fit for circulation.

The distinction between `C` and `c` prevents ambiguity between a one-major-unit coin and a one-minor-unit coin belonging to the same currency.

### 11.3 Active denomination, unfit cash

`USD.B1BU`

Regular major-unit 100-denomination banknote belonging to an active denomination but classified as unfit for recirculation.

### 11.4 Special denomination

Assume an implementation defines:

`26` → 250

The representation:

`IQD.X26A`

then identifies an active major-unit banknote whose denomination is resolved through the local special-denomination mapping.

### 11.5 Another special denomination

Assume the same implementation defines:

`28` → 25,000

The representation:

`IQD.X28A`

identifies the corresponding active major-unit banknote.

The `26` and `28` codes are local mapping identifiers and are not interpreted through the regular trailing-zero algorithm.

### 11.6 Large denomination

`B5LA`

represents a regular major-unit banknote with a denomination structurally encoded as `5 × 10¹²`, active and fit for circulation.

In routine operational use, staff may recognize `B5LA` directly as the applicable tender category without calculating the meaning of `L`.

---

## 12. Conformance and Adoption

A NAVS.G2.21-conformant core representation uses exactly four characters in `TDZV` order.

A conformant implementation follows the defined semantics of the characters it uses.

For regular tender types `B`, `b`, `C`, and `c`:

* `D` uses a decimal digit from `1` through `9`;
* `Z` uses `-` or an uppercase letter `A–Z` according to the trailing-zero convention.

For special tender types `X`, `x`, `Y`, and `y`:

* `D` is a decimal digit;
* `Z` is a decimal digit;
* the resulting `DD` value is interpreted through the applicable implementation-defined mapping rather than through the regular denomination algorithm.

`V` uses only `A`, `U`, `W`, or `-` with the meanings defined by this standard.

Where a currency-qualified representation is used, the prefix follows the form `CCC.` using the applicable ISO 4217 alphabetic currency code.

An implementation is not required to use every tender type or every operational status defined by NAVS.G2.21.

For example, an implementation dealing only with major-unit banknotes may use only `B`, `X`, and the relevant `V` values.

Local denomination mappings are permitted for special tender types and do not affect conformance provided that the `TDZV` structure and the special-denomination interpretation rules are preserved.

Additional implementation attributes may be maintained outside the NAVS.G2.21 token.

An extended identifier that changes the four-character `TDZV` core structure is not a canonical NAVS.G2.21 core representation unless such an extension is defined by a later NAVS publication or revision.

---

## 13. Implementation Guidance

This section is informative.

NAVS.G2.21 is intended to support recognition rather than force manual decoding.

In a typical bank cash-storage or branch cash-position matrix, staff may work repeatedly with the same limited set of tender types. Familiar codes are therefore expected to become recognizable as complete operational identifiers.

Implementations using `X`, `x`, `Y`, or `y` should maintain an accessible mapping table identifying the denomination represented by each locally assigned `DD` code.

Where several systems exchange NAVS.G2.21 special-denomination codes, those systems should use the same mapping or otherwise exchange sufficient mapping information to interpret the values consistently.

Implementations may also maintain additional attributes independently, including issuer series, design version, detailed fitness grade, legal-tender status, redemption rules, authenticity status, serial numbers, or storage characteristics.

Such attributes are intentionally outside the compact NAVS.G2.21 core where they are not required for rapid operational tender identification.

---

## 14. Governance and Maintenance

NAVS.G2.21 is developed and maintained by **Nastavia** as part of the Nastavia Voluntary Standards system.

Future revisions may clarify representation rules, extend defined tender categories, improve interoperability provisions, or address implementation experience while preserving the objective of compact and predictable operational identification.

Interpretation issues and proposed changes are handled through the applicable NAVS publication and maintenance process.

Formal change-control, feedback, versioning, and supersession procedures will follow the NAVS-wide governance model as those mechanisms are formalized.

This standard does not establish a certification mechanism.

---

## Annex A — Compact Reference Table

This annex is informative.

### A.1 Structure

**`TDZV`**

### A.2 Tender type

| Code | Meaning                     |
| :--: | :-------------------------- |
|  `B` | Regular major-unit banknote |
|  `b` | Regular minor-unit banknote |
|  `C` | Regular major-unit coin     |
|  `c` | Regular minor-unit coin     |
|  `X` | Special major-unit banknote |
|  `x` | Special minor-unit banknote |
|  `Y` | Special major-unit coin     |
|  `y` | Special minor-unit coin     |

### A.3 Regular Z values

`-` = 0 zeros
`A` = 1 zero
`B` = 2 zeros
…
`Z` = 26 zeros

### A.4 Special denomination

For `X/x/Y/y`:

**`DZ = DD`**

where `DD` is a two-digit implementation-defined denomination code.

### A.5 Operational status

| Code | Meaning                             |
| :--: | :---------------------------------- |
|  `A` | Active and fit                      |
|  `U` | Active but unfit for recirculation  |
|  `W` | Withdrawn                           |
|  `-` | Status not tracked / not applicable |

### A.6 Forms

**Contextual:** `TDZV`
**Currency-qualified:** `CCC.TDZV`
