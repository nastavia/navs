# NAVS-221: Voluntary Standard for Shortened Denomination Representation in Information Systems for material money forms (Banknotes/Coins/Metals)  
**Developed by Nastavia** (www.nastavia.com)

---

## 1. Purpose

The **NAVS-221** standard establishes a compact, consistent and fixed notation system for representing monetary denominations and material money forms in information systems where space constraints limit the display of full face values. This is particularly relevant for currencies or assets with large nominal figures (e.g., 1,000,000 and above) or when handling various cash types.

The standard ensures all characters fit within the **Base64URL** character set, making the notation safe for embedding in URLs, digital systems, and Excel-based data exchange forms.

---

## 2. Scope

NAVS-221 applies to software systems, databases, spreadsheets, APIs, and digital tools that process or display monetary denominations and material forms in a shortened, structured form for identification, exchange, or analysis purposes.

---

## 3. Notation Structure

The NAVS-221 notation follows a **TDZG[U]** group format:


| Group  | Description                                                                                                                                                                                                                                                                             |
|--------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **T**  | Type of material form: `B` = banknotes, `C` = coins, `M` = metal bars.                                                                                                                                                                                                                  |
| **D**  | First non-zero digit of the denomination. For example, `5` for a 5-unit note or `1` for a 100-unit coin.                                                                                                                                                                                |
| **Z**  | Number of trailing zeros, represented as letters: `A` = 1 zero, `B` = 2 zeros, ..., up to `Z` = 26 zeros. For special cases (denominations like 12 or 25), a **strict** numeric digit `1–9` is used. For single-digit denominations (e.g., 5), a mandatory dash `-` is placed.          |
| **G**  | Generation code, as a letter (`A` = first generation, `B` = second, etc.) determined by the issuer's **actual** accounting system. If generation tracking is absent, a mandatory dash `-` is used. NAVS-221 strongly encourages always including this group to avoid misinterpretation. |
| **U**  | (Optional) Usability indicator, on a scale of `1` (new/unused) to `9` (unusable, must be replaced). Values `2–8` are reserved for user-defined interpretations, allowing customization based on specific needs.                                                                         |

---
**Note.** The option for using SI prefixes in the Z group was considered during the standard preparation. Because not all prefixes are single character and they are not always intuitive, the contunuous model was selected, where majority of cases (usually, in A-F range) are quite simple to rapidly identify for the majority of the expected users.

## 4. Currency Prefixing

To ensure unique, unambiguous identification, the notation **can be optionally** prefixed with the **ISO 4217** three-letter currency code, separated by a dot (`.`). This prefix is optional, and not used, when records or columns are already grouped by currency context.


| Example     | Meaning                                                                             |
|-------------|-------------------------------------------------------------------------------------|
| `USD.B1BA`  | USD banknote, 100 units, first generation.                                          |
| `USD.C5--`  | USD coin, 5 units, no zeros, no generation tracking.                                |
| `XAU.M1CF`  | Gold metal bar, 1,000 units, sixth generation.                                      |
| `THB.C12A1` | Thailand Baht coin, 12 units, first generation, pristine condition (usability `1`). |
| `THB.C25A`  | Thailand Satang coin, 25 units, first generation.                                   |
| `ZWL.B1N-`  | Zimbabwe dollar banknote, 100 trillion units, generation tracking absent.           |

---

## 5. Character Set Compliance

All components of the NAVS-221 notation are **strictly limited** to the **Base64URL** character set. This guarantees safe embedding in:

- URLs and web addresses
- Digital system identifiers
- Excel and spreadsheet-based data exchange forms

No extended ASCII or special characters are permitted.

---

## 6. Recommendations

- **Mandatory dashes** (`-`) must be used when `Z` (zero group) or `G` (generation group) are not applicable.
- Inclusion of the `U` (usability) group is optional but recommended for enhanced inventory tracking.
- Systems using NAVS-221 are encouraged to provide internal mappings or legend tables explaining the customized meanings of values `2–8` in the usability scale.

---

## 7. Compliance and Governance

This standard is intended as a voluntary guideline developed by **Nastavia** and is offered for public use to promote interoperability and consistency across information systems. Organizations adopting NAVS-221 are responsible for ensuring internal adherence and compatibility with their specific use cases.

