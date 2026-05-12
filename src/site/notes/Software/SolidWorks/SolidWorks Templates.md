---
{"dg-publish":true,"permalink":"/software/solid-works/solid-works-templates/","tags":["Software","My-Projects"],"dg-note-properties":{"tags":["Software","My-Projects"],"aliases":["SW Templates"],"source":"personal_notes","last_updated":"2026-05-07"}}
---

#Software #My-Projects

SolidWorks template files used at Promega for part, assembly, and drawing creation. Templates are stored in the SolidWorks template directory and load automatically on new file creation. The goal of this project is to make sure all templates are properly configured so new files don't require manual cleanup each time.

## Status

In progress -- see task items below.

## To Do

- [ ] 3D part template: confirm custom properties are present (SAP#, Equipment#, Description, Material, Finish, DesignedBy, etc.)
- [ ] 3D part template: set lighting to a normal/standard configuration
- [ ] 3D part template: hide all reference planes on new file creation
- [ ] Drawing template: add a general note at the top for breaking sharp edges (e.g. "DEBURR AND BREAK ALL SHARP EDGES")
- [ ] Drawing template: link the Drawing Number field in the title block to the SAP# custom property so they stay in sync automatically

---

## Title Block Templates

### Part Drawing Template
Used for individual machined or fabricated parts. Title block should pull from custom properties via linked fields. Drawing number field should be linked to SAP# property. General notes section should include the break sharp edges note by default.

### Assembly Drawing Template
Used for multi-part assemblies. Same title block linking rules apply. BOM table should be pre-configured.

### Sheet Metal Drawing Template
Used for sheet metal parts. May need flat pattern view pre-configured. Same title block and notes requirements as part drawing template.

> [!info]- Details & Notes
>
> **Unknowns:** Template file locations on the network not yet confirmed -- need to find where Promega stores the master templates
>
> **See also:** [[Software/SolidWorks/Solidworks\|Solidworks]], [[Software/SolidWorks/Solidworks Sheet Metal\|Solidworks Sheet Metal]], [[Software/EPDM\|EPDM]]
