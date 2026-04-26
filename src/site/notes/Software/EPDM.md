---
{"dg-publish":true,"permalink":"/software/epdm/","tags":["Software"],"dg-note-properties":{"tags":["Software"],"aliases":["EPDM"],"source":"personal_notes","last_updated":"2026-03-19"}}
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

> [!info]- Details & Notes
>
> **Encountered in:** [[My Projects/Mixer Chuck\|Mixer Chuck]] (checking in drawings before shop request submission)
>
> **See also:** [[Definitions/Shop Request\|Shop Request]], [[Definitions/Change Control\|Change Control]]