---
{"dg-publish":true,"permalink":"/definitions/shop-request/","tags":["Definitions"],"dg-note-properties":{"tags":["Definitions"],"source":"personal_notes","last_updated":"2026-05-11"}}
---


#Definitions

A shop request is the standard form used to request machined parts be fabricated at Promega, whether internally at the [[Buildings/Lamarr\|Lamarr Shop]] or through an external vendor. The form is hosted on Smartsheet and is officially named the **2026 Machine Shop Request**.

Before submitting, drawings and models must be checked into [[Software/EPDM\|EPDM]] and SAP part numbers must be assigned. The same form applies regardless of whether parts are made in-house or sent out.

---

## Form Structure

The form has 14 fields plus a priority tier selector. Required fields are marked with an asterisk (*).

### Field-by-Field Guidance

**Requestor *** — Your name. Used to track who submitted the request.

**Requestor Email** — Your Promega email. Used for follow-up.

**Requestor Department** — Your department (e.g. Operations Engineering).

**Part Description *** — A short description of what is being requested. For multi-part requests, give a project-level description here and put the per-part breakdown in Additional Information. Example: "Mixer Chuck Assembly Parts (collet-style redesign — 8 part types across 3 chuck styles)".

**Type of Request *** — Dropdown. Pick the category that best describes the request:
- Prototype
- Production Part (most common for IPPP parts going into production)
- Emergency Equipment Part - line down
- Safety
- Process Improvement Part
- Rework Vendor Parts

**Requested Date *** — When you need the parts by. The form notes to allow at least 2 weeks if possible. Match this against the priority tier lead times below.

**Name of Project this is for** — The internal project name (e.g. Spectrum, Mixer Chuck). Helps the shop categorize and prioritize.

**Material Type *** — Multi-select dropdown. Choose all materials present in the request:
- 3D Print
- Aluminum
- Steel
- Stainless Steel
- Delrin
- Nylon
- HDPE
- Other

For specific stainless grades (316L, 440C, etc.) pick Stainless Steel and call out the grade in Additional Information.

**Material Source *** — Dropdown. Who is providing the raw stock:
- Ordered by Machine Shop (most common — Travis sources it)
- Provided by Requestor (you bring the stock to the shop)

**Quantity of Assemblies *** — Total number of finished assemblies being requested. If parts don't form assemblies, this can be 1 or matched to the part count.

**Quantity of Finished Parts *** — Total number of individual parts/components across all assemblies. Example: 2 assemblies × 5 parts each = 10. The form gives this exact example.

**Equipment Used** — Dropdown. The fabrication tool that will make the parts:
- CNC Shop (most common for machined parts)
- ZUND (for sheet/flat cutting)
- 3D Printer

**Additional Information** — Free text. Use this generously for any per-part detail the shop needs. For multi-part requests, include a structured breakdown: SAP number, descriptive name, quantity, and the assembly-level math (e.g. "18 = 1 per assembly × 18 assemblies"). Also call out specific stainless grades, surface finish notes, or anything not obvious from the drawings.

**Describe "Other" Finishing** — Free text. Only fill in if a finish is needed that isn't standard machined/deburred. Most parts won't need this.

**File Upload** — Attach PDFs of drawings if helpful. Travis pulls from [[Software/EPDM\|EPDM]] but a direct attachment can speed review.

**Vault Location for Model** — The [[Software/EPDM\|EPDM]] path where the models live. For [[My Projects/Mixer Chuck/Mixer Chuck\|Mixer Chuck]] parts the path is `C:\Operations Engineering\MAD-FEYNMAN\EQUIPMENT RELATED DOCS\Feynman Mixers\DRAWINGS\MECHANICAL DRAWINGS`. Always provide a path so Travis can find the source files.

**Priority *** — Four tiers with defined criteria and typical lead times. See the next section.

---

## Priority Tiers

### Tier 1: Urgent (Red)
Same-day to 48 hours. Use only when production is halted or about to halt, or a QA/regulatory deadline is within 48 hours.

Examples: emergency repair of equipment causing batch delays, CAPA-driven modifications with QA or regulatory due dates, QA hold resolution, sterility failures, fixtures critical for validated production runs.

### Tier 2: High (Orange)
2-4 weeks. R&D Top 10 Projects, Operations Engineering Top Projects, tooling for scheduled batch runs within 5-7 days, in-flight engineering changes tied to commercial manufacturing, new spare parts for critical-path equipment, preventive maintenance fixtures that reduce future downtime.

This is the default for most Operations Engineering project work.

### Tier 3: Medium (Yellow)
4-6 weeks. Ergonomic upgrades, prototype tooling for new product introduction (pre-validation), internal lean initiatives, spare parts for non-critical assets, productivity work without compliance or quality impact.

### Tier 4: Low (Green)
6+ weeks or as capacity allows. Marketing props, training tools, office mounts, signage, backup fixtures already available, cosmetic modifications.

---

## Office Hours

The shop holds office hours **every Monday from 10am - 11am at Lamarr**. Recommended after submitting a request to discuss the project and ensure alignment. Contact one of the following to be added to the invite:

- [[People/Travis Beyer\|Travis Beyer]]
- Chris Rusthoven
- [[People/Kent Toepfer\|Kent Toepfer]]

In-person or virtual attendance is fine — let them know which you prefer.

---

## Worked Example — Mixer Chuck

> [!info]- Mixer Chuck Shop Request (TBD)
>
> Worked example placeholder. Full quantities pending updated assembly count.
>
> **Requestor:** Ryan Meyer
> **Requestor Email:** Ryan.meyer@promega.com
> **Requestor Department:** Operations Engineering
> **Part Description:** Mixer Chuck Assembly Parts (collet-style redesign — 8 part types across 3 chuck styles)
> **Type of Request:** Production Part
> **Name of Project:** Mixer Chuck
> **Material Type:** Stainless Steel, Delrin (specific grades 316L and 440C noted in Additional Information)
> **Material Source:** Ordered by Machine Shop
> **Quantity of Assemblies:** TBD pending final count
> **Quantity of Finished Parts:** TBD
> **Equipment Used:** CNC Shop
> **Vault Location for Model:** `C:\Operations Engineering\MAD-FEYNMAN\EQUIPMENT RELATED DOCS\Feynman Mixers\DRAWINGS\MECHANICAL DRAWINGS`
> **Priority:** TBD (likely Tier 2 — Operations Engineering project)
>
> **Additional Information template:**
> Per-part breakdown for each SAP number — quantity, descriptive name, per-assembly math, and any special notes (material grade, finish, etc.). The collet (1016456) is a stock part from McMaster-Carr — call out separately or handle outside this form.

#unsure-or-needs-to-be-finished

---

> [!info]- Details & Notes
>
> **Form location:** Smartsheet — hosted form, not the underlying sheet itself.
>
> **Encountered in:** [[My Projects/Mixer Chuck/Mixer Chuck\|Mixer Chuck]] (submitting machined parts request)
>
> **See also:** [[Software/EPDM\|EPDM]], [[Software/SAP\|SAP]], [[People/Travis Beyer\|Travis Beyer]], [[Buildings/Lamarr\|Lamarr]], [[People/Nikki Masterson\|Nikki Masterson]], [[People/Claire Moll\|Claire Moll]]
