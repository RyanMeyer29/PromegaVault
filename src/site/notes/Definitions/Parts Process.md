---
{"dg-publish":true,"permalink":"/definitions/parts-process/","tags":["Definitions"],"dg-note-properties":{"aliases":["IPPP","Internally Produced Production Part"],"tags":["Definitions"],"source":"personal_notes","last_updated":"2026-04-03"}}
---


#Definitions

An Internally Produced Production Part (IPPP) is any component produced or manufactured internally by the Operations Engineering or Packaging Engineering departments with the intention of being permanently used in a Promega production environment. Prototype parts are explicitly out of scope. The full process for creating and deploying an IPPP is governed by SOP22698 #unsure-or-needs-to-be-finished (SOP number may also be SOP226898 — verify against the document control system).

The parts process touches [[Software/SAP\|SAP]], [[Software/EPDM\|EPDM]], and the [[Definitions/CoC\|Certificate of Compliance]] form at different stages. Getting a part number from the [[SAP Analyst\|SAP Analyst]] is the first step before anything else happens. As of early 2026, that contact is [[People/Gary McCauley\|Gary McCauley]].

---

## Parts Process — Step by Step

### Step 1 — Part Setup

Request a part number from the SAP Analyst ([[People/Gary McCauley\|Gary McCauley]] as of early 2026). [[People/Nikki Masterson\|Nikki]] is also a contact for SAP part number requests. For fewer than 5 parts, use the [[Definitions/Parts Order Form\|Parts Order Form]] (Smartsheet) to submit the request. For 5 or more parts at once, use the [[Definitions/Multiple Materials Request Spreadsheet\|Multiple Materials Request Spreadsheet]] instead.

The Parts Order Form is available at: https://app.smartsheet.com/b/publish?EQBCT=ad110954f1e047ab85f66a46824875d7

For most fabricated parts, the request type is New SAP ERSA material. Print the completed form to PDF before submitting as a record. Key fields on the form:

- Requester Email: Ryan.meyer@promega.com
- Type of Request: New SAP ERSA material (most common)
- Approver: Claire Moll (Ali Heinemann is not currently an option as approver on this form)
- Material Description: 40-character hard limit — use the naming convention from [[Definitions/Material Naming Convention\|QSOP23.007]]. Format is: Part Name, Use Case, Description/Material, Size, Part Number. Omit fields that don't apply.
- SAP Equipment BOM Information: list each SAP equipment number and BOM quantity (quantity = how many the equipment uses at one time, not production run size)
- Vendor: required — use Travis Beyer / Lamarr Shop for in-house machined parts
- Unit of Measure: EA (each) for most parts
- Building and Storage Location (SLOC): always required — do not assume
- File Upload: attach quote or datasheet if available; attach the Multiple Materials Request Spreadsheet if that route was used
- Comments: include project name and traceability context

For questions on the form, contact [[People/Gary McCauley\|Gary McCauley]] (gary.mccauley@promega.com). The form is managed through Smartsheet and approvals are routed automatically once submitted.

### Step 2 — Create the Engineering Drawing

Create the drawing and save it to [[Software/EPDM\|EPDM]]. Key checklist before the drawing is considered complete:

- Title block is correct and fully filled out
- All critical dimensions have appropriate tolerance ranges annotated
- Critical dimensions are identified (circles are used in SolidWorks for this)
- Revision block is present
- Drawing has a reviewer and approver — "Drawn By" never changes, but "Approved By" updates with every revision
- Proper drawing symbols and callouts are used (follow ASME Y14.5 where applicable)

In [[Software/EPDM\|EPDM]], create a folder with the part number under the appropriate equipment folder. If the part doesn't fit under an existing equipment folder, it can go in the Custom Jigs_Fixtures folder.

### Step 3 — Produce the Part

Make the part, or have it made. Options include:

- Make it yourself using available fabrication equipment
- Have it sourced externally
- Submit a request to the [[Buildings/Lamarr\|Lamarr]] Shop (request via Smartsheet)

When possible, physically mark the part with the part number and revision level using indelible means. If marking directly on the part isn't feasible, use a labeled storage solution instead.

### Step 4 — Complete the Certificate of Compliance (CoC)

The [[Definitions/CoC\|CoC]] must be completed before the part is put into service. Steps:

- Fill out all production information: quantity produced, date of production, who produced them, and where they are being deployed
- Verify all critical dimensions are within acceptable tolerance ranges on each part
- Ensure SAP BOMs are updated to reflect the new part
- If the part is used to determine acceptable quality limits, confirm a PM plan is set up in SAP

Save the completed [[Definitions/CoC\|CoC]] to [[Software/EPDM\|EPDM]] in the same folder as the drawing. The CoC filename must include the part or equipment number so it is easily searchable.

### Step 5 — Deploy the Part

Once the [[Definitions/CoC\|CoC]] is uploaded to [[Software/EPDM\|EPDM]], the part can be turned over to the end user (Production). As the author/originator, it is your responsibility to remove any old parts being replaced. Confirm SAP BOMs are adjusted and any required PM plans are in place.

---

> [!info]- Details & Notes
>
> **Unknowns:** SOP number is uncertain — DOCX references SOP22698, PPTX filename references SOP226898. Verify against the document control system. #unsure-or-needs-to-be-finished
>
> **Encountered in:** [[My Projects/Mixer Chuck\|Mixer Chuck]] (parts process is a key deliverable for this project)
>
> **See also:** [[Software/SAP\|SAP]], [[Software/EPDM\|EPDM]], [[Definitions/CoC\|CoC]], [[Buildings/Lamarr\|Lamarr]], [[People/Gary McCauley\|Gary McCauley]], [[Definitions/Change Control\|Change Control]], [[Definitions/Parts Order Form\|Parts Order Form]], [[Definitions/Multiple Materials Request Spreadsheet\|Multiple Materials Request Spreadsheet]], [[People/Nikki Masterson\|Nikki]]
