# NAVS-201: Voluntary Standard for Shortened Denomination Representation in Information Systems  
**Developed by Nastavia**

---

## 1. Purpose

The **NAVS-201** standard establishes a compact, consistent notation system for representing monetary denominations in information systems where space constraints limit the display of full face values. This is particularly relevant for currencies with large nominal figures (e.g., 1,000,000 and above).

The standard ensures all characters fit within the **Base64URL** character set, making the notation safe for embedding in URLs, digital systems, and Excel-based data exchange forms.

---

## 2. Scope

NAVS-201 applies to software systems, databases, spreadsheets, APIs, and digital tools that process or display monetary denominations in a shortened, structured form for identification, exchange, or analysis purposes.

---

## 3. Notation Structure

The NAVS-201 notation follows a **DZGU** group format:


| Group | Description |
|-------|-------------|
| **D** | First non-zero digit of the denomination. For example, `5` for a 5-unit note or `1` for a 100-unit note. |
| **Z** | Number of trailing zeros, represented as letters: `A` = 1 zero, `B` = 2 zeros, ..., up to `Z` = 26 zeros. For special cases (denominations like 12 or 15), a **strict** numeric digit `1–9` is used. For single-digit denominations (e.g., 5), a mandatory dash `-` is placed. |
| **G** | Generation code of the banknote, as a letter (`A` = first generation, `B` = second, etc.) determined by the issuer's accounting system. If generation tracking is absent, a mandatory dash `-` is used. NAVS-201 strongly encourages always including this group to avoid misinterpretation. |
| **U** | (Optional) Usability indicator, on a scale of `1` (new/unused) to `9` (unusable, must be replaced). Values `2–8` are reserved for user-defined interpretations, allowing customization based on specific needs. |

---

## 4. Currency Prefixing

To ensure unique, unambiguous identification, the notation can be prefixed with the **ISO 4217** three-letter currency code, separated by a dot (`.`):


| Example        | Meaning |
|---------------|---------|
| `USD.1BA`    | USD 100 banknote, first generation. |
| `USD.1B-`    | USD 100 banknote, any generation (generation tracking absent). |
| `USD.1BA1`   | USD 100 banknote, first generation, in pristine/new condition (usability = 1). |
| `JPY.1F-`    | Japanese yen 1,000,000 banknote, sixth generation, no usability indicator. |


---
There may be cases, when those are grouped under the currency group. Then 3 Alpha code could be omitted.

## 5. Character Set Compliance

All components of the NAVS-201 notation are **strictly limited** to the **Base64URL** character set. This guarantees safe embedding in:

- URLs and web addresses
- Digital system identifiers
- Excel and spreadsheet-based data exchange forms

No extended ASCII or special characters are permitted.

---

## 6. Recommendations

- **Mandatory dashes** (`-`) must be used when `Z` (zero group) or `G` (generation group) are not applicable.
- Inclusion of the `U` (usability) group is optional but recommended for enhanced cash inventory tracking.
- Systems using NAVS-201 are encouraged to provide internal mappings or legend tables explaining the customized meanings of values `2–8` in the usability scale.

---

## 7. Examples

| Denomination          | Notation       | Meaning |
|-----------------------|----------------|---------|
| USD 5 (single-digit) | `USD.5--`      | USD 5 banknote, no zeros, no generation tracking. |
| USD 100              | `USD.1BA`      | USD 100 banknote, first generation, usability unspecified. |
| USD 100,000          | `USD.1EA`      | USD 100,000 banknote, first generation. |
| EUR 15 (special)     | `EUR.1-2A`     | EUR 15 banknote, second digit `5` (special numeric case), first generation. |

---

## 8. Compliance and Governance

This standard is intended as a voluntary guideline developed by **Nastavia** and is offered for public use to promote interoperability and consistency across information systems. Organizations adopting NAVS-201 are responsible for ensuring internal adherence and compatibility with their specific use cases.

