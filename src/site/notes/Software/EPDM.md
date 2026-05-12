---
{"dg-publish":true,"permalink":"/software/epdm/","tags":["Software"],"dg-note-properties":{"tags":["Software"],"aliases":["EPDM"],"source":"personal_notes","last_updated":"2026-05-11"}}
---


#Software

ePDM (Engineering Product Data Management) is Promega's engineering drawing and document management system. It is used to check drawings and models in and out, manage file versions, and control document states. Parts and drawings must be checked into ePDM before a shop request can be submitted. Note: EPDM is also a common rubber and seal material used in manufacturing — these are unrelated uses of the same acronym.

> [!info]- How to Use ePDM
>
> **Adding a new file:**
> Save the file to the correct ePDM subfolder using the naming convention (see below). Fill out the data card. Right-click and check in. Change state from "New File" → "New File Complete" → "Approved" (increments major revision).
>
> **Editing an existing file:**
> Right-click → Change State → "Request Change" (sets state to Under Editing). Check out the file. Make edits. Fill out data card if needed. Check in. Change state to "Edit Complete" to increment minor revision, or straight to "Approved" to increment major and reset minor to zero.
>
> **Approving a file:**
> File must be in New File, New File Complete, Under Editing, or Edit Complete state. Right-click → Change State → "Approved" (new file) or "Change Approved" (existing file). Add a comment — reference CC number if applicable.
>
> **Obsoleting a file:**
> Cut the file and paste it into the OBSOLETE folder under the drawing folder. Then right-click → Change State → "Obsolete". If no OBSOLETE folder exists, contact the ePDM Administrator.
>
> **Revision format — Major.Minor:**
> Minor increments each time you hit "Edit Complete" (marks a milestone). Major increments when you hit "Approved" (minor resets to zero). Version increments every check-in where the file differs from the last stored version.
>
> **File naming convention:**
> `EquipmentName_SecondaryEquipmentName_FileType_Identifier`
> — SecondaryEquipmentName and Identifier are optional.
> — FileType examples: Mechanical, Electrical, PLC, HMI, Photo, Operational, DDS.
> — Identifier options: number, compass direction, or short description.
> — Engineering studies: start with `ES-CC#####` then a descriptive name.

> [!info]- Data Card Field Conventions
>
> Data cards have two tabs: an @ icon tab (file-level custom properties) and a named configuration tab (Default for parts/assemblies, Sheet1 for drawings). Fill out both to be safe — the title block pulls from whichever tab the property is linked to.
>
> **Parent Equipment Name:** The equipment model the part is used on. Include both the manufacturer and model so the reader can identify it easily (e.g. `Lightnin Mixer, X5P33`). For parts used across multiple models, list them comma-separated (e.g. `Lightnin Mixer, X5P33, XSS1P33, XSS5P33`). Leave blank if no in-service equipment uses the part yet.
>
> **Parent SAP Number:** Comma-separated list of all equipment SAP numbers the part is used on. Pull from the equipment list in the drawing's title block (Notes section).
>
> **Child Equipment Name / Child SAP Number:** Leave blank unless there is a specific child relationship to document.
>
> **Drawing Type:** Mechanical (for mechanical parts and assemblies).
>
> **Type of File:** Solidworks (for .SLDPRT/.SLDDRW/.SLDASM), PDF (for .pdf).
>
> **Equipment Manufacturer:** Promega for any part fabricated internally or designed by Promega. The original manufacturer name (e.g. Parlec) for stock/purchased components.
>
> **Drawing Description:** Same text that appears in the SolidWorks title block Description field. ALL CAPS to match drawing conventions.
>
> **Drawing Number:** Same as the SAP Material number (per Promega convention, Drawing # = SAP Material #).

> [!info]- Mixer Chuck Destination Folder
>
> [[My Projects/Mixer Chuck/Mixer Chuck\|Mixer Chuck]] parts are stored at:
> `C:\Operations Engineering\MAD-FEYNMAN\EQUIPMENT RELATED DOCS\Feynman Mixers\DRAWINGS\MECHANICAL DRAWINGS`
>
> Confirmed with [[People/Claire Moll\|Claire]] 2026-05-11.

> [!info]- Mixer Chuck Data Card Values
>
> | Part | SAP | Parent Equipment Name | Parent SAP Number |
> | :--- | :--- | :--- | :--- |
> | Chuck Style A | 1016437 | (blank) | (blank) |
> | Chuck Style B | 1016438 | Lightnin Mixer, X5P33 | 102956, 112142, 122278, 122277, 102943 |
> | Chuck Style C | 1016439 | Lightnin Mixer, XSS1P33 | 113417, 113418, 117266, 127950, 120019, 102883 |
> | Stop | 1016455 | Lightnin Mixer, X5P33, XSS1P33, XSS5P33 | full 11 |
> | Collet Cap | 1016457 | Lightnin Mixer, X5P33, XSS1P33, XSS5P33 | full 11 |
> | Spanner Tool Assy | 1016458 | Lightnin Mixer, X5P33, XSS1P33, XSS5P33 | full 11 |
> | Spanner Tool Head | 1016458A | Lightnin Mixer, X5P33, XSS1P33, XSS5P33 | full 11 |
> | Spanner Tool Handle | 1016458B | Lightnin Mixer, X5P33, XSS1P33, XSS5P33 | full 11 |
> | Chuck Tool Assy | 1016459 | Lightnin Mixer, X5P33, XSS1P33, XSS5P33 | full 11 |
> | Chuck Tool Handle | 1016459A | Lightnin Mixer, X5P33, XSS1P33, XSS5P33 | full 11 |
> | Chuck Tool Head | 1016459B | Lightnin Mixer, X5P33, XSS1P33, XSS5P33 | full 11 |
>
> **Full 11 SAP list:** 102956, 112142, 122278, 122277, 102943, 113417, 113418, 117266, 127950, 120019, 102883
>
> Equipment Manufacturer: Promega for all of the above. The [[Definitions/Parlec ER32 Collet\|Parlec ER32 Collet]] (stock component) gets Parlec.

> [!info]- Details & Notes
>
> **Encountered in:** [[My Projects/Mixer Chuck/Mixer Chuck\|Mixer Chuck]] (checking in drawings before shop request submission)
>
> **See also:** [[Definitions/Shop Request\|Shop Request]], [[Definitions/Quality/Change Control\|Change Control]]